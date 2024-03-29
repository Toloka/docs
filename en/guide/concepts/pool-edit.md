# Editing a pool

You can edit a pool which doesn't have the **Archived** status. While editing, an open pool switches to the “CLOSED_FOR_UPDATE” status. For example, this way you can change the payout amount in a running pool.

{% note info %}

The cost of a task is registered at the moment when a Toloker accepts it. If the cost changes during task completion, the Toloker will receive the amount that was specified before editing the cost.

{% endnote %}

To edit the pool parameters, click ![](../_images/other/project-edit-b.svg) at the top of the pool page or ![](../_images/edit.svg) in the list of pools on the [project](../../glossary.md#project) page.

![](../_images/other/pool-settings.png)

## General information {#pool-general-info}

### Pool type

{% include [toloka-requester-pool-type](../_includes/toloka-requester-source/id-toloka-requester-source/pool-type.md) %}

### Pool name

{% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

### Pool description

{% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

{% cut "Alternative way to edit pool information" %}

To edit pool information:

1. Click ![](../_images/other/project-edit-b.svg) near the pool name.

1. {% include [toloka-requester-pool-type](../_includes/toloka-requester-source/id-toloka-requester-source/pool-type.md) %}

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Save**.

{% endcut %}

## Price {#pool-price-info}

### Price per task suite, $

Payment per [task suite](../../glossary.md#task-suite) in US dollars. For cents, use the dot (".") as a separator. If the **Pool type** is **General tasks**, the minimum price per task suite is $0.005. For other pool types, you can set the price to zero. To learn more about price management, go to [Setting up pricing](dynamic-pricing.md).

### Toloker interest at this price

Calculated automatically. Shows how the price meets Tolokers' expectations.

### Number of tasks per suite

Calculated automatically. Shows the number of tasks per suite recommended for this type of project.

### Overlap

The number of Tolokers who should complete each task in the pool.

Configure this parameter if you need several people to complete your task. Overlap is necessary in tasks for collecting photo datasets, recording audio, or conducting surveys. In other types of tasks, it can improve the quality of results.

To save money, you can set up [dynamic overlap](../../glossary.md#dynamic-overlap) (also known as incremental relabeling or IRL).

Dynamic overlap will help you save money. [Learn more](dynamic-overlap.md).

### Task price

Calculated automatically.

## Audience {#pool-audience-info}

### Adult content

Whether the tasks have some content which can be marked as adult, including shocking or pornographic content. Tasks with such content are only given to Tolokers who agree to complete these types of tasks.

If you aren't sure whether the tasks have such content, enable the **My tasks may contain shocking or pornographic content** option.

### Filters and skills

{% include [toloka-requester-source-filters-desc](../_includes/toloka-requester-source/id-toloka-requester-source/filters-desc.md) %}

### Speed/quality balance

A [setting](adjust.md) for choosing Tolokers for your tasks. You can set the percentage or number of top-rated Tolokers.

When there are many Tolokers, you can get results quickly, but the quality of the Tolokers' responses may be poor. Find a balance that meets your needs. [Learn more](adjust.md).

## Quality control {#pool-quality-control-info}

### Review responses manually

Turn on this option to [review](accept.md) the [completed tasks](../../glossary.md#completed-tasks) manually.

Set the time period when you can check the tasks and reject them if the results are poor.

Learn more about the [manual review](offline-accept.md) and [reviewing Tolokers' responses](accept.md).

### Review period in days

The number of days for reviewing and accepting tasks (max: 21). The Toloker will see the deadline for checking the tasks:

- In the task information on the Toloka main page.

- In the history of completed tasks.

### Quality control rules

You can add other quality control rules by clicking **Add a quality control rule**. You can select ready-made sets of rules or set the rules you need manually. [Learn more](control.md).

{% cut "Optional" %}

### Fast responses

Restricting access for Tolokers who respond too quickly. Specify the minimum time required for completing a task suite (in seconds) and set the condition.

For example: if the number of responses is > 5 and the number of quick responses is > 3, then ban the Toloker on the project for 5 days. [Learn more](quick-answers.md).

### Majority vote

Evaluate Tolokers' [task responses](../../glossary.md#task-response) by comparing them with the majority vote: reward Tolokers who give correct responses and block those who often make mistakes.

In the **Accept as majority** field, specify the number of matching task responses that is considered the majority vote and set the condition. The rule takes effect when the number of responses for the task is equal to the overlap.

For example: if the number of responses is > 5 and the percentage of correct responses is < 60, then ban the Toloker on the project for 10 days.

### Training

This field is only available if you have training pools in the project.

[Training pool](../../glossary.md#training-pool) that will be linked to the main one.

### Level required

This box is only available if you filled in the **Training** box.

Percentage of correct responses in training tasks (from 5 to 100) required to be admitted to the pool tasks. The calculation is based on the first response the Toloker gave in each task.

The minimum required level that you can set is 5. Tolokers who complete training with apercentage below this level won't have access to tasks.

{% endcut %}

## Smart mixing

{% note info %}

When editing a pool, the **Smart mixing** section is available only if you have already uploaded tasks to the pool using [smart mixing](../../glossary.md#smart-mixing).

{% endnote %}

### General tasks

The number of general tasks per suite.

### Control tasks

The number of control tasks per suite.

### Training tasks

The number of training tasks per suite.

### Min general tasks

The minimum number of general tasks per suite.

### Min control tasks

The minimum number of control tasks per suite.

### Min training tasks

The minimum number of training tasks per suite.

### Allow partial task suites

The setting determines the output in the last task suite if it has less than the required number of general tasks.

By default, the option is enabled.

### Keep task order from uploaded data

{% include [keep-task-order](../_includes/toloka-requester-source/id-toloka-requester-source/keep-task-order.md) %}

## Dynamic pricing and overlap {#pool-dynamic-price-info}

### Dynamic pricing

This parameter allows you to vary the task price depending on the Toloker's [skill](../../glossary.md#skill) level. [Learn more](dynamic-pricing.md).

### Dynamic overlap

You can use this parameter if you specify fixed values for the [input data](../../glossary.md#input-output-data) fields. It lets you save your budget and avoid setting fixed [overlap](../../glossary.md#overlap) for all pool tasks.

You set the range, the service analyzes the task responses, their consistency, the level of Tolokers' skills and, if necessary, increases the overlap within the range you specified. [Learn more](dynamic-overlap.md).

## Optional settings {#pool-additional-settings-info}

### Pool priority within the project

Number from 0 to 100. Allows you to rank a pool within a project. First, a Toloker is assigned tasks from a pool with higher priority.

### Time per task suite, sec

The time allowed for completing a task suite, in seconds. Uncompleted tasks are redistributed to other Tolokers.

We recommend spending no more than 60 seconds per task (including the time for page loading and sending responses).

If you set the interval too long, the tasks will stay open for a long time. If it is too short, the tasks won't be completed and paid for.

### Keep pool open after completion, sec

The interval during which the pool will remain open from the moment all tasks are completed. Minimum — 0 (1 if you use dynamic overlap), maximum — 259200 seconds (three days).

For example, you can use this parameter if you need an open pool where you regularly upload new tasks.

### Pool closing date

The date the pool closes. The pool closes automatically on this date, even if the tasks aren't marked up.

### Pool type

Specify the pool type:

- **General tasks**: The main pool that contains your regular tasks.

- **Exam**: A pool that contains only [control tasks](../../glossary.md#control-task).

- **Training**: A main pool that consists only of [training tasks](../../glossary.md#training-task) and can have zero cost. Use it to train Tolokers before performing real tasks if the [training pool](train.md) doesn't work well for your project.

- **Retry**: A pool that helps Tolokers who make mistakes improve their skills and get a second chance to complete tasks.

- **Other**: If none of the previous options fit.

{% note info %}

If the price per task suite is zero, you must select the pool type.

{% endnote %}

{% note tip "How to work via Toloka API" %}

To edit a pool using Toloka API, send a `PUT` request with all the pool parameters including the ones you want to modify:

```bash
curl -X PUT 'https://toloka.dev/api/v1/pools/32267581' \
     -H 'Content-Type: application/json' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
     -d '{"id":"32267581","project_id":"81776","private_name":"Transcript of audio recordings","may_contain_adult_content":true,"will_expire":"2023-03-09T00:00:00","auto_close_after_complete_delay_seconds":0,"reward_per_assignment":0.070,"metadata":{},"assignment_max_duration_seconds":600,"auto_accept_solutions":true,"auto_accept_period_day":21,"assignments_issuing_config":{"issue_task_suites_in_creation_order":false},"filter":{"and":[{"or":[{"category":"profile","key":"languages","operator":"IN","value":"EN"}]}]},"quality_control":{"configs":[{"collector_config":{"type":"ASSIGNMENT_SUBMIT_TIME","uuid":"38830d4b-930b-43ab-a98f-f52e992fd11a","parameters":{"fast_submit_threshold_seconds":15}},"rules":[{"conditions":[{"key":"fast_submitted_count","operator":"GTE","value":2}],"action":{"type":"RESTRICTION_V2","parameters":{"scope":"PROJECT","duration_unit":"PERMANENT"}}}]}]},"defaults":{"default_overlap_for_new_task_suites":3},"priority":0,"owner":{"id":"6c6e20dc86cca2ae787afcb2629de162","myself":true},"type":"REGULAR","status":"OPEN","created":"2022-03-10T07:41:53.626","speed_quality_balance":{"percent":100,"type":"TOP_PERCENTAGE_BY_QUALITY"}}'
```

Refer to the [Edit pool](https://toloka.ai/docs/api/api-reference/#put-/pools/-id-) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

{% endnote %}

## What's next {#what_next}

- [Add tasks to the pool](pool.md)
- Learn more about how to set up a pool:

    - [Setting up pricing](dynamic-pricing.md).
    - [Dynamic overlap](dynamic-overlap.md).
    - Selective [majority vote](selective-mvote.md) control.
    - [Filters](filters.md).
    - [Speed/quality balance](adjust.md).
    - [Setting up quality control](qa-pool-settings.md).
    - [Reviewed assignments](offline-accept.md).

## For developers {#for-developers}

- [Toloka API: Editing pool](https://toloka.ai/docs/api/api-reference/#put-/pools/-id-)
- [Toloka API: Changing pool priority](https://toloka.ai/docs/api/api-reference/#patch-/pools/-id-)
- [Toloka-Kit: Editing pool](../../toloka-kit/reference/toloka.client.TolokaClient.update_pool.md)
- [Toloka-Kit: Patching pool](../../toloka-kit/reference/toloka.client.TolokaClient.patch_pool.md)
- [Toloka-Kit recipe: Change pool priority](../../toloka-kit/recipes/change-pool-priority.md)

## Troubleshooting {#troubleshooting}

{% include [faq-right-time-limit](../_includes/faq/adding-tasks-to-the-pool/right-time-limit.md) %}

{% include [faq-overlap](../_includes/faq/pool-setup/overlap.md) %}

{% cut "Can I change overlap after the pool is started?" %}

Yes. Open edit mode for the pool and set a new overlap value. You don't need to restart the pool. Updating the settings is usually fast, but if there are many tasks, it may take several minutes.

{% endcut %}

{% include [faq-how-many-tasks-in-suite](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-in-suite.md) %}

{% include [troubleshooting-speed-dropped](../_includes/troubleshooting/pool-setup/speed-dropped.md) %}

{% include [faq-labeling-speed](../_includes/faq/project-settings/labeling-speed.md) %}

{% include [faq-speed-up-completion](../_includes/faq/pool-setup/speed-up-completion.md) %}

{% include [faq-change-time-for-task](../_includes/faq/adding-tasks-to-the-pool/change-time-for-task.md) %}

{% include [faq-edit-uploaded-tasks](../_includes/faq/adding-tasks-to-the-pool/edit-uploaded-tasks.md) %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}