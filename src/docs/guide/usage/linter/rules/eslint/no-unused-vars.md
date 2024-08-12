<!-- This file is auto-generated by tasks/website/src/linter/rules/doc_page.rs. Do not edit it manually. -->

# eslint/no-unused-vars <Badge type="info" text="Nursery" />

<div class="rule-meta">
<Alert class="fix" type="info">
<span class="emoji">⚠️💡</span> A dangerous suggestion is available for this rule.
</Alert>
</div>

### What it does

Disallows variable declarations or imports that are not used in code.

### Why is this bad?

Variables that are declared and not used anywhere in the code are most
likely an error due to incomplete refactoring. Such variables take up
space in the code and can lead to confusion by readers.

A variable `foo` is considered to be used if any of the following are
true:

- It is called (`foo()`) or constructed (`new foo()`)
- It is read (`var bar = foo`)
- It is passed into a function as an argument (`doSomething(foo)`)
- It is read inside of a function that is passed to another function (`doSomething(function() { foo(); })`)

A variable is _not_ considered to be used if it is only ever declared
(`var foo = 5`) or assigned to (`foo = 7`).

#### Ignored Files

This rule ignores `.d.ts` files and `.vue` files entirely. Variables,
classes, interfaces, and types declared in `.d.ts` files are generally
used by other files, which are not checked by Oxlint. Since Oxlint does
not support parsing Vue templates, this rule cannot tell if a variable
is used or unused in a Vue file.

#### Exported

The original ESLint rule recognizes `/* exported variableName */`
comments as a way to indicate that a variable is used in another script
and should not be considered unused. Since ES6 modules are now a TC39
standard, Oxlint does not support this feature.

### Example

Examples of **incorrect** code for this rule:

```javascript
/*eslint no-unused-vars: "error"*/
/*global some_unused_var*/

// It checks variables you have defined as global
some_unused_var = 42;

var x;

// Write-only variables are not considered as used.
var y = 10;
y = 5;

// A read for a modification of itself is not considered as used.
var z = 0;
z = z + 1;

// By default, unused arguments cause warnings.
(function (foo) {
  return 5;
})();

// Unused recursive functions also cause warnings.
function fact(n) {
  if (n < 2) return 1;
  return n * fact(n - 1);
}

// When a function definition destructures an array, unused entries from
// the array also cause warnings.
function getY([x, y]) {
  return y;
}
```

Examples of **correct** code for this rule:

```javascript
/*eslint no-unused-vars: "error"*/

var x = 10;
alert(x);

// foo is considered used here
myFunc(
  function foo() {
    // ...
  }.bind(this),
);

(function (foo) {
  return foo;
})();

var myFunc;
myFunc = setTimeout(function () {
  // myFunc is considered used
  myFunc();
}, 50);

// Only the second argument from the destructured array is used.
function getY([, y]) {
  return y;
}
```

Examples of **incorrect** code for `/* exported variableName */` operation:

```javascript
/* exported global_var */

// Not respected, use ES6 modules instead.
var global_var = 42;
```