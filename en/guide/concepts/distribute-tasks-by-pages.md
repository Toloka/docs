# Ways to group tasks in suites

There are several ways to combine uploaded tasks into suites. You can choose the way that works best for you and specify additional settings.

{% cut "Why this is important" %}

The Toloker receives payment for a task suite, so the labeling cost and quality depend on optimal task distribution.

{% endcut %}

## Set manually {#by-empty-row}

Enter the number of tasks per suite.

## Smart mixing {#smart-mixing}

Specify how many tasks of each type should be in each task suite. For example, 8 general tasks, 1 training and 1 control task. If necessary, specify the minimum number of tasks for each type in [pool settings](pool-main.md). The order of tasks depends on the **Keep task order from uploaded data** pool setting.

#### When to use

This method is useful if the created pool:

- Contains [control](../../glossary.md#control-task) or [training](../../glossary.md#training-task) tasks in addition to the [general](../../glossary.md#general-task) tasks.

- Has [dynamic overlap](dynamic-overlap.md) (incremental relabeling, IRL) enabled.

{% cut "Sample settings" %}

![](../_images/location-job/task-upload/method-uploading-tasks.png =700x)

{% endcut %}

#### Features

- Tasks are divided into lists: regular, control, and training.

- The number of tasks of the given type that you specified in the settings is added from each list. By default, tasks are randomly selected.

- Tasks in the suite are mixed up before the page is shown to the Toloker.

- If there aren't enough general tasks and the **Allow partial task suites** option is set, the Toloker is given an [incomplete task suite](../../glossary.md#incomplete-task-suite). Please note that the number of control and training tasks in this case must be complete.

{% note alert %}

If you upload a file via **Smart mixing**, you won't be able to use other ways of task distribution on the pages in this pool.

{% endnote %}

After uploading the tasks with **smart mixing** you will be able to [mark up tasks](task_markup.md) and set selective [majority vote checking](mvote.md).

#### How to distribute tasks as suites {#smart-mixing}

| Characteristics/upload type                                                                            | Set manually | Smart mixing |
|--------------------------------------------------------------------------------------------------------|--------------|--------------|
| To generate task suites, tasks are taken in the order of rows (from top to bottom) in an uploaded file | Yes          | No           |
| Tasks are mixed within a suite                                                                         | No           | Yes          |
| Task suites are distributed to Tolokers in the same order                                              | No           | Yes          |
| Within identical task suites, control tasks are the same for all Tolokers                              | Yes          | No           |

{% note info %}

Please note that the above table is correct if you have **more than one task** per task suite. When you choose to have only one task in a task suite, the platform will sort not tasks but task suites. In this case, the **Set manually** option will not keep the order of the tasks and, on the contrary, the **Smart mixing** option will preserve the task order.

{% endnote %}

## Control tasks {#gs}

#### How many control tasks do I need to add?

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

If there are few control tasks in the open pool, [add new control tasks](../troubleshooting/troubleshooting.md#add-gs).

{% cut "What for" %}

In a large pool with few control tasks, there might be a situation when a Toloker who has completed a lot of tasks in the project stops getting new task suites. This happens when the Toloker completes all control tasks in the pool.

{% endcut %}

{% note info %}

To filter out Tolokers, use the [Control tasks](control.md) quality control rule. To rank Tolokers by the quality of control task responses, use a [skill](nav.md).

{% endnote %}

#### Setting overlap

If you upload tasks from the Toloka interface, infinite overlap is set automatically for control and training tasks, so that there is enough to mark up all general tasks.

You can set the overlap via the [Toloka API](../../glossary.md#toloka-api) or use **Set manually** for task allocation.

{% note alert "Important" %}

Set infinite overlap for control tasks.

If another overlap value is set, control tasks may end during labeling and the pool will stop being labeled.

{% endnote %}

## Tips and recommendations {#tips}

- If you used **Set manually**, you can find out the number of tasks per suite in the pool settings. But some suites may be [incomplete](../../glossary.md#incomplete-task-suite).

- If you uploaded tasks in a different way, you can check how they're grouped into suites in the Toloka interface for requesters. To do this, on the pool page, click **files** → **Download all tasks**. You can use the [Toloka API](../../glossary.md#toloka-api) to check task distribution across suites.

## See also {#see-also}

- [{#T}](train.md)
- [{#T}](task_markup.md)
- [{#T}](dynamic-overlap.md)

## For developers {#for-developers}

- [Toloka API: Task suites](https://toloka.ai/docs/api/api-reference/#tag--task-suite)
- [Toloka-Kit recipe: Group tasks in task suites](../../toloka-kit/recipes/create-task-suite.md)

## Troubleshooting {#troubleshooting}

{% include [faq-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/smart-mixing.md) %}

{% include [faq-smart-mixing-after-uploading](../_includes/faq/adding-tasks-to-the-pool/smart-mixing-after-uploading.md) %}

{% include [faq-max-number-per-suite](../_includes/faq/adding-tasks-to-the-pool/max-number-per-suite.md) %}

{% include [troubleshooting-same-task-on-different-pages](../_includes/troubleshooting/adding-tasks-to-the-pool/same-task-on-different-pages.md) %}

{% include [faq-upload-accepted-assignments](../_includes/faq/adding-tasks-to-the-pool/upload-accepted-assignments.md) %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}