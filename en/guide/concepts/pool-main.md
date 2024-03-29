# Creating a pool

If you already have a [pool](../../glossary.md#pool) and you want to create an identical one, [clone](pool-main.md) the existing pool. If not, create a new pool.

## New pool {#new-pool}

A pool contains the settings of a set of task that are sent out for completion. [The task interface](../../glossary.md#task-interface) is described in the [project](project.md).

{% note info %}

You can first test the pool settings in the [sandbox](sandbox.md) and then [move](sandbox.md#export) them to the Toloka production version along with the project.

{% endnote %}

To create a pool:

{% include [toloka-requester-pool-wizard](../_includes/toloka-requester-source/id-toloka-requester-source/pool-wizard.md) %}

![](../_images/other/pool-settings.png)

Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the **Client** filter and select the desired value: **Toloka web version** or **Toloka for mobile**.

{% note tip "How to work via Toloka API" %}

To create a pool using Toloka API, send a `POST` request with the information about the pool:

```bash
curl -X POST 'https://toloka.dev/api/v1/pools' \
     -H 'Content-Type: application/json' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
     -d '{"project_id":"83859","private_name":"First pool","will_expire":"2030-01-01T00:00:00.000Z","reward_per_assignment":0.05,"assignment_max_duration_seconds":300,"auto_accept_solutions":false,"defaults":{"default_overlap_for_new_task_suites":1}}'
```

Refer to the [Create pool](https://toloka.ai/docs/api/api-reference/#post-/pools) section of the Toloka API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

{% endnote %}

### Pool parameters {#pool-params}

#|
||**Parameter** | **Overview** | **Found at the step**||
||**My tasks may contain shocking or pornographic content** | Whether the tasks have some content which can be marked as adult, including shocking or pornographic content. Tasks with such content are only given to Tolokers who agree to complete these types of tasks.

If you aren't sure whether the tasks have such content, enable this option. | **Select the audience for your tasks**||
||**Filters** | {% include [toloka-requester-source-filters-desc](../_includes/toloka-requester-source/id-toloka-requester-source/filters-desc.md) %} | **Select the audience for your tasks**||
||**Speed/quality balance** | A [setting](adjust.md) for choosing Tolokers for your tasks. If you want to get responses very quickly, the quality may be doubtful. If you want very high quality, be prepared to wait longer. Find a balance that meets your needs. [Learn more](adjust.md). | **Select the audience for your tasks**||
||**Review task responses manually** | Turn on this option to [review](accept.md) the [completed tasks](../../glossary.md#completed-tasks) manually.

Set the time period when you can check the tasks and reject them if the results are poor.

To learn more about manual review, see the [Manual review](offline-accept.md) page. | **Set up quality control**||
||**Training** | This field is only available if you have training pools in the project.

[Training pool](../../glossary.md#training-pool) that will be linked to the main one. | **Set up quality control**||
||**Level required, %** | This field is only available if you have filled in the **Training** field.

Percentage of correct responses in training tasks (from 0 to 100) required to be admitted to the pool tasks. The calculation is based on the first response the Toloker gave in each task.

The minimum required level that you can set is 5. Tolokers who complete training with apercentage below this level won't have access to tasks. | **Set up quality control**||
||**Review period in days** | The number of days for reviewing and accepting tasks (max: 21). The Toloker will see the deadline for checking the tasks:

- In the task information on the Toloka main page.
- In the history of completed tasks. | **Set up quality control**||

||**Price per task suite, $** | Payment per [task suite](../../glossary.md#task-suite) in US dollars. For cents, use the dot (".") as a separator. If the **Pool type** is **General tasks**, the minimum price per task suite is $0.005. For other pool types, you can set the price to zero. To learn more about price management, go to [Setting up pricing](dynamic-pricing.md). | **Set the task price and overlap**||

||**Overlap** | The number of Tolokers who should complete each task in the pool.

Configure this parameter if you need several people to complete your task. Overlap is necessary in tasks for collecting photo datasets, recording audio, or conducting surveys. In other types of tasks, it can improve the quality of results.

To save money, you can set up [dynamic overlap](../../glossary.md#dynamic-overlap) (also known as incremental relabeling or IRL).

Dynamic overlap will help you save money. [Learn more](dynamic-overlap.md). | **Set the task price and overlap**||

||**Dynamic pricing** | Click **Show dynamic pricing & overlap** to go to the parameter. This parameter allows you to vary the task price depending on the Toloker's [skill](../../glossary.md#skill) level. [Learn more](dynamic-pricing.md) | **Set the task price and overlap**||
||**Dynamic overlap** | Click **Show dynamic pricing & overlap** to go to the parameter. You can use this parameter if you specify fixed values for the [input data](../../glossary.md#input-output-data) fields. It lets you save your budget and avoid setting fixed [overlap](../../glossary.md#overlap) for all pool tasks.

You set the range, the service analyzes the responses, their consistency, the level of Tolokers' skills and, if necessary, increases the overlap within the range you specified. | **Set the task price and overlap**||
||**Pool priority within the project** | Number from 0 to 100. Allows you to rank a pool within a project. First, a Toloker is assigned tasks from a pool with higher priority. | **Add optional pool settings**||
||**Time per task suite, sec** | The time allowed for completing a task suite, in seconds. Uncompleted tasks are redistributed to other Tolokers.

We recommend giving at least 60 seconds per task suite (including the time for page loading and sending responses).

If you set the interval too long, the tasks will stay open for a long time. If it is too short, the tasks won't be completed and paid for. | **Add optional pool settings**||
||**Keep pool open after completion, sec** | The interval during which the pool will remain open from the moment all tasks are completed. Minimum — 0, maximum — 259200 seconds (three days).

For example, you can use this parameter if you need an open pool where you regularly upload new tasks. | **Additional settings**||
||**Pool closing date** | The date the pool closes. The pool closes automatically on this date, even if the tasks aren't marked up. | **Add optional pool settings**||

||**Metafields** | To pass an array of metafields, specify key and value for each metafield. | **Add optional pool settings**||
||**General tasks** | The number of general tasks per suite when using smart mixing. | **Prepare and upload data**||
||**Control tasks** | The number of control tasks per suite when using smart mixing. | **Prepare and upload data**||
||**Training tasks** | The number of training tasks per suite when using smart mixing. | **Prepare and upload data**||
||**Min general tasks** | The minimum number of general tasks per suite when using smart mixing. | **Prepare and upload data**||
||**Min control tasks** | The minimum number of control tasks per suite when using smart mixing. | **Prepare and upload data**||
||**Min training tasks** | The minimum number of training tasks per suite when using smart mixing. | **Prepare and upload data**||
||**Number of tasks per suite** | The number of tasks per suite when using the **Set manually** method. | **Prepare and upload data**||
||**Allow partial task suites** |{% include [smart-mixing-selected](../_includes/toloka-requester-source/id-toloka-requester-source/smart-mixing-selected.md) %}

The setting determines the output in the last task suite if it has less than the required number of general tasks.

By default, the option is enabled.| **Prepare and upload data**||
||**Keep task order from uploaded data** |{% include [smart-mixing-selected](../_includes/toloka-requester-source/id-toloka-requester-source/smart-mixing-selected.md) %}

{% include [keep-task-order](../_includes/toloka-requester-source/id-toloka-requester-source/keep-task-order.md) %}|**Prepare and upload data**||
|#

{% include [project-moderation](../_includes/toloka-requester-source/id-toloka-requester-source/project-moderation.md) %}

## How Tolokers see pools {#pool-appear}

Tolokers can't see pools inside the project and select specific tasks (except for field tasks, where they can select points on the map). They also can't see pool settings, the number of tasks, or completion progress.

If at least one pool from the project is available to the Toloker, then this project is displayed on the main page as a card with the name, description, and price for the task. After selecting a project, the Toloker is issued a task from the pool. When they complete it, another one is issued, and so on.

A single project card is displayed if the pools in it differ only by name, quality control, or [filters](../../glossary.md#filters). In the latter case, the project card only includes tasks from the pools that the Toloker has access to.

{% cut "Tolokers see one project card" %}

For example, you create "Pool 1" and "Pool 2" with the same settings in the "Are there traffic signs in the photo?" project. If the Toloker has access to both pools, they are displayed as a single card on the main page.

![](../_images/other/toloka-1pool.png)

{% endcut %}

Several cards are displayed if the pools differ in these settings:

- Acceptance type
- Public description
- Task price

This is useful if you want to combine tasks in pools by subject, duration of audio recordings, or difficulty of evaluation.

{% cut "Tolokers see several project cards" %}

In this example, the Toloker has access to two pools with different prices and descriptions, so there are two project cards on the main page. The Toloker can choose any of them — for example, the one with the higher price.

![](../_images/other/toloka-2pools.png)

{% endcut %}

## Cloning a pool {#clone}

To clone a pool, click **![Drop-down button](../_images/drop-down.svg) → Clone** at the top of the pool page or ![](../_images/clone-pool.svg) in the list of pools on the project page.

If you need to change the pool settings, [open edit mode](pool-edit.md).

## What's next {#what_next}

- [Start](pool-run-and-stop.md) a pool.
- Learn more about how to set up a pool:

    - [Setting up pricing](dynamic-pricing.md).
    - [Dynamic overlap](dynamic-overlap.md).
    - Selective [majority vote](selective-mvote.md) control.
    - [Filters](filters.md).
    - [Speed/quality balance](adjust.md).
    - [Setting up quality control](qa-pool-settings.md).
    - [Reviewed assignments](offline-accept.md).

## For developers {#for-developers}

- [Toloka API: Creating pool](https://toloka.ai/docs/api/api-reference/#post-/pools)
- [Toloka-Kit recipe: Create pool](../../toloka-kit/recipes/create-pool.md)

## Troubleshooting {#troubleshooting}

{% include [faq-overlap](../_includes/faq/pool-setup/overlap.md) %}

{% include [faq-specific-number](../_includes/faq/pool-setup/specific-number.md) %}

{% include [faq-change-overlap](../_includes/faq/pool-setup/change-overlap.md) %}

{% include [faq-right-time-limit](../_includes/faq/adding-tasks-to-the-pool/right-time-limit.md) %}

{% include [faq-how-many-tasks-in-suite](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-in-suite.md) %}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}