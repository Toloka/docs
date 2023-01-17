# How to edit tasks by yourself

You can turn a general task into a [control task](../../glossary.md#control-task) by adding the correct answer, or into a [training task](../../glossary.md#training-task) by adding the correct answer and a hint.

{% cut "What makes a good hint?" %}

Avoid wordings like: “You answered incorrectly, please provide the correct response”. The Toloker learns when the hint explains the essence of their mistake.

Make the hints clear. Explain which response should be chosen and why.

{% endcut %}

{% note alert "Restriction" %}

Task markup is available only for [training pools](train.md) and pools uploaded with [“smart mixing”](distribute-tasks-by-pages.md#smart-mixing).

{% endnote %}

## How do I mark up tasks? {#section_czh_fj2_ghb}

1. Make sure the pool isn't running.

1. Click {% if locale == "en-com" %}**Edit**{% endif %} in the {% if locale == "en-com" %}**Pool tasks**{% endif %} block.

1. Open the **General**, **Control**, or **Training** tab. Create a control or a training task from another type of task.

1. Select the responses that should be checked. (The list of the [output data fields](incoming.md) is on the right.)

1. Click **Save and go to next**.

{% cut "Example of task markup" %}

In this example, the correct response is added for the control task. Only the choice in the `result` field (Good/Bad/Loading error) is checked.

![](../_images/location-job/task-edit/task-edit.png)

{% endcut %}

## Improve the reliability of control tasks {#answer_distribution}

After you have created the control tasks, make sure that different variations of correct responses occur with the same frequency. This will help avoid random guessing in responses.

1. Go to the task markup page.

1. Open the {% if locale == "en-com" %}**Training tasks → Distribution of correct responses for control tasks**{% endif %} tab.

    The distribution of responses is shown as a percentage.

{% note tip %}

When creating control tasks, enter only correct responses that answer the question. So for an image classification task, **Image loading error** is not a correct response that answers the task question.

{% endnote %}

#### Example of response distribution

{% list tabs %}

- Correct

  ![](../_images/location-job/task-edit/distribution_ex1.png)

- Incorrect

  ![](../_images/location-job/task-edit/distribution_ex2.png)

{% endlist %}

## How to edit tasks {#task-edit}

1. Make sure the pool isn't running.

1. Click **Edit** in the **Pool tasks** block.

1. Click the tab with the type of the task.

1. Find the task in the list and click ![](../_images/edit.svg) . Editing mode opens.

## How to delete a task from the pool {#delete-task}

1. Make sure the pool isn't running.

1. Click **Edit** in the **Pool tasks** block.

1. Click the tab with the type of the task.

1. Find the task in the list and click ![](../_images/location-job/task-edit/task-action-delete.svg). You can also delete a task from the pool in [editing mode](#task-edit).

{% note tip %}

If you set the overlap to 0 [via the API](../../api/concepts/set-min-task-overlap.md), the task won't be visible to Tolokers, and you won't have to delete it.

{% endnote %}

## What's next {#what_next}

- [Add a training pool](train.md).
- {% if locale == "en-com" %}[Top up your account](refill.md).{% endif %}
- [Start the pool](pool-run-and-stop.md).

## See also {#see-also}

- [Efficiency indicators: Control tasks](./efficiency-metrics/control-tasks-share.md)
- [Efficiency indicators: Control task balance](./efficiency-metrics/control-tasks-balance.md)

## Troubleshooting {#troubleshooting}

{% cut "Uploading tasks to a pool" %}

{% cut "Errors when uploading tasks in the pool" %}

{% include [faq-processing-log](../_includes/faq/adding-tasks-to-the-pool/processing-log.md) %}

#### Errors in column headers

If the [column headings](pool_csv.md) are incorrect, the whole file is rejected. Otherwise, Toloka specifies the number of tasks with processing errors.

#### Processing errors tables

```json
"parsing_error_of": "https://tlk.s3.yandex.net/wsdm2020/photos/2d5f63a3184919ce7e3e7068cf93da4b.jpg\t\t",
"exception_msg": "the nameMapping array and the sourceList should be the same size (nameMapping length = 1, sourceList size = 3)"
```

#|
||**Overview**|**How to fix**||
||**Extra tabs.**

If the uploaded file contains more `\t` column separators after the data or the link than the number of columns set in the [input data](../../glossary.md#input-output-data), you get an error message.

For example, if 1 column is set in the input data, and two more `\t\t` tabs are added in the file after the link, you get 3 columns, 2 of which are excessive. | Remove extra column separators in the above example — both `\t\t` characters.||
|#

```json
"exception_msg": "the nameMapping array and the sourceList should be the same size (nameMapping length = 4, sourceList size = 6)"
```

#|
||**Overview**|**How to fix**||
||**The number of fields in the header and in the row doesn't match.** | Make sure that:

- The number of tabs in the file structure is correct.
- String values with tab characters are enclosed in [quotation marks](pool_csv.md#string)`" "`.
|#

```json
"code": "VALUE_REQUIRED", "message": "Value must be present and not equal to null"
```

#|
||**Overview**|**How to fix**||
||**The value is missing for a required input field.** | Make sure that columns with required input data fields are filled.||
|#

```json
"code": "INVALID_URL_SYNTAX", "message": "Value must be in valid url format"
```

#|
||**Overview**|**How to fix**||
||**Invalid data in a “link” (“url”) field.** | Make sure that:

- Links start with the `http://`, `https://` or `www` prefix.||
|#

```json
"exception_msg": "unexpected end of file while reading quoted column beginning on line 2 and ending on line 4"
```

#|
||**Overview**|**How to fix**||
||**Unpaired quotation mark in a string.** | Check that all quotation marks are [escaped](pool_csv.md#string).||
|#

{% endcut %}

{% cut "How do I know how many tasks a Toloker will see on the page?" %}

You can specify the number of tasks on the page when you upload your tasks to the pool. For more information about distributing tasks across pages, see [this article](distribute-tasks-by-pages.md).

{% endcut %}

{% cut "How do I upload the file with the accepted assignments back to Toloka for projects with non-automatic acceptance? Where do I find the format of the upload data?" %}

Use the button **Upload review results** to upload your file. You can see the format [here](accept.md).

Assignments are reviewed in a file.

{% endcut %}

{% include [troubleshooting-marked-as-training](../_includes/troubleshooting/adding-tasks-to-the-pool/marked-as-training.md) %}

{% cut "How do I create the task file properly so that there are no errors?" %}

In the file with the general tasks, the columns with the `INPUT` headers must be filled out. You can see those headers if you download a sample file from the pool.

If you are creating control tasks, fill out the `GOLDEN` columns with the correct responses.

If you are creating a training task, you also need to fill in the `HINT:text` column. For the general tasks you don't need any columns other than `INPUT`, so feel free to delete them.

The file format must be TSV, XLSX or JSON, and the encoding must be UTF-8.

For more information about creating the file, see the [Guide](pool_csv.md). If there are errors during the upload, look up the error description on this [page](task_upload.md).

{% endcut %}

{% include [troubleshooting-syntax-error](../_includes/troubleshooting/adding-tasks-to-the-pool/syntax-error.md) %}

{% cut "What is the maximum number of tasks per page?" %}

It depends on the task. Technically, you can use as many tasks you want.

But users are reluctant to take lengthy tasks. They'd rather do 10 tasks that take one minute each than one task that takes 10 minutes.

In addition, if you use a large number of tasks on the page, there might be issues with uploading the files to be labeled. This problem might occur with images.

The third thing to consider is quality control and assignment review. If you use recompletion of assignments from banned users, you should split the task into smaller parts so that fewer assignments are recompleted. You are more likely to meet your budget this way.

{% endcut %}

{% include [faq-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/smart-mixing.md) %}

{% cut "What is the right time limit for the task completion?" %}
Try completing the tasks yourself. Ask your colleagues and friends to complete them. Find out average completion time and add 50% to it.
{% endcut %}

{% include [faq-task-suite-difference](../_includes/faq/adding-tasks-to-the-pool/task-suite-difference.md) %}

{% include [troubleshooting-same-task-on-different-pages](../_includes/troubleshooting/adding-tasks-to-the-pool/same-task-on-different-pages.md) %}

{% endcut %}

{% endcut %}

{% include [faq-how-many-tasks-in-suite](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-in-suite.md) %}

{% cut "How many control tasks do I need to add?" %}

We recommend adding at least 1% of control tasks in the pool. And for small pools — 5–10%.

{% cut "Why's that?" %}

Each control task is shown to the Toloker only once. If you use smart mixing, you determine how many control tasks should be in a suite. If each suite contains one control task, then the maximum number of suites the Toloker can complete is equal to the number of control tasks in the pool. If you increase the number of control tasks in a suite, the number of suites available to the Toloker decreases by the same number.

There shouldn't be too few pages available. Otherwise:

- You won't be able to correctly evaluate the quality of the Toloker's responses.

- The Toloker won't be interested in completing such tasks because they'll spend a lot of time studying instructions but won't earn much.

{% cut "Example" %}

#### A large pool with 1% of control tasks (good)

There are 10,000 tasks in the pool, and 100 of them are control tasks (1%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, a user can complete up to 100 suites.

#### A small pool with 1% control tasks (bad)

There are 100 tasks in the pool, and 1 of them is a control task (1%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, each user can only complete 1 suite.

#### A small pool with 10% control tasks (good)

There are 100 tasks in the pool, and 10 of them are control tasks (10%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, each user can complete up to 100 suites

{% endcut %}

{% endcut %}

If there are few control tasks in the open pool, [add new control tasks](../troubleshooting/pool-setup.md#add-gs).

{% cut "What for" %}

In a large pool with few control tasks, a situation might occur when users who have completed a lot of tasks in the project stop getting new task suites. This happens when the Toloker completes all control tasks in the pool.

{% endcut %}

{% note info %}

To filter out Tolokers, use the [Control tasks](control.md) quality control rule. To rank Tolokers by the quality of responses in control tasks, use a [skill](nav.md).

{% endnote %}

{% endcut %}

{% include [faq-correct-responses-counted](../_includes/faq/pool-setup/correct-responses-counted.md) %}

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}