<!-- This file is auto-generated by tasks/website/src/linter/rules/doc_page.rs. Do not edit it manually. -->

# jsx_a11y/no-access-key <Badge type="info" text="Correctness" />

<div class="rule-meta">
</div>

### What it does

Enforces that the `accessKey` prop is not used on any element to avoid complications with keyboard commands used by a screenreader.

### Why is this bad?

Access keys are HTML attributes that allow web developers to assign keyboard shortcuts to elements.
Inconsistencies between keyboard shortcuts and keyboard commands used by screenreaders and keyboard-only users create accessibility complications so to avoid complications, access keys should not be used.

### Example

```jsx
// Bad
<div accessKey="h" />

// Good
<div />
```