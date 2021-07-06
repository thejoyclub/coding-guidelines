# CSS & Sass

We favour BEM (Block-Element-Modifier) as a naming convention for writing our CSS as it defines a clear relationship between a HTML element and its styles, it decreases the chances of naming conflicts and reduces the specificity of styles.

See [introduction to BEM](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/) for more info.

## BEM example

### React component

```js
const BlogArticle = () => (
  <section className="blog-article">
    <h1 className="blog-article__heading">A blog</h1>
    <p className="blog-article__content">Lorem ipsim</p>
    <p className="blog-article__content blog-article__content--highlight">Dolor sit amet</p>
  </section>
);
```

### Resulting BEM SCSS structure

```scss
.blog-article {
  &__heading {}

  &__content {
    &--highlight {}
  }
}
```

## Table of contents

- [ID selectors](#id-selectors)
- [Variable naming](#variable-naming)
- [Nesting](#nesting)

## ID selectors

ID selectors should be avoided where possible as they introduce unecessary specificity, the same result can be achieved with a class.

[back to top](#table-of-contents)

## Variable naming

Use dash case for SCSS variable names.

```scss
// bad
$my_var: red;
$MyVar: red;

// good
$my-var: red;

```

[back to top](#table-of-contents)

## Nesting

Using BEM with Sass can lead to overly nested styles, which are difficult to read and can be overly specific.  Try to avoid nesting more than 3 levels deep.  This can normally be avoided by reviewing the markup and classes you have, you may be able to add another class to remove the need for nesting.

```scss
// bad
.page {
  .container {
    .element {
      .inner-element {
        color: red; 
      }
    }
  }
}

// good
.inner-element {
  color: red;
}

```

[back to top](#table-of-contents)