# React

## Table of contents

- [General layout](#general-layout)
- [Fragments](#fragments)
- [Multi line JSX](#multi-line-jsx)
- [Quotes](#quotes)
- [Component naming](#component-naming)
- [Prop alignment](#prop-alignment)
- [Prop naming](#prop-naming)

## General layout

General layout and formatting of a React component

```js
// absolute imports first (i.e. anything from node_modules)
import React, { Fragment, useEffect } from 'react';
import PropTypes from 'prop-types';

// relative imports next (anything from within the app)
import SubComponent from './sub-component';

const MyComponent = ({ requiredProp, optionalProp }) => { //destructure props here for readability, split onto separate lines if there are a lot of them
  // any functions, useEffect, useState listed first
  useEffect(() => {
    //rest of useEffect code
  }, [optionalProp]);

  // return the component JSX
  return (
    <Fragment>
      <SubComponent />
      { /* rest of component JSX */ }
    </Fragment>
  );
};

// specify default values for any optional props
MyComponent.defaultProps = {
  optionalProp: false,
}

// specify the prop types and whether they are required
MyComponent.propTypes = {
  optionalProp: PropTypes.bool,
  requiredProp: PropTypes.string.isRequired,
};

// export the component as default
export default MyComponent;
```

[back to top](#table-of-contents)

## Fragments

Fragments should be used where necessary, rather than using a wrapping `<div>` or other element, as they prevent unecessary elements being added to the DOM.  There are several ways to use Fragments in React, (`<Fragment>`, `<>`, `<React.Fragment>`), we prefer to import `Fragment` at the top of the file and then use it as `<Fragment></Fragment>`.  `<>` can easily be missed and `<React.Fragment>` is a pain to type.

```js
// bad
return (
  <>
    <Component />
    <Component />
    <React.Fragment>
      <Component />
      <Component />
    </React.Fragment>
  <>
);


// good
import { Fragment } from 'React';

return (
  <Fragment>
    <Component />
    <Component />
    <Fragment>
      <Component />
      <Component />
    </Fragment>
  </Fragment>
);

```

[back to top](#table-of-contents)

## Multi line JSX

Multi-line JSX should be wrapped in enclosing parenthesis to aid readability.

```js
// bad
return (
  <ul>
    { someData.map(data =>
      <li>{ data.value }</li>
    ) }
  </ul>
);

// good
return (
  <ul>
    { someData.map(data => (
      <li>{ data.value }</li>
    ) ) }
  </ul>
);
```

[back to top](#table-of-contents)

## Quotes

Use double quotes (`"`) for JSX attributes as this mirrors the HTML syntax.  All other JavaScript should use single quotes.

```js
// bad
<Component propOne='test123' />

// good
<Component propOne="test123" />
```

[back to top](#table-of-contents)

## Component naming

React components should use PascalCase.

```js
// bad
<mycomponent />
<MYCOMPONENT />

// good
<MyComponent />
```

[back to top](#table-of-contents)

## Prop alignment

Keep props on one line if they will fit within 80 characters, use a separate line for each prop if not.

```js
// bad
<Component propOne="123" propTwo="456" propThree="789" propFour="abc" propFive="def" />

// good
<Component
  propOne="123"
  propTwo="456"
  propThree="789"
  propFour="abc"
  propFive="def"
/>
```

[back to top](#table-of-contents)

## Prop naming

Use camel case for prop names.

```js
// bad
<Component PropOne="test123" />

// good
<Component propOne="test123" />
```

[back to top](#table-of-contents)