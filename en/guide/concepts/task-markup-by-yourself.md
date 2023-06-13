# How to edit tasks by yourself

You can turn a [general task](../../glossary.md#general-task) into a [control task](../../glossary.md#control-task) by adding the correct answer, or into a [training task](../../glossary.md#training-task) by adding the correct answer and a hint.

{% cut "What makes a good hint?" %}

Avoid wordings like: “You answered incorrectly, please provide the correct response”. The Toloker learns when the hint explains the essence of their mistake.

Make the hints clear. Explain which response should be chosen and why.

{% endcut %}

{% note alert "Restriction" %}

Task markup is available only for [training pools](train.md) and [pools](../../glossary.md#pool) uploaded with [“smart mixing”](distribute-tasks-by-pages.md#smart-mixing).

{% endnote %}

## How do I mark up tasks? {#section_czh_fj2_ghb}

1. Make sure the pool isn't running.

1. Go to the pool page and click either the **Control tasks** or **Training tasks** indicator in the **Tasks** block.

    ![Click Control or Training tasks](../_images/location-job/task-edit/control-training-tasks.png =400x)

1. Create a control or a training task from another type of task clicking the appropriate button.

    ![Create control or training tasks](../_images/location-job/task-edit/create-from-tasks.png =700x)
    
1. Select the correct response in the task preview block.

1. Select the [output data fields](incoming.md) that should be checked. 

1. Add a hint if you're creating a training task.

1. Click **Save and go to next**.

{% cut "Example of task markup" %}

In this example, the correct response is added for the control task. Only the choice in the `result` field is checked.

![](../_images/location-job/task-edit/task-edit.png =630x)

{% endcut %}

{% note tip %}

When creating control tasks, enter only correct responses that answer the question. So for an image classification task, **Image loading error** is not a correct response that answers the task question.

{% endnote %}

## How to improve the reliability of control tasks {#answer_distribution}

After you have created the control tasks, make sure that different variations of correct responses occur with the same frequency. This will help avoid random guessing in responses.

1. Go to the pool page and click the **Control tasks** indicator in the **Tasks** block.

1. Check the **Distribution of correct responses for control tasks** chart.

    The distribution of responses is shown as a percentage.

### Example of response distribution

{% list tabs %}

- Correct

  ![](../_images/location-job/task-edit/distribution_ex1.png =400x)

- Incorrect

  ![](../_images/location-job/task-edit/distribution_ex2.png =400x)

{% endlist %}

## How to view the control tasks statistics {#task-statistics}

You can view the number and percentage of correct responses to the control tasks or training tasks.

To do this, go to the pool page and click the **Control tasks** or **Training tasks** indicator in the **Tasks** block.

The response statistics is shown in the **Responses from Tolokers** and **Correct responses, %** columns.

### Alternative way

1. Click ![](../_images/other/three-points-button.svg) → **Edit** in the **Tasks** block on the pool page.

1. Click the tab with the type of the task.

1. Find the task in the list and click ![](../_images/edit.svg).

The response statistics is shown in the **Responses** and **Correct** fields  at the right.

## How to edit tasks {#task-edit}

1. Make sure the pool isn't running.

1. Go to the pool page and click ![](../_images/other/three-points-button.svg) → **Edit** in the **Tasks** block.

1. Click the tab with the type of the task.

1. Find the task in the list and click ![](../_images/edit.svg). Editing mode opens.

## How to delete a task from the pool {#delete-task}

1. Make sure the pool isn't running.

1. Go to the pool page and click ![](../_images/other/three-points-button.svg) → **Edit** in the **Tasks** block.

1. Click the tab with the type of the task.

1. Find the task in the list and click ![](../_images/location-job/task-edit/task-action-delete.svg). You can also delete a task from the pool in [editing mode](#task-edit).

{% note tip %}

If you set the overlap to 0 [via the API](https://toloka.ai/docs/api/api-reference/#patch-/tasks/-id-/set-overlap-or-min), the task won't be visible to Tolokers, and you won't have to delete it.

{% endnote %}

## What's next {#what_next}

- [Add a training pool](train.md).
- [Top up your account](refill.md).
- [Start the pool](pool-run-and-stop.md).

## See also {#see-also}

- [Efficiency indicators: Control tasks](./efficiency-metrics/control-tasks-share.md)
- [Efficiency indicators: Control task balance](./efficiency-metrics/control-tasks-balance.md)

## Troubleshooting {#troubleshooting}

{% cut "Uploading tasks to a pool" %}

{% include [faq-processing-log](../_includes/faq/adding-tasks-to-the-pool/processing-log.md) %}

{% include [troubleshooting-uploading-tasks-errors](../_includes/troubleshooting/adding-tasks-to-the-pool/uploading-tasks-errors.md) %}

{% include [faq-how-many-tasks-toloker-will-see](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-toloker-will-see.md) %}

{% include [faq-upload-accepted-assignments](../_includes/faq/adding-tasks-to-the-pool/upload-accepted-assignments.md) %}

{% include [troubleshooting-marked-as-training](../_includes/troubleshooting/adding-tasks-to-the-pool/marked-as-training.md) %}

{% include [faq-create-task-file-properly](../_includes/faq/adding-tasks-to-the-pool/create-task-file-properly.md) %}

{% include [troubleshooting-syntax-error](../_includes/troubleshooting/adding-tasks-to-the-pool/syntax-error.md) %}

{% include [faq-max-number-per-suite](../_includes/faq/adding-tasks-to-the-pool/max-number-per-suite.md) %}

{% include [faq-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/smart-mixing.md) %}

{% include [faq-smart-mixing-after-uploading](../_includes/faq/adding-tasks-to-the-pool/smart-mixing-after-uploading.md) %}

{% include [faq-right-time-limit](../_includes/faq/adding-tasks-to-the-pool/right-time-limit.md) %}

{% include [faq-task-suite-difference](../_includes/faq/adding-tasks-to-the-pool/task-suite-difference.md) %}

{% include [troubleshooting-same-task-on-different-pages](../_includes/troubleshooting/adding-tasks-to-the-pool/same-task-on-different-pages.md) %}

{% endcut %}

{% include [faq-how-many-tasks-in-suite](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-in-suite.md) %}

{% include [faq-how-many-control-tasks](../_includes/faq/pool-setup/how-many-control-tasks.md) %}

{% include [faq-correct-responses-counted](../_includes/faq/pool-setup/correct-responses-counted.md) %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles-internal](../../../_includes/image-styles-internal.md) %}
