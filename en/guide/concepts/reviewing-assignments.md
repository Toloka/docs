# Results of assignment review

If you don't want Tolokers who made a lot of mistakes to do your tasks in the future, set up this quality control rule.

## When to use {#when-use}

If [non-automatic acceptance](../../glossary.md#pool) (assignment review) is set in the [pool](offline-accept.md), add a rule to:

- Set the Toloker's [skill](../../glossary.md#skill) based on their responses.

- Block access for Tolokers who give incorrect responses.

To have rejected tasks redistributed to other Tolokers, set up the [Recompletion of rejected assignments](reassessment-after-accepting.md) rule.

## How to configure {#rule}

{% note warning %}

The **If** and **then** fields in this rule are mandatory. If you don't fill in at least one field, you won't be able to save the rule.

{% endnote %}

#|
|| **Field** | **Overview** ||
||{% if locale == "en-com" %}**Recent values to use**{% endif %} | How many recent responses from the Toloker to use.

If this field is not filled in, the calculation includes only task responses from the pool to which the rule is applied.

If the field is filled in, the corresponding number of responses is used. The rule takes into account responses from both the current pool and other pools where this field is filled in.

To learn more about how this field works, go to [“Remember values” parameter](remember-values.md).||
||{% if locale == "en-com" %}**If**{% endif %} | A condition for performing the action in the {% if locale == "en-com" %}**then**{% endif %} field:

- {% if locale == "en-com" %}**total reviewed responses**{% endif %} — The number of the Toloker's assignments that were reviewed.

- {% if locale == "en-com" %}**accepted responses (%)**{% endif %} — The percentage of the Toloker's assignments that were accepted (from 0 to 100).

- {% if locale == "en-com" %}**rejected responses (%)**{% endif %} — The percentage of the Toloker's assignments that were rejected (from 0 to 100).

To add multiple conditions, click ![](../_images/add.svg).||
||{% if locale == "en-com" %}**then**{% endif %} | Action to perform for the condition {% if locale == "en-com" %}**If**{% endif %}:

- {% if locale == "en-com" %}**suspend**{% endif %} — Suspend the Toloker's access to the pool for the specified number of days. Only the requester can view the reason.

- {% if locale == "en-com" %}**assign skill value**{% endif %} — Assign a fixed value to the [skill](nav.md).

- {% if locale == "en-com" %}**accept all assignments from this Toloker in the pool**{% endif %} — Requires the [non-automatic acceptance](offline-accept.md) option to be set.

    Useful if the Toloker completes most tasks well. Example: The Toloker completed more than 80% of the tasks correctly and you are satisfied with this result. The rule will work automatically and accept all responses in the pool.

- {% if locale == "en-com" %}**ban**{% endif %} — Block access to the project or all of the requester's projects for the specified number of days. Only the requester can view the reason.

    If access to tasks is blocked temporarily (for example, for 7 days), the history of the Toloker's responses is not saved after the ban is lifted. The skill value is based on new responses.

- {% if locale == "en-com" %}**assign skill from the field**{% endif %} — Save the percentage of Toloker's accepted responses as the [skill](nav.md) value.||
|#

## Examples of rules {#examples}

You understand that the Toloker didn't complete your tasks well enough. You can block this Toloker's access to tasks that you're going to do yourself.

You can also assign a skill that you can use to either block access to tasks for Tolokers, or to encourage those who did tasks well.

#### Blocking for incorrect responses

{% note warning %}

The assignments submitted by banned Tolokers will be taken into account if they are not rejected manually using assignment review They can be reassigned by setting up the [Recompletion of assignments from banned users](restore-task-overlap.md) rule.

{% endnote %}

{% list tabs %}

- Correct settings

  ![](../_images/control-rules/reviewing-assignments/qcr-reviewing-assignments_example1.png)

  If more than 50% of Toloker's responses are rejected, the Toloker is blocked and can't complete your tasks for 15 days.

- Incorrect settings

  ![](../_images/control-rules/reviewing-assignments/qcr-reviewing-assignments_example_1.png)

  The Toloker is blocked after the first rejected response, because the number of the reviewed tasks is not specified.

{% endlist %}

#### Setting the skill

![](../_images/control-rules/reviewing-assignments/qcr-reviewing-assignments_example2.png)

After 3 tasks are reviewed, the skill is set to the percentage of correct responses. Use the skill value to set access to other pools with [filters](filters.md).

{% cut "Example of filter settings" %}

![](../_images/other/qcr-control_example_filter.png)

{% endcut %}

## For developers {#for-developers}

- [Toloka API: Processing rejected and accepted assignments](../../api/concepts/reassessment.md)
- [Toloka-Kit: AssignmentsAssessment collector class](../../toloka-kit/reference/toloka.client.collectors.AssignmentsAssessment.md)

## Troubleshooting {#troubleshooting}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% cut "Can I disable tasks for Tolokers who do a poor job on tasks?" %}

You can deny access to the pool if the Toloker's responses are [too fast](quick-answers.md), if they don't match the [majority vote](mvote.md), or if the Toloker makes too many mistakes in [control tasks](goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](restore-task-overlap.md).

{% endcut %}

{% include [faq-redo-task](../_includes/faq/users/redo-task.md) %}

{% include [contact-support](../_includes/contact-support.md) %}