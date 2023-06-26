# Pool parameters

#|
||**Parameter** | **Overview** | **Found in the block**||
||**Pool name** | The [pool](../../glossary.md#pool) name shown only to you (as a requester) on the [project](../../glossary.md#project) page. | **General information**||
||**Public description** | Will be displayed instead of the project description in the task list for Tolokers and [linked training](train.md). | **General information**||
||**Private comment** | If necessary, you can add a private pool description that will only be available to you. | **General information**||
||**Price per task suite, $** | Payment per [task suite](../../glossary.md#task-suite) in US dollars. For cents, use the dot (".") as a separator. If the **Pool type** is **General tasks**, the minimum price per task suite is $0.005. For other pool types, you can set the price to zero. To learn more about price management, go to [Setting up pricing](dynamic-pricing.md). | **Price**||
||**Overlap** | The number of Tolokers who should complete each task in the pool.

Configure this parameter if you need several people to complete your task. Overlap is necessary in tasks for collecting photo datasets, recording audio, or conducting surveys. In other types of tasks, it can improve the quality of results.

To save money, you can set up dynamic overlap (also known as incremental relabeling or IRL). [Learn more](dynamic-overlap.md). | **Price**||
||**My tasks may contain shocking or pornographic content** | Whether the tasks have some content which can be marked as adult, including shocking or pornographic content. Tasks with such content are only given to Tolokers who agree to complete these types of tasks.

If you aren't sure whether the tasks have such content, enable this option. | **Audience**||
||**Filters** |

{% include [toloka-requester-source-filters-desc](../_includes/toloka-requester-source/id-toloka-requester-source/filters-desc.md) %}

| **Audience**||
||**Speed/quality balance** | A [setting](adjust.md) for choosing Tolokers for your tasks. If you want to get responses very quickly, the quality may be doubtful. If you want very high quality, be prepared to wait longer. Find a balance that meets your needs. [Learn more](adjust.md). | **Audience**||
||**Review task responses manually** | Turn on this option to [review](accept.md) the [completed tasks](../../glossary.md#completed-tasks) manually.

Set the time period when you can check the tasks and reject them if the results are poor.

To learn more about manual review, go to [Reviewing assignments](offline-accept.md). | **Quality control**||
||**Training** | This field is only available if you have training pools in the project.

[Training pool](../../glossary.md#training-pool) that will be linked to the main one. | **Quality control**||
||**Level required, %** | This field is only available if you have filled in the **Training** field.

Percentage of correct responses in training tasks (from 0 to 100) required to be admitted to the pool tasks. The calculation is based on the first response the Toloker gave in each task.

The minimum required level that you can set is 5. Tolokers who complete training with apercentage below this level won't have access to tasks. | **Quality control**||
||**General tasks** | The number of general tasks per suite. | **Smart mixing**||
||**Control tasks** | The number of control tasks per suite. | **Smart mixing**||
||**Training tasks** | The number of training tasks per suite. | **Smart mixing**||
||**Min general tasks** | The minimum number of general tasks per suite. | **Smart mixing**||
||**Min control tasks** | The minimum number of control tasks per suite. | **Smart mixing**||
||**Min training tasks** | The minimum number of training tasks per suite. | **Smart mixing**||
||**Allow partial task suites** |
{% include [smart-mixing-selected](../_includes/toloka-requester-source/id-toloka-requester-source/smart-mixing-selected.md) %}

The setting determines the output in the last task suite if it has less than the required number of general tasks.

By default, the option is enabled.
| **Smart mixing**||
||**Keep task order from uploaded data** |
{% include [smart-mixing-selected](../_includes/toloka-requester-source/id-toloka-requester-source/smart-mixing-selected.md) %}

**Option disabled (default value)**

The uploaded tasks are grouped in pages and given to Tolokers in random order. Within the page, the task order is always random.

{% cut "Example" %}

If you specified 2 tasks per page when uploading the [TSV file](../../glossary.md#tsv) with image links to the pool, the system can generate them as follows:

#|
||**Tasks in the file** | **Page 1** | **Page 2** | **Page 3**||
||Image 1 | Image 2 | Image 6 | Image 4||
||Image 2 | Image 5 | Image 1 | Image 3||
||Image 3 |  |  | ||
||Image 4 |  |  | ||
||Image 5 |  |  | ||
||Image 6 |  |  | ||
|#

{% endcut %}

**Option enabled**

Tasks will be grouped on pages in the order they are listed in the task file.

{% cut "Example" %}

If you specified 2 tasks per page when uploading the file with image links to the pool, you're equally likely to get pages where the first link goes first and the second goes second, and the other way around:

#|
||**Tasks in the file** | **Page 1** | **Page 2** | **Page 3**||
||Image 1 | Image 1 | Image 3 | Image 5||
||Image 2 | Image 2 | Image 4 | Image 6||
||Image 3 | _or_ | _or_ | _or_||
||Image 4 | Image 2 | Image 4 | Image 6||
||Image 5 | Image 1 | Image 3 | Image 5||
||Image 6 |  |  | ||
|#

{% endcut %}

If the pool has an overlap, the next task is distributed only when the previous task is completed by the necessary number of Tolokers.

Use this parameter to:

- Speed up collection of responses for [majority vote](mvote.md) check.

- Issue tasks by priority.

    Put important tasks in the beginning of the file. They will be completed faster and with the necessary overlap.
|**Smart mixing**||
||**Review period in days** | The number of days for reviewing and accepting tasks (max: 21). The Toloker will see the deadline for checking the tasks:

- In the task information on the Toloka main page.
- In the history of completed tasks. | **Quality control**||
||**Dynamic pricing** | This parameter allows you to vary the task price depending on the Toloker's [skill](../../glossary.md#skill) level. [Learn more](dynamic-pricing.md) | **Dynamic pricing and overlap**||
||**Dynamic overlap** | You can use this parameter if you specify fixed values for the [input data](../../glossary.md#input-output-data) fields. It lets you save your budget and avoid setting fixed [overlap](../../glossary.md#overlap) for all pool tasks.

You set the range, the service analyzes the responses, their consistency, the level of Tolokers' skills and, if necessary, increases the overlap within the range you specified. | **Dynamic pricing and overlap**||
||**Pool priority within the project** | Number from 0 to 100. Allows you to rank a pool within a project. First, a Toloker is assigned tasks from a pool with higher priority. | **Additional settings**||
||**Time per task suite, sec** | The time allowed for completing a task suite, in seconds. Uncompleted tasks are redistributed to other Tolokers.

We recommend spending no more than 60 seconds per task (including the time for page loading and sending responses).

If you set the interval too long, the tasks will stay open for a long time. If it is too short, the tasks won't be completed and paid for. | **Additional settings**||
||**Keep pool open after completion, sec** | The interval during which the pool will remain open from the moment all tasks are completed. Minimum — 0 (1 if you use dynamic overlap), maximum — 259200 seconds (three days).

For example, you can use this parameter if you need an open pool where you regularly upload new tasks. | **Additional settings**||
||**Pool closing date** | The date the pool closes. The pool closes automatically on this date, even if the tasks aren't marked up. | **Additional settings**||
||**Pool type** | Specify the pool type:

- **General tasks**: The main pool that contains your regular tasks.

- **Exam**: A pool that contains only [control tasks](../../glossary.md#control-task).

- **Training**: A main pool that consists only of [training tasks](../../glossary.md#training-task) and can have zero cost. Use it to train Tolokers before performing real tasks if the [training pool](train.md) doesn't work well for your project.

- **Retry**: A pool that helps Tolokers who make mistakes improve their skills and get a second chance to complete tasks.

- **Other**: If none of the previous options fit.

{% note info %}

If the price per task suite is zero, you must select the pool type.

{% endnote %}
| **Additional settings**||
||
|#