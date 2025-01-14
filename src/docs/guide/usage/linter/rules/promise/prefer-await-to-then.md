<!-- This file is auto-generated by tasks/website/src/linter/rules/doc_page.rs. Do not edit it manually. -->

# promise/prefer-await-to-then <Badge type="info" text="Style" />

<div class="rule-meta">
</div>

### What it does

Prefer `await` to `then()`/`catch()`/`finally()` for reading Promise values

### Why is this bad?

Async/await syntax can be seen as more readable.

### Examples

Examples of **incorrect** code for this rule:

```javascript
function foo() {
  hey.then((x) => {});
}
```

Examples of **correct** code for this rule:

```javascript
async function hi() {
  await thing();
}
```

## References

- [Rule Source](https://github.com/oxc-project/oxc/blob/2b14a6fb5403dfe5eff8dfade3baf7725b837052/crates/oxc_linter/src/rules/promise/prefer_await_to_then.rs)
