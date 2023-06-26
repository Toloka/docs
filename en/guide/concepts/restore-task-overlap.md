# Recompletion of assignments from banned users

Use this rule if the Toloker was banned and you want someone else to complete their tasks.

{% note info %}

Don't use this rule in [pools](../../glossary.md#pool) with [dynamic overlap](dynamic-overlap.md). This increases the maximum [overlap](../../glossary.md#overlap) value.

{% endnote %}

## When to use {#when-use}

{% note alert %}

This rule can increase the cost of the pool.

{% endnote %}

Use the rule if you want to get responses only from honest Tolokers to each task in the given overlap.

The assignments submitted by banned Tolokers will be taken into account if they are not rejected manually using [manual review](../../glossary.md#assignment-review). They can be reassigned by setting up the corresponding rule.

To download the responses of users who are not blocked:

1. On the pool page, click **Download results** on the right.
1. Click **Additional options**.
1. Turn off the **Include responses from banned Tolokers** option.
1. Click **Download**.

![](../_images/control-rules/restore-task-overlap/good-results.png =700x)

Don't use it if:

- You don't want to increase the overlap for tasks.
- You don't want the final budget for pool labeling to exceed the initial budget.
- You set up [dynamic overlap](dynamic-overlap.md). This increases the maximum overlap value.

## How to configure {#rule}

{% note alert %}

All fields in this rule are required. If you don't fill in at least one of them, you won't be able to save the rule.

{% endnote %}

#|
||**Field** | **Overview**||
||**If** | A condition for performing the action in the **then** field:

- **Toloker banned** — The Toloker's access to tasks is blocked by a [quality control rule](../../glossary.md#quality-control-rule) (such as [control tasks](../../glossary.md#control-task), [majority vote](../../glossary.md#majority-vote), [fast responses](../../glossary.md#fast-responses), or [skipping tasks](../../glossary.md#skipping-tasks)).

- **Toloker filtered out** — The Toloker no longer meets one or more [filters](filters.md).

- **skill** — The Toloker no longer meets the specific skill filter.

To add multiple conditions, click ![](../_images/add.svg).||
||**then** | Action performed under the **If** condition:

- **extend overlap by** — Resend the [task suite](../../glossary.md#task-suite) for completion to other Tolokers.

    If you want an assignment to be automatically reassigned even if your pool is already completed and closed, turn on the option **Open pool if closed**.

- **reduce overlap by** — Decrease the number of times a task suite can be completed by Tolokers. For example, use this action to cancel the recompletion of accepted assignments.||
|#

## Examples {#examples}

Task: classify photos for a dataset across different categories. If a Toloker is banned by a quality control rule (for example, [fast resposes](quick-answers.md)) or no longer matches the skill, their responses aren't counted and their tasks are sent for re-completion to another Toloker.

{% list tabs %}

- Correct settings

  ### Resending tasks from a banned Toloker

  ![](../_images/control-rules/restore-task-overlap/qcr-banned_users_reassessment_example_1.png =700x)

  If a Toloker is banned by a quality control rule, their tasks are sent for re-completion to another Toloker.

  ### Resending tasks if the Toloker doesn't meet the skill filter

  ![](../_images/control-rules/restore-task-overlap/qcr-banned_users_reassessment_example_2.png =700x)

  If the Toloker no longer meets the requirements of the skill filter and their responses aren't taken into account, their tasks are sent for re-completion to another Toloker.

- Incorrect settings

  ### Resending tasks from a banned Toloker

  ![](../_images/control-rules/restore-task-overlap/qcr-banned_users_reassessment_example_3.png =700x)

  If a Toloker is banned by a quality control rule, their tasks are not sent for re-completion to another Toloker.

  ### Resending tasks if the Toloker doesn't meet the skill filter

  ![](../_images/control-rules/restore-task-overlap/qcr-banned_users_reassessment_example_4.png =700x)

  If the Toloker no longer meets the requirements of the skill filter and their responses aren't taken into account, their tasks are not sent for re-completion to another Toloker.

{% endlist %}

## For developers {#for-developers}

- [Toloka API: Recompletion of assignments](../../api/concepts/restore-task-overlap.md)
- [Toloka-Kit: UsersAssessment collector class](../../toloka-kit/reference/toloka.client.collectors.UsersAssessment.md)

## Troubleshooting {#troubleshooting}

{% include [faq-overlap](../_includes/faq/pool-setup/overlap.md) %}

{% include [faq-change-overlap](../_includes/faq/pool-setup/change-overlap.md) %}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [faq-output-format](../_includes/faq/pool-setup/output-format.md) %}

{% include [faq-classify-users](../_includes/faq/pool-setup/classify-users.md) %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}