<!-- This file is auto-generated by tasks/website/src/linter/rules/doc_page.rs. Do not edit it manually. -->

# eslint/eqeqeq <Badge type="info" text="Pedantic" />

<div class="rule-meta">
<Alert class="fix" type="info">
<span class="emoji">🛠️</span> An auto-fix is available for this rule for some violations.
</Alert>
</div>

### What it does

Requires the use of the === and !== operators

### Why is this bad?

Using non-strict equality operators leads to hard to track bugs due to type coercion.

### Example

```javascript
let a = [];
let b = false;
a == b;
```

## References

- [Rule Source](https://github.com/oxc-project/oxc/blob/2b14a6fb5403dfe5eff8dfade3baf7725b837052/crates/oxc_linter/src/rules/eslint/eqeqeq.rs)
