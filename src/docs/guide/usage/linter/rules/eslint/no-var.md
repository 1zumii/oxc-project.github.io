<!-- This file is auto-generated by tasks/website/src/linter/rules/doc_page.rs. Do not edit it manually. -->

# eslint/no-var <Badge type="info" text="Restriction" />

<div class="rule-meta">
<Alert class="fix" type="info">
<span class="emoji">🛠️</span> An auto-fix is available for this rule.
</Alert>
</div>

### What it does

ECMAScript 6 allows programmers to create variables with block scope
instead of function scope using the `let` and `const` keywords. Block
scope is common in many other programming languages and helps
programmers avoid mistakes.

### Why is this bad?

Using `var` in an es6 environment triggers this error

### Example

```javascript
// error
var x = "y";
var CONFIG = {};

// success
let x = "y";
const CONFIG = {};
```

## References

- [Rule Source](https://github.com/oxc-project/oxc/blob/2b14a6fb5403dfe5eff8dfade3baf7725b837052/crates/oxc_linter/src/rules/eslint/no_var.rs)
