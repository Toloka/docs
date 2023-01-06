# Control tasks

[Control tasks](../../glossary.md#control-task) contain samples of correct responses. They allow you to monitor the quality of task completion without having to check all the responses. Control tasks simplify the verification process, help identify Tolokers' qualifications, and save your time.

{% note info %}

To save time, you can opt for having your control tasks edited by [Toloka experts](task_markup.md#auto-markup). In this case, markup is performed within the pool.

{% endnote %}

## When to use {#when-use}

Use control tasks to assign a [skill](../../glossary.md#skill) to Tolokers based on their responses and [ban](../../glossary.md#banning-tolokers) Tolokers who submit incorrect responses.

#### Don't use it if:

- You have a lot of response options.
- Tolokers need to attach a file to their assignment.
- Tolokers need to transcribe text.
- Tolokers need to select objects in a photo.
- Tasks don't have a correct or incorrect response. For example: “Which image do you like best?” or “Choose the page design option that you like best”.

## How to configure {#rule-golden}

{% note alert %}

The **If** and **then** fields in this rule are mandatory. If you don't fill in at least one field, you won't be able to save the rule.

{% endnote %}

#|
|| Field | Overview ||
||{% if locale == "en-com" %}**Recent control and training task responses to use**{% endif %} | The number of the Toloker's last responses to control tasks.

If this field is not filled in, the calculation includes only control task responses in the pool to which the rule applies.

If the field is filled in, the corresponding number of control task responses is used. The rule takes into account responses from both the current pool and other pools where this field is filled in.

[Learn more](remember-values.md) about how this field works.||
||{% if locale == "en-com" %}**If**{% endif %} | A condition for performing the action in the {% if locale == "en-com" %}**then**{% endif %} field:

- {% if locale == "en-com" %}**number of responses**{% endif %} — The number of completed control and [training](../../glossary.md#training-task) tasks.

- {% if locale == "en-com" %}**correct responses (%)**{% endif %} — The percentage of correct responses in training and control tasks (from 0 to 100).

- {% if locale == "en-com" %}**incorrect responses (%)**{% endif %} — The percentage of incorrect responses in training and control tasks (from 0 to 100).

- {% if locale == "en-com" %}**number of control responses**{% endif %} — The number of completed control tasks.

- {% if locale == "en-com" %}**correct control responses (%)**{% endif %} — The percentage of correct responses in control tasks (from 0 to 100).

- {% if locale == "en-com" %}**incorrect control responses (%)**{% endif %} — The percentage of incorrect responses in control tasks (from 0 to 100).

To add multiple conditions, click ![](../_images/add.svg).||
||{% if locale == "en-com" %}**then**{% endif %} | Action to perform for the condition:

- {% if locale == "en-com" %}**assign skill from the field**{% endif %} — Save the percentage of the Toloker's correct responses in control tasks as a skill value.

- {% if locale == "en-com" %}**assign skill value**{% endif %} — Assign a fixed value to the Toloker's [skill](nav.md).

- {% if locale == "en-com" %}**accept all assignments from this Toloker in the pool**{% endif %} — Requires the [non-automatic acceptance](offline-accept.md) option to be set.

    Useful if the Toloker completes most tasks well. Example: The Toloker completed more than 80% of the tasks correctly and you're satisfied with this result. The rule will work automatically and accept all responses in the pool.

- {% if locale == "en-com" %}**suspend**{% endif %} — Suspend the Toloker's access to the pool for the specified number of days. Only the requester can view the reason.

- {% if locale == "en-com" %}**ban**{% endif %} — Block access to the project or all of the requester's projects for the specified number of days. Only the requester can view the reason.

    If access to tasks is blocked temporarily (for example, for 7 days), the history of the Toloker's responses is not saved after the ban is lifted. The skill level is calculated based on the new responses.||
|#

## Examples of rules {#examples}

**Purpose**: filter out Tolokers who often make mistakes.

Solutions:

- [Ban Tolokers based on control tasks and the percentage of correct responses](goldenset.md#qcr-control_example1)

- [Set a skill and deny access to Tolokers with a low skill level](goldenset.md#nav)

- [Ban Tolokers if their percentage of correct responses to control tasks is less than 40%](goldenset.md#qcr-control_example3)

{% note warning %}

The assignments submitted by banned Tolokers will be taken into account if you don't reject them manually using assignment review They can be reassigned by setting up the [Recompletion of assignments from banned users](restore-task-overlap.md) rule.

{% endnote %}

#### Ban Tolokers based on control tasks and the percentage of correct responses

{% list tabs %}

- Correct settings

  ![](../_images/control-rules/control-tasks/qcr-control_example1_1.png =700x)

  ![](../_images/control-rules/control-tasks/qcr-control_example1_2.png =700x)

  Both rules work independently:

  1. If the Toloker gives at least 3 responses to the control tasks, the percentage of correct answers is assigned as the skill value. This is useful if you want to prevent Tolokers with a low skill level from completing your tasks.

  1. If the Toloker gives at least 3 responses to the control tasks and the percentage of correct answers is less than 60%, they lose access to the project.

  The calculation uses up to 10 of the Toloker's recent responses to the project's control tasks.

- Incorrect settings

  ![](../_images/control-rules/control-tasks/qcr-control_example-1_1.png =700x)

  ![](../_images/control-rules/control-tasks/qcr-control_example-1_2.png =700x)

  The Toloker is banned after the first incorrect response to the first, second or third control task. The skill is not assigned. Since the ban reason is not specified, there is no way to find out why the Toloker is banned.

- Alternative settings

  ![](../_images/control-rules/control-tasks/qcr-control_example2a_1.png =700x)

  ![](../_images/control-rules/control-tasks/qcr-control_example2a_2.png =700x)

  ![](../_images/control-rules/control-tasks/qcr-control_example2a_3.png =700x)

  ![](../_images/control-rules/control-tasks/qcr-control_example2a_4.png =700x)

  All rules are applied independently:

  1. If the Toloker gives at least 3 responses to the control and training tasks, the percentage of correct answers is assigned as the skill value.

  1. If the Toloker gives 2 incorrect answers to 3 control tasks, they lose access to the pool for 10 days.

  1. If the Toloker gives 2 incorrect responses to 4 control tasks, they lose access to the pool for 10 days.

  1. If the Toloker gives 5 or more responses to the control tasks and the percentage of correct responses is less than 80%, they lose access to the pool for 10 days.

   A set of rules like this prevents Tolokers from being banned for one incorrect response and lets you maintain high accuracy.

{% endlist %}

#### Set a skill and deny access to Tolokers with a low skill level

Skills help identify how well Tolokers do your tasks. You can ban Tolokers with low skill levels from completing tasks in your pool or project.

{% list tabs %}

- Correct settings

  ![](../_images/control-rules/control-tasks/qcr-control_example2.png =700x)

  If the Toloker completes 3 control or training tasks, they get a skill. Use the skill value to set access to other pools with [filters](filters.md).

  {% cut "Example of filter settings" %}

  ![](../_images/other/qcr-control_example_filter.png)

  {% endcut %}

- Incorrect settings

  ![](../_images/control-rules/control-tasks/qcr-control_example-2.png =700x)

  This rule will never take effect because the number of responses counted ({% if locale == "en-com" %}**Recent control and training task responses to use**{% endif %}) is less than the number of responses in the rule ({% if locale == "en-com" %}**number of control responses**{% endif %}).

{% endlist %}

#### Ban Tolokers if their percentage of correct responses to control tasks is less than 40%

{% list tabs %}

- Correct settings

  ![](../_images/control-rules/control-tasks/qcr-control_example3.png =700x)

  If the percentage of correct responses in the control tasks is less than 40%, the Toloker loses access to the project for 30 days.

  This rule doesn't take into account responses in the training tasks for banning.

- Incorrect settings

  ![](../_images/control-rules/control-tasks/qcr-control_example-3.png =700x)

  If the percentage of correct responses in the control tasks is less than 40%, the Toloker loses access to the project for 30 days. The rule will be applied once — after the fifth response in the control task.

{% endlist %}

## See also {#see-also}

- [{#T}](qa-pool-settings.md)
- [{#T}](remember-values.md)

## For developers {#for-developers}

- [Toloka API: Control tasks](../../api/concepts/goldenset.md)
- [Toloka-Kit: Control and training task statistics collector](../../toloka-kit/reference/toloka.client.collectors.GoldenSet.md)

## Troubleshooting {#troubleshooting}

{% cut "How many control tasks do I need to add?" %}

We recommend adding at least 1% of control tasks in the pool. And for small pools — 5–10%.

{% cut "Why's that?" %}

Each control task is shown to the Toloker only once. If you use smart mixing, you determine how many control tasks should be in a suite. If each suite contains one control task, then the maximum number of suites that the Toloker can complete is equal to the number of control tasks in the pool. If you increase the number of control tasks in a suite, the number of suites available to the Toloker decreases by the same degree.

There shouldn't be too few pages available. Otherwise:

- You won't be able to correctly evaluate the quality of the Toloker's responses.
- The Toloker won't be interested in completing such tasks because they'll spend a lot of time studying instructions but won't earn much.

{% cut "Example" %}

#### A large pool with 1% of control tasks (good)

There are 10,000 tasks in the pool, and 100 of them are control tasks (1%). Each suite contains 10 tasks, and 1 of them is a control task. This means a Toloker can complete up to 100 suites.

#### A small pool with 1% control tasks (bad)

There are 100 tasks in the pool, and 1 of them is a control task (1%). Each suite contains 10 tasks, and 1 of them is a control task. This means each Toloker can only complete 1 suite.

#### A small pool with 10% control tasks (good)

There are 100 tasks in the pool, and 10 of them are control tasks (10%). Each suite contains 10 tasks, and 1 of them is a control task. This means a Toloker can complete up to 10 suites.

{% endcut %}

{% endcut %}

If there are few control tasks in the open pool, [add new control tasks](../troubleshooting/pool-setup.md#add-gs).

{% cut "What for" %}

In a large pool with few control tasks, there might be a situation when a Toloker who has completed a lot of tasks in the project stops getting new task suites. This happens when the Toloker completes all control tasks in the pool.

{% note info %}

To filter out Tolokers, use the [Control tasks](control.md) quality control rule. To rank Tolokers by the quality of responses in control tasks, use a [skill](nav.md).

{% endnote %}

{% endcut %}

{% endcut %}

{% cut "How are the correct responses to control questions counted?" %}

The Control tasks rule starts working after the Toloker completes the number of control tasks you specified. If your pool contains both [training](../../glossary.md#training-task) and control tasks, you can take into account the responses in both of them (the **Number of responses** parameter) or only in control tasks (the **Number of control responses** parameter).

As soon as the needed number of responses is collected, Toloka calculates the percentage of correct and incorrect responses and performs an action (assigns a skill, or blocks the Toloker in the pool or in the project). Then this percentage is updated as the tasks are completed by the Toloker. The number of the Toloker's recent responses that's used in the calculation is set in the **Recent control and training task responses to use** field. If you leave it empty, all the responses from the Toloker in the pool are counted.

{% endcut %}

{% cut "Should I create a skill for every pool?" %}

It is better to use one [skill](../../glossary.md#skill) in a project. You can choose the way to calculate the skill:

- Calculate the skill for each pool separately. The current skill value is the value of the skill in the pool the Toloker completed last. This option is convenient if:

    - The pools are intended for different groups of Tolokers (for example, there are filters by city or country).

    - Pools are started one by one and you don't want to take into account the responses in the previous pools to calculate the skill in the current pool.

    This calculation method is used by default when adding a quality control rule to a pool. For the control tasks block, leave the **Recent control and training task responses to use** field empty.

- Calculate skill based on all tasks in a project This option is good if the pools are small and you don't need to have skill calculated for each pool.

    This option is available only for skills on control tasks. To use it, fill in the **Recent control and training task responses to use** field in pool quality control rules.

{% endcut %}

{% cut "Can I use a skill beyond a particular pool or project and apply it to other projects as well?" %}

Yes, of course — you can use the same skill for different projects. But most often, a skill is intended for a specific project. If the Toloker completes a certain task well, this doesn't mean that they will complete other ones successfully. Another disadvantage is that if you filter by skills that were set long ago, you will artificially limit the number of available Tolokers.

{% endcut %}

{% include [faq-move-control-tasks](../_includes/faq/sandbox/move-control-tasks.md) %}

{% cut "If a cheating Toloker gives a lot of incorrect responses, and the system eventually bans them for errors in control tasks, do I have to pay for the bad responses anyway?" %}

If the Toloker already got paid for the tasks, you can't get your money back.

{% endcut %}

{% cut "When I export a project from the Sandbox, the task files are not exported. Is this how it's supposed to work? I suddenly lost the markup of the control tasks that I created in the sandbox." %}

The tasks themselves are not exported, only the project configuration and the settings of the selected pool. However, you can download your marked up tasks from the **Sandbox** pool and import them to the pool you created. To download the control tasks only (if you marked them up in the interface), go to **Mark up**, then click **Control tasks** and **Download**.

{% endcut %}

{% include [faq-using-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/using-smart-mixing.md) %}

{% include [contact-support](../_includes/contact-support.md) %}