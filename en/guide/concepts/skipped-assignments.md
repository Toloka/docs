# Skipped assignments

Restrict access to [pool](../../glossary.md#pool) tasks for Tolokers who skip multiple [task suites](../../glossary.md#task-suite) in a row.

Tolokers can [skip task suites](pool_statistic-pool.md#skipped-tasks) that seem too large or complex and choose easier tasks. They get paid in the same way. For example, the Toloker is evaluating medical articles for whether they contain prescriptions, dosage, and mentions of specific medications. They might decide to skip long texts and label only short ones that take 10–20 seconds to read.

You can set up this rule to restrict Toloker access to a pool.

Before you enable skipping tasks, we recommend that you read the section [Tips for designing tasks](faq.md).

## When to use {#when-use}

Restrict access to [pool](../../glossary.md#pool) tasks for Tolokers who skip multiple task suites in a row if:

- Tasks are different in volume and Tolokers might skip large tasks in order to only perform short ones;

- Tasks must be performed in order and skipping tasks may affect the quality.

Don't use it if:

- There aren't very many tasks in the pools. For example, if a task is a survey on a single page and the Toloker skips this page, they will no longer be able to perform tasks in the pool, which means there is no need to ban them.

- Tasks are the same in volume.

- The task complexity can't be estimated, which means the Tolokers won't be willing to skip tasks in search of easier ones.

## How to configure {#rule}

{% note alert %}

All fields in this rule are required. If you don't fill in at least one of them, you won't be able to save the rule.

{% endnote %}

#|
||**Field** | **Overview**||
||**If** | A condition for performing the action in the **then** field:

- **task suites skipped in a row** — The number of task suites skipped in a row.||
||**then** | Action to perform for the **If** condition:

- **ban** — Block access to the project or all of the requester's projects for the specified number of days. Only the requester can view the reason.

    If access to tasks is blocked temporarily (for example, for 7 days), the history of the Toloker's task suite responses is not saved after the ban is lifted. The skill value is based on new task suite responses.

- **accept user's answers** — Requires the [manual review](offline-accept.md) option to be set.

    Useful if the Toloker completes most tasks well. Example: The Toloker completed more than 80% of the tasks correctly and you are satisfied with this result. The rule will work automatically and accept all task suite responses in the pool.

- **suspend** — Suspend the Toloker's access to the pool for the specified number of days. Only the requester can view the reason.

- **assign skill value** — Assign a fixed value to the [skill](nav.md).||
|#

## Examples {#examples}

Task: you're conducting an opinion poll. For the results to be accurate, the Toloker must answer most of the questions.

{% list tabs %}

- Correct settings

  ![](../_images/control-rules/skipped-assignments/qcr-skipped_assignments_example1.png =700x)

  A Toloker who skips 2 task suites in a row is restricted from accessing the pool and can't complete your tasks for 5 days.

- Incorrect settings

  ![](../_images/control-rules/skipped-assignments/qcr-skipped_assignments_example3.png =700x)

  If a Toloker skips 2 task suites in a row, all their task suite responses will be accepted automatically.

  ![](../_images/control-rules/skipped-assignments/qcr-skipped_assignments_example4.png =700x)

  With this setting, a Toloker who skips less than 2 task suites in a row is restricted from accessing the pool and can't complete your tasks for 5 days.

{% endlist %}

{% note alert %}

The assignments submitted by banned Tolokers will be taken into account if they are not rejected using manual review. They can be reassigned by setting up the [Recompletion of assignments from banned users](restore-task-overlap.md) rule.

{% endnote %}

## For developers {#for-developers}

- [Toloka API: Skipped assignments](../../api/concepts/skipped.md)
- [Toloka-Kit: SkippedInRowAssignments collector class](../../toloka-kit/reference/toloka.client.collectors.SkippedInRowAssignments.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [faq-submit-empty-assignments](../_includes/faq/pool-setup/submit-empty-assignments.md) %}

{% include [faq-incorrect-responses](../_includes/faq/pool-setup/incorrect-responses.md) %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}