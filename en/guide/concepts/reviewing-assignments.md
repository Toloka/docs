# Results of manual review

If you don't want Tolokers who made a lot of mistakes to do your [tasks](../../glossary.md#task) in the future, set up this quality control rule.

## When to use {#when-use}

If [manual review](offline-accept.md) is set in the [pool](../../glossary.md#pool), add a rule to:

- Set the Toloker's [skill](../../glossary.md#skill) based on their responses.

- Block access for Tolokers who give incorrect responses.

To have rejected tasks redistributed to other Tolokers, set up the [Recompletion of rejected assignments](reassessment-after-accepting.md) rule.

## How to configure {#rule}

{% note warning %}

The **If** and **then** fields in this rule are required. If you don't fill in at least one field, you won't be able to save the rule.

{% endnote %}

#|
||**Field** | **Overview**||
||**Recent tasks to use** | How many recent responses from the Toloker to use.

If this field is not filled in, the calculation includes only responses from the pool to which the rule is applied.

If the field is filled in, the corresponding number of responses is used. The rule takes into account responses from both the current pool and other pools where this field is filled in.

[Learn more](remember-values.md) about how this field works.||
||**If** | A condition for performing the action in the **then** field:

- **total reviewed task suite responses** — The number of the Toloker's assignments that were reviewed.

- **accepted task suite responses (%)** — The percentage of the Toloker's assignments that were accepted (from 0 to 100).

- **rejected task suite responses (%)** — The percentage of the Toloker's assignments that were rejected (from 0 to 100).

To add multiple conditions, click ![](../_images/add.svg).||
||**then** | Action to perform for the **If** condition:

- **accept all assignments from this Toloker in the pool** — Requires the [manual review](offline-accept.md) option to be set.

    Useful if the Toloker completes most tasks well. Example: The Toloker completed more than 80% of the tasks correctly and you are satisfied with this result. The rule will work automatically and accept all task suite responses from this Toloker in the pool.

- **assign skill from the field** — Save the percentage of Toloker's accepted task suite responses as the [skill](nav.md) value.

- **ban** — Block access to the project or all of the requester's projects for the specified number of days. Only the requester can view the reason.

- **assign skill value** — Assign a fixed value to the [skill](nav.md).

- **suspend** — Suspend the Toloker's access to the pool for the specified number of days. Only the requester can view the reason.

    If access to tasks is blocked temporarily (for example, for 7 days), the history of the Toloker's task suite responses is not saved after the ban is lifted. The skill value is based on new task suite responses.||
|#

## Examples {#examples}

You understand that the Toloker didn't complete your tasks well enough. You can block this Toloker's access to tasks that you're going to do yourself.

You can also assign a skill that you can use to either block access to tasks for Tolokers, or to encourage those who did tasks well.

### Blocking for incorrect responses

{% note warning %}

The assignments submitted by banned Tolokers will be taken into account if they are not rejected using manual review. They can be reassigned by setting up the [Recompletion of assignments from banned users](restore-task-overlap.md) rule.

{% endnote %}

{% list tabs %}

- Correct settings

  ![](../_images/control-rules/reviewing-assignments/qcr-reviewing-assignments_example1.png =700x)

  If more than 50% of Toloker's responses are rejected, the Toloker is blocked and can't complete your tasks for 15 days.

- Incorrect settings

  ![](../_images/control-rules/reviewing-assignments/qcr-reviewing-assignments_example_1.png =700x)

  The Toloker is blocked after the first rejected response, because the number of the reviewed tasks is not specified.

{% endlist %}

### Setting the skill

![](../_images/control-rules/reviewing-assignments/qcr-reviewing-assignments_example2.png =700x)

After 3 tasks are reviewed, the skill is set to the percentage of correct responses. Use the skill value to set access to other pools with [filters](filters.md).

{% cut "Example of filter settings" %}

![](../_images/other/qcr-control_example_filter.png =700x)

{% endcut %}

## For developers {#for-developers}

- [Toloka API: Processing rejected and accepted assignments](../../api/concepts/reassessment.md)
- [Toloka-Kit: AssignmentsAssessment collector class](../../toloka-kit/reference/toloka.client.collectors.AssignmentsAssessment.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [faq-disable-tasks](../_includes/faq/result-questions/disable-tasks.md) %}

{% include [faq-redo-task](../_includes/faq/users/redo-task.md) %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}