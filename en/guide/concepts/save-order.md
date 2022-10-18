# Keep task order

If you need the Tolokers to receive task suites in the same order that they are within the uploaded [TSV file](../../glossary.md#tsv-file-definition) or quickly reach the overlap to monitor the [majority vote](../../glossary.md#selective-majority-vote-check), set it up with the {% if locale == "en-com" %}**Keep task order**{% endif %} option.


## Theory {#do-not-save}

The **Keep task order** option works differently depending on the task distribution method.
- If the **Set manually** method is used, Tolokers receive task suites one after another: page 1 first, then pages 2 and 3, and so on.

    Tasks within suites also follow one after another, and all Tolokers see the same sequence.

- For **smart mixing**, the algorithm generates suites so that Tolokers receive tasks in the order they are listed in the TSV file. Note that only task suites are distributed in order, while the tasks **within the suites** are mixed on the page.

By default, this option is disabled (set to {% if locale == "en-com" %}**No**{% endif %}). In this case, both the task suites and the tasks inside the suites are given to the Tolokers in random order.
#### Example

If you upload 20 tasks from the TSV file to the pool (in order from the 1st to the 20th) and set four tasks per suite, the tasks will be distributed to the Tolokers in the following way:

Tolokers | Task suite number | Order of tasks on the page:
----- | ----- | -----
1 | 1 | 3, 2, 4, 1
2 | 5 | 17, 20, 18, 19
1 | 3 | 12, 9, 11, 10
3 | 2 | 7, 8, 6, 5
2 | 4 | 16, 13, 15, 14
3 | 3 | 11, 12, 10, 9
... | ... | ...

If the option is enabled (set to {% if locale == "en-com" %}**Yes**{% endif %}), the tasks are given to the Toloker page by page in the same order as they are in the TSV file. The tasks within the page are shuffled.
#### Example

Like in the previous case, tasks are loaded in the pool in order (from the 1st to the 20th), four tasks per suite. But in this case, the Tolokers receive task suites in the same order as in the upload file, with tasks shuffled inside each of them:

Tolokers | Task suite number | Order of tasks on the page:
----- | ----- | -----
1 | 1 | 1, 4, 3, 2
2 | 1 | 3, 4, 1, 2
1 | 2 | 6, 5, 7, 8
3 | 1 | 2, 1, 4, 3
2 | 2 | 8, 5, 7, 6
3 | 2 | 5, 8, 6, 7
... | ... | ...


## Features including overlap {#with-overlap}

If [overlap](../../glossary.md#overlap) is more than one and the {% if locale == "en-com" %}**Keep task order**{% endif %} option is enabled, then the next task suite will be distributed after it reaches full overlap.

In this case, if the [user](../../glossary.md#started-workers) has already completed one task suite or there is a new [interested user](../../glossary.md#interested-workers), they will get the next suite that isn't in progress yet, even if the previous one didn't reach full overlap.

If a user refuses the issued task suite, it will be given to another user — either someone else who is interested in the pool, or an available user who accepts the task.

If you added the **majority vote** quality control rule, when all completed task suites have reached full overlap, the Toloker will be assigned a [skill](../../glossary.md#skill) using **majority vote**. For example, if overlap 3 is set in the pool settings, the skill is calculated after each of these suites reaches overlap 3, not after the Toloker completes 3 suites.

#### Example

The pool's overlap is set to 3:

Tolokers | Task suite number | The overlap value achieved | Note
----- | ----- | ----- | -----
1 | 1 | 1 | Interested users received page 1
2 | 1 | 2
1 | 2 | 1 | A Toloker completed task suite 1 and got task suite 2, although task suite 1 didn't reach full overlap
3 | 1 | 3 | Full overlap of task suite 1
3 | 2 | 1 | The Toloker who took the task refused to complete task suite 2
4 | 2 | 2 | The interested user received task suite 2 right away because there is already a full overlap for task suite 1, and the Toloker who took it refused to perform task suite 2
1 | 3 | 1 | A Toloker completed task suite 2 and got task suite 3, although suite 2 didn't reach full overlap
2 | 2 | 3 | Full overlap of task suite 2
5 | 3 | 1 | Interested user refused to complete task suite 3
2 | 3 | 2 | The Toloker who accepted it received task suite 3 because the interested user refused to complete it
3 | 3 | 3 | Full overlap of task suite 3
... | ... | ... | ...


## How to enable it {#save}

To use this option in your project, turn on the **Keep task order** option in the {% if locale == "en-com" %}**Parameters**{% endif %} settings when creating a new [pool](../../glossary.md#pool).
![](../_images/control-rules/mvote/save-order-tasks-yes.png)
You can also set the order of tasks in the [Toloka API](../../glossary.md#api-yandex-toloka).

To do this, use the function `issue_task_suites_in_creation_order: ture/false`
- `true` — Task suites are distributed in the same order as they are in the uploaded [TSV file](../../glossary.md#tsv-file-definition).

- `false` — Task suites are distributed in random order.

Additionally, you can use the function that mixes tasks within the suite: `shuffle_tasks_in_task_suite: true/false`.
- `true` — Tasks are mixed up within the suite.

- `false` — The order in which tasks were uploaded is kept. The default is `true`, meaning that tasks are shuffled within the suite.


## Troubleshooting {#troubleshooting}

#### Where is my TSV file added if I upload it to the running pool?

If you have the **Keep task order** option enabled, labeling will start after the previously uploaded tasks are taken by users. If this option is disabled, we can't guarantee that the tasks are assigned in their sequence order.


{% include [contact-support](../_includes/contact-support-help.md) %}
