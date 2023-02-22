# Processing rejected and accepted assignments

You can enable the [manual review](offline-accept.md) option to [reject or accept](accept.md) assignments that Tolokers completed. Assignments are rejected and accepted on a page-by-page basis.

{% note info %}

Once the review period in the **Review period in days** field runs out, tasks are accepted automatically.

{% endnote %}

## When to use {#when-use}

This rule is helpful when you need to:
- Resend rejected assignments for re-completion to other Tolokers.

    If you rejected an assignment, you may want it to be completed by another Toloker instead of the one whose response you rejected. To do this, you can increase the [overlap](../../glossary.md#overlap) for this assignment only. This is especially helpful if you have the overlap value set to 1.

- Save money on re-completing assignments that you have already accepted.

    If you've reviewed and accepted a task, it may not make sense for other Tolokers to also complete it. To avoid this, you can reduce the overlap for accepted assignments only.

## Rule settings {#rule}

{% note warning %}

All fields in this rule are required. If you don't fill in at least one of them, you won't be able to save the rule.

{% endnote %}

#|
|| **Field**  | **Overview**||
||**If** | A condition for performing the action in the **then** field:

- **submitted assignments** — The number of [task suites](../../glossary.md#task-suite) that are completed and awaiting review.

- **approved assignments** — The number of task suites accepted after the review.

- **rejected assignments** — The number of task suites rejected after the review.

- **assignment becomes approved** — The task suite was accepted after the review.

- **assignment becomes approved after rejection** — The task suite was first rejected, but then accepted after the review.

    {% note info %}

    Note that you can't change the task status if the task [pool](../../glossary.md#pool) was [archived](pool-archive.md).

    {% endnote %}

- **assignment becomes rejected** — The task suite was rejected after the review.

To add multiple conditions, click ![](../_images/add.svg).||
||**then** | Action to perform for the condition:

- **extend overlap by** — Resend the [task suite](../../glossary.md#task-suite) for completion to other Tolokers.

    If you want an assignment to be automatically reassigned even if your pool is already completed and closed, turn on the option **Open pool if closed**.

- **reduce overlap by** — Decrease the number of times a task suite can be completed by Tolokers. For example, use this action to cancel the recompletion of accepted assignments.||
|#

## Rule example {#examples}

The task is to send rejected and recompleted assignments for review. Or assign them to new Tolokers after rejection.

{% list tabs %}

- Correct settings

  ![](../_images/control-rules/reassessment-after-accepting/qcr-reassessment-after-accepting_example1.png)

  A Toloker's assignments rejected after the review are sent to another Toloker for recompletion.

- Incorrect settings

  ![](../_images/control-rules/reassessment-after-accepting/qcr-reassessment-after-accepting_example_2.png)

  A Toloker's assignments rejected after the review are not sent to another Toloker for recompletion.

{% endlist %}

## For developers {#for-developers}

- [Toloka API: Processing rejected and accepted assignments](../../api/concepts/reassessment.md)

## Frequently asked questions {#troubleshooting}

{% include [faq-overlap](../_includes/faq/pool-setup/overlap.md) %}

{% include [faq-change-overlap](../_includes/faq/pool-setup/change-overlap.md) %}

{% include [contact-support](../_includes/contact-support.md) %}