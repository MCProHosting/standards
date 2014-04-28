# Javascript Conventions

The following conventions are based on a [previous document](http://Javascript.crockford.com/code.html) and the PSR standards (for PHP).

### Delivery

Javascript programs should be stored in and delivered as .js files.

Javascript code should not be embedded in HTML files unless the code is specific to a single session. Code in HTML adds significantly to pageweight with no opportunity for mitigation by caching and compression.

When using Javascript on the client side, `<script src="filename.js"></script>` tags should be placed as late in the body as possible. There is no need to use the language or type attributes.

### General

There must not be a hard limit on line length.

The soft limit on line length must be 120 characters; automated style checkers must warn but must not error at the soft limit.

Lines should not be longer than 80 characters; lines longer than that should be split into multiple subsequent lines of no more than 80 characters each.

There must not be trailing whitespace at the end of non-blank lines.

Blank lines may be added to improve readability and to indicate related blocks of code.
 
There must not be more than one statement per line, except in the event of ternary operations. Ternary operators must not be nested.
 
### Variable Declarations

All variables must be declared with `var` before use. Implied global variables should never be used. If it is necessary that a variable be globally available on client-side code - a very rare instance - it may be set as a property of the `window`.

Each variable declaration should be given its own line. Multiple variables may be declared at once in the following format:

```
var foo    = 23,
    bar    = 89,
    foobar = foo + bar;
```

### Function Declarations

Functions should be defined as a function literal in a variable. One space must be inserted before and after the parameter list of the function, and after each comma within the list.

Argument lists may be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list must be on the next line, and there must be only one argument per line.

When the argument list is split across multiple lines, the closing parenthesis and opening brace must be placed together on their own line with one space between them.

For example:

```
var develop = function (developer, language) {
    console.log(developer + ' wrote in ' + language + '!');
};
```

If a function must be defined and invoked at the same time, the following format may be used:

```
var develop;
(develop = function (developer, language) {
    console.log(developer + ' wrote in ' + language + '!');
})('Connor', 'Javascript');
```

### Names

The underscore may only be used as the first character of a name only in regards to private or protected properties of objects.

All variables must only contain lowercase letters and use snake_case, except in the event of a variable containing a jQuery object (the variable should be prefixed with a dollar sign) or when defining a constant (must only contain uppercase letters).

Constructor functions which must be used with the new prefix should be written in StudlyCase.

### Statements

#### Simple Statements

Each line should contain at most one statement. Put a ; (semicolon) at the end of every simple statement. Note that an assignment statement which is assigning a function literal or object literal is still an assignment statement and must end with a semicolon.

Javascript allows any expression to be used as a statement. This can mask some errors, particularly in the presence of semicolon insertion. The only expressions that should be used as statements are assignments and invocations.

#### Compound Statements

Compound statements are statements that contain lists of statements enclosed in { } (curly braces).

 * The enclosed statements should be indented four more spaces.
 * The { (left curly brace) should be at the end of the line that begins the compound statement.
 * The } (right curly brace) should begin a line and be indented to align with the beginning of the line containing the matching { (left curly brace).
 * Braces should be used around all statements, even single statements, when they are part of a control structure, such as an if or for statement. This makes it easier to add statements without accidentally introducing bugs.

#### `return` Statement

A `return` statement with a value should not use parentheses around the value being returned. The return value expression must start on the same line as the return keyword in order to avoid semicolon insertion.

#### `if` Statement

The `if` class of statements should have the following form:

```
if (condition) {
    statements
}

if (condition) {
    statements
} else {
    statements
}

if (condition) {
    statements
} else if (condition) {
    statements
} else {
    statements
}
```

#### `for` Statement

A for class of statements should have the following form:

```
for (var i = 0, l = items.length; i < l; i++) {
    doSomething(items[i]);
}

for (key in item) {
    if (item.hasOwnProperty(key)) {
        statements
    }

    doSomething(item[key]);
}
```

The first form should be used with arrays and with loops of a predetermined number of iterations. The initialization should include a declaration of the "pointer" variable as well as a declaration the the length of the list to iterate over.

The second form is used to iterate over objects. A check for `item.hasOwnProperty` must be done for iterating over objects which inherit properties from other objects.

#### `while` Statement

A while statement should have the following form:

```
while (condition) {
    statements
}
```

#### `do` Statement

A do statement should have the following form:

```
do {
    statements
} while (condition);
```

`switch` Statement

A switch statement should have the following form:

```
switch (expression) {
    case expression:
        statements
        break;
    default:
        statements
}
```

Each group of statements (except the default) should end with break, return, or throw. Do not fall through.

#### `try` Statement

The try class of statements should have the following form:

```
try {
    statements
} catch (variable) {
    statements
}

try {
    statements
} catch (variable) {
    statements
} finally {
    statements
}
```

#### `continue` Statement

Avoid use of the continue statements in complex loops. It tends to obscure the control flow of the function.

#### `with` Statement

The with statement should not be used.

#### Operators, Assignments

Every operator must be surrounded by a single space.

```
var i = 2,
    j = debug ? 'hello' : 'world';
```

Ternary operators should not be nested. Remember, readability is king. Your code will be compressed upon deployment if it needs to be.

Avoid doing assignments to existing variables in the condition part of if and while statements. It is preferred to use the `!==` and `===` operators, rather than `!=` or `==`, in most cases, to avoid type coercion.

```
if (var i = getData()) { /* ... */ } // Okay!
if (i = getData()) { /* ... */ } // Not okay!

if (i === getData()) { /* ... */ } // Okay!
if (i == getData()) { /* ... */ } // Avoid this
```

#### Callbacks

Do not nest callbacks deeply. Pass by variable reference, or use an `async.series`-like function to manage your nestings. Generic callbacks, particularly when developing server-side in Node.js, should pass an error (or `null` if no error), as the first argument in the callback, and appropriate function output in the following arguments. 

For example, this is a rather useless snippet that just opens and closes a file, using [async](https://github.com/caolan/async#series) for all the dirty work.

```
var file;
async.series([
    function (next) {
        fs.open('data.csv', 'r', function (err, handle) {
            file = handle;
            next(err);
        });
    },
    function (next) {
        fs.close(file, next);
    } 
], callback);
```

#### `eval` is Evil

In a few cases, it's useful. Module loaders (such as Require.js) and special-use tools like Angular make use of it, but in most day-to-day coding, `eval` should be avoided.
