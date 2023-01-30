# Editing a pool

You can edit a pool with the “Open” or “Closed” status. While editing, an open pool switches to the “CLOSED_FOR_UPDATE” status. For example, this way you can change the payout amount in a running pool.

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

### Captcha frequency

You can choose how often [captchas](../../glossary.md#captcha) are shown to Tolokers:

- “No” — Don't show captchas.

- “Low” — Show a captcha after every 20 assignments.

- “Medium”/ “High” — Show a captcha after every 10 assignments.

To show the captcha to Tolokers, set [the quality control rule](captcha.md).

{% include [captcha-warning](../_includes/captcha-warning.md) %}

### Review task responses manually

Turn on this option to [review](accept.md) the [completed tasks](../../glossary.md#completed-tasks) manually.

Set the time period when you can check the tasks and reject them if the results are poor.

Learn more about task review [here](offline-accept.md) and [here](accept.md).

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

Evaluate Tolokers' responses by comparing them with the majority vote: reward Tolokers who give correct responses and block those who often make mistakes.

In the **Accept as majority** field, specify the number of matching responses that is considered the majority vote and set the condition. The rule takes effect when the number of responses for the task is equal to the overlap.

For example: if the number of responses is > 5 and the percentage of correct responses is < 60, then ban the Toloker on the project for 10 days.

### Training

This field is only available if you have training pools in the project.

[Training pool](../../glossary.md#training-pool) that will be linked to the main one.

### Level required

This box is only available if you filled in the **Training** box.

Percentage of correct responses in training tasks (from 5 to 100) required to be admitted to the pool tasks. The calculation is based on the first response the Toloker gave in each task.

The minimum required level that you can set is 5. Tolokers who complete training with apercentage below this level won't have access to tasks.

{% endcut %}

## Dynamic pricing and overlap {#pool-dynamic-price-info}

### Dynamic pricing

This parameter allows you to vary the task price depending on the Toloker's [skill](../../glossary.md#skill) level. [Learn more](dynamic-pricing.md).

### Dynamic overlap

You can use this parameter if you specify fixed values for the [input data](../../glossary.md#input-output-data) fields. It lets you save your budget and avoid setting fixed [overlap](../../glossary.md#overlap) for all pool tasks.

You set the range, the service analyzes the responses, their consistency, the level of Tolokers' skills and, if necessary, increases the overlap within the range you specified. [Learn more](dynamic-overlap.md).

## Optional pool settings {#pool-additional-settings-info}

Click **Show advanced settings** to edit optional pool settings.

### Priority

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

### Keep task order

#### Option disabled (default value)

The uploaded tasks are grouped in pages and given to Tolokers in random order. Within the page, the task order is always random.

{% cut "Example" %}

If you specified 2 tasks per suite when uploading the [file](../../glossary.md#tsv) with image links to the pool, the system can generate them as follows:

Tasks in the file | Page 1 | Page 2 | Page 3
----- | ----- | ----- | -----
Image 1 | Image 2 | Image 6 | Image 4
Image 2 | Image 5 | Image 1 | Image 3
Image 3 |  |  |
Image 4 |  |  |
Image 5 |  |  |
Image 6 |  |  |

{% endcut %}

#### Option enabled

Tasks will be grouped on pages in the order they are listed in the task file.

{% cut "Example" %}

If you specified 2 tasks per suite when uploading the file with image links to the pool, you're equally likely to get pages where the first link goes first and the second goes second, and the other way around:

Tasks in the file | Page 1 | Page 2 | Page 3
----- | ----- | ----- | -----
Image 1 | Image 1 | Image 3 | Image 5
Image 2 | Image 2 | Image 4 | Image 6
Image 3 | _or_ | _or_ | _or_
Image 4 | Image 2 | Image 4 | Image 6
Image 5 | Image 1 | Image 3 | Image 5
Image 6 |  |  |

{% endcut %}

If the pool has an overlap, the next task is distributed only when the previous task is completed by the necessary number of Tolokers.

Use this parameter to:

- Speed up collection of responses for [majority vote](mvote.md) check.

- Assign tasks by priority.

    Put important tasks in the beginning of the file. They will be completed faster and with the necessary overlap.

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

- [Toloka API: Editing pool](../../api/concepts/edit-pool.md)
- [Toloka API: Changing pool priority](../../api/concepts/set-priority-pool.md)
- [Toloka-Kit: Editing pool](../../toloka-kit/reference/toloka.client.TolokaClient.update_pool.md)
- [Toloka-Kit: Patching pool](../../toloka-kit/reference/toloka.client.TolokaClient.patch_pool.md)
- [Toloka-Kit recipe: Change pool priority](../../toloka-kit/recipes/change-pool-priority.md)

## Troubleshooting {#troubleshooting}

{% cut "What is the right time limit for the task completion?" %}

Try completing the tasks yourself. Ask your colleagues and friends to complete them. Find out average completion time and add 50% to it.

{% endcut %}

{% cut "What overlap should I set?" %}

Overlap defines how many Tolokers complete the same pool task.

The best overlap is an overlap that provides satisfying quality of results. For most tasks that are not [reviewed](../../glossary.md#assignment-review), overlap from “3” to “5” is enough. If the tasks are simple, overlap of “3” is likely to be enough. For tasks that are reviewed, set overlap to “1”.

{% endcut %}

{% cut "Can I change overlap after the pool is started?" %}

Yes. Open edit mode for the pool and set a new overlap value. You don't need to restart the pool. Updating the settings is usually fast, but if there are many tasks, it may take several minutes.

{% endcut %}

{% cut "How many tasks should be in a suite?" %}

The number of tasks depends on how difficult and time-consuming the tasks are. Keep the size reasonably small. Large task suites are unpopular, partly because they are inconvenient for Tolokers (for example, if the internet connection is unstable).

{% endcut %}

{% cut "Why has the speed of pool completion dropped?" %}

Possible reasons:

- You've stopped the [main pool](../../glossary.md#training-pool). This could limit the number of Tolokers with access to the pool. Start the training pool again. There will be more Tolokers who can access the tasks.

- The filters you set are too strict. For example, a strong restriction on a certain skill that most Tolokers don't have.

- Too many Tolokers are banned. Ease the quality control rules.

{% endcut %}

{% cut "How can I speed up the pool completion?" %}

- To motivate Tolokers, assign a [public skill](nav-create.md#public) and use [dynamic pricing](dynamic-pricing.md).

- Try to [increase the project rating](project_rating_stat.md), so that your task is higher in the list of tasks for Tolokers.

- Adjust the [quality-speed ratio](adjust.md).

- Set a higher [priority](pool_poolparams.md#priority) for the pool among other project pools.

{% endcut %}

{% cut "If I change the time allocated for one task, will this apply to tasks assigned earlier?" %}

If you change the time allocated for a task, the time value will apply to the tasks that have not yet been taken by the Tolokers. The same applies to the case when you close the pool. A Toloker who has an assignment in the active status can complete the assignment.

{% endcut %}

{% cut "How do I edit or delete tasks uploaded to the pool?" %}

If you uploaded tasks to the pool using “smart mixing”, you can stop the pool and mark up your tasks: edit answers, hints, or delete tasks.

If you uploaded them using a different method, clone your pool and upload the new file with the corrected list of data to be labeled.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}