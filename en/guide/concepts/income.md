# Earnings

If you want to have a large number of Tolokers in a project, limit the daily earnings in the [project](../../glossary.md#project).

Ban by earnings works for the [pool](../../glossary.md#pool). If you set up a blocking rule for the project, the earnings are calculated separately for each pool.

{% cut "Example" %}

The project has a rule set up that bans the Toloker if their earnings exceed $5 in the last 24 hours. If the Toloker earns more than $5 in one of the pools, they can no longer access this pool. If they earn $2 in each of three project pools, they won't be banned.

{% endcut %}

## When to use {#when-use}

Limit the Toloker's daily earnings in the pool if you want to:

- Get responses from as many Tolokers as possible. For this purpose, you might want to set the maximum amount of earnings equal to the price for a single [task suite](../../glossary.md#task-suite).

- Provide protection from robots. For this purpose, set maximum earnings to a higher amount, like 10% of the entire pool cost.

{% note info %}

Set an amount that Tolokers can realistically earn in a day, otherwise the rule will be pointless.

{% endnote %}

## How to configure {#rule}

{% note alert %}

All fields in this rule are required. If you don't fill in at least one of them, you won't be able to save the rule.

{% endnote %}

#|
|| **Field** | **Overview** ||
||**If** | A condition for performing the action in the **then** field:

- **earned in last 24 hours** — The Toloker's earnings for [completed tasks](../../glossary.md#completed-tasks) in the pool over the last 24 hours.||
||**then** | Action to perform for the condition:

- **assign skill value** — Assign a fixed value to the [skill](nav.md).

- **suspend** — Suspend the Toloker's access to the pool for the specified number of days. Only the requester can view the reason.

- **accept all assignments from this Toloker in the pool** — Requires the [manual review](offline-accept.md) option to be set.

    Useful if the Toloker completes most tasks well. Example: The Toloker completed more than 80% of the tasks correctly and you are satisfied with this result. The rule will work automatically and accept all responses in the pool.

- **ban** — Block access to the project or all of the requester's projects for the specified number of days. Only the requester can view the reason.

    If access to tasks is blocked temporarily (for example, for 7 days), the history of the Toloker's responses is not saved after the ban is lifted. The skill value is based on new responses.||
|#

{% note warning %}

The assignments submitted by banned Tolokers will be taken into account if they are not rejected using manual review. They can be reassigned by setting up the [Recompletion of assignments from banned users](restore-task-overlap.md) rule.

{% endnote %}

## Examples {#examples}

**Task**: you're conducting a sociological survey. To collect responses from as many Tolokers as possible, set up the **earnings** rule.

![](../_images/control-rules/income/qcr-income_example1.png)

If the Toloker's earnings exceed 5 dollars in the last 24 hours, they lose access to the pool and can't complete your tasks.

## See also {#see-also}

- [{#T}](qa-pool-settings.md)

## For developers {#for-developers}

- [Toloka API: Compensation amount](../../api/concepts/earn_limit.md)
- [Toloka-Kit: Income collector class](../../toloka-kit/reference/toloka.client.collectors.Income.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [contact-support](../_includes/contact-support.md) %}