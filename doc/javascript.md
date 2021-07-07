# JavaScript

## Table of contents

- [Strings](#strings)
- [Spacing](#spacing)
- [Semicolons](#semicolons)
- [Variables](#variables)
- [Comparison Operators](#comparison-operators)
- [Ternaries](#ternaries)

## Strings

For consistency please define strings using single quotes (`'`).  If you need to build a string programmatically use template literals over concatentation as template literals are easier to read and handle newlines properly.

```js
// bad
const myString = "test123";
const myString = `test123`;
const sayHello = name => 'Hello ' + name;

// good
const myString = 'test123';
const sayHello = name => `Hello ${name}`;

```

[back to top](#table-of-contents)

## Spacing

### Whitespace

Use 2 spaces rather than 4, this is particularly helpful when writing JSX which can contain a lot of nested elements.  2 spaces in this instance will help to keep the code visible in your editor.

```js
// bad
function myFunc() {
....const myVar = 'test123';
}

// good
function myFunc() {
..const myVar = 'test123';
}
```

### Space before parenthesis

Use a single space before and after the parenthesis for control statements (`if`, `while` etc).

```js
// bad
if(someCondition){}

//good
if (someCondition) {}
```

### Blank line after block statements

Use a new line after block statements, before the next statement

```js
// bad
if (someCondition) {
  return true;
}
return false;

//good
if (someCondition) {
  return true;
}

return false;
```

[back to top](#table-of-contents)

## Semicolons

Always terminate statements with a semicolon.  When JavaScript encounters a line break without a semicolon, it uses Automatic Semicolon Insertion to decide whether it should regard that line break as the end of the statement and add a semicolon. This behaviour can be erratic and a misplaced semicolon will break your code.

```js
// bad
const myVar = 'test123'

// good
const myVar = 'test123';
```

[back to top](#table-of-contents)

## Variables

Always use `const` and `let` to declare variables, these are block scoped rather than global so prevents us polluting the global namespace.

```js
// bad
myVar = 'test123';

//good
const myVar = 'test123';
```

[back to top](#table-of-contents)

## Comparison Operators

Due to the nature of JavaScript type coercion usage of `==` or `!=` can lead to surprising results, as such it's safer to always rely on the type-safe equality operators `===` and `!==`, which will mean the type of the statements in the condition will also be checked.

```js
// bad
3 == '3' //true

// good
3 === '3' //false
```

[back to top](#table-of-contents)

## Ternaries

Ternaries should not be nested and should generally fit on a single line, any longer than this and it may be an indication that an `if` statement will probably be more readable.  Nested ternaries should also be avoided, most of the time the logic for these could be separated out into two separate statements before checking.

```js
// bad
const myVar = condition1 < condition2 ? 'case1' : condition3 === condition4 ? 'case2' : null;


// good
const firstValue = condition1 < condition2;
const secondValue = condition3 === condition4;

const myVar = firstValue || secondValue;

if (test) {
  return false;
}
```

[back to top](#table-of-contents)