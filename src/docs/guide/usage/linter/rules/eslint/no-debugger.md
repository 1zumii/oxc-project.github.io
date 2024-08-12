<!-- This file is auto-generated by tasks/website/src/linter/rules/doc_page.rs. Do not edit it manually. -->

# eslint/no-debugger <Badge type="info" text="Correctness" />

<div class="rule-meta">
<Alert class="default-on" type="success">
<span class="emoji">✅</span> This rule is turned on by default.
</Alert>
<Alert class="fix" type="info">
<span class="emoji">🛠️</span> An auto-fix is available for this rule.
</Alert>
</div>

### What it does

Checks for usage of the `debugger` statement

### Why is this bad?

`debugger` statements do not affect functionality when a debugger isn't attached.
They're most commonly an accidental debugging leftover.

### Example

```javascript
async function main() {
  const data = await getData();
  const result = complexCalculation(data);
  debugger;
}
```