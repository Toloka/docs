# Overview

Quality control rules help regulate access to a project or pool: you can filter out Tolokers who give incorrect responses in control tasks, skip too many tasks in a row, respond too fast, and so on.

A rule consists of two parts: the condition ("If"), and the action to perform when the condition is met ("then"). If there are multiple conditions, they are combined using AND.

To define quality control rules, add an array of `quality_control.configs` JSON objects to the pool.

## Quality control rules {#quality-control-blocks}

- [Control tasks](./goldenset.md)
- [Majority vote](./mv.md)
- [Entering captchas](./captcha.md)
- [Compensation amount](./earn_limit.md)
- [Skipped assignments](./skipped.md)
- [Submitted assignments](./completed.md)
- [Fast responses](./fast.md)
- [Rejected tasks](./accept_ban.md)
- [Processing rejected and accepted assignments](./reassessment.md)
- [Recompletion of assignments](./restore-task-overlap.md)

## Learn more {#links}

- [Quality control rules in the Requester's guide](https://toloka.ai/docs/guide/check-performers.html)