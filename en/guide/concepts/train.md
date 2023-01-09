# Adding a training

With training pools, Tolokers can practice before getting started. You can provide access to the general task pool only to those Tolokers who passed the training.

The training pool contains only [training tasks](../../glossary.md#training-task). Tasks in the training pool aren't paid for.

The training pool doesn't have its own filters. The Toloker requirements are the same as in the main pool.

{% note info %}

If the training pool functionality doesn't meet your needs, create a main pool and set the pool type to [**Training**](../../glossary.md#training).

{% endnote %}

## How does it work? {#how-it-works}

1. You create a training pool. A [training skill](../../glossary.md#training-skill) is created automatically. Newly created training pools use a skill that was already created.

1. You upload tasks to the pool and [mark them up](../../glossary.md#task-markup). You can upload tasks that are already marked up.

1. You link the training to the main pool.

1. You start the main pool and the training pool.

1. The Toloker sees only the training tasks and decides to complete them.

    If the Toloker makes a mistake, they are shown a hint. To go to the next assignment, they need to answer all questions correctly. If the tips aren't helpful, the Toloker won't be able to complete the training.

1. When the Toloker completes the training, they are assigned a training skill. The skill value is the percentage of correct responses submitted by the Toloker.

    Only the first responses of the Toloker are taken into account. Therefore, the correct responses in the hints don't affect the the training skill value.

1. If the percentage of correct responses is higher or equal to the **Level required** value in the **linked** pool, the Toloker will have access to this pool.

    Pools that aren't linked to the training pool will be available to everyone unless you set the filters. Regardless of whether the Toloker passed the training or not.

    {% note tip %}

    You can link multiple pools to one training pool and set different required levels for them. This lets you assign more difficult tasks to more advanced Tolokers.

    {% endnote %}

## How do I create a training pool? {#create-train}

1. Open the [project](../../glossary.md#project) page.

1. Go to the {% if locale == "en-com" %}**Training**{% endif %} tab.

1. Click the {% if locale == "en-com" %}**Add training**{% endif %} button.

1. Fill in the [training settings](train.md) fields.
    You can use the {% if locale == "en-com" %}**Retry after**{% endif %} field to set up [repeated training](train.md).
1. Click {% if locale == "en-com" %}**Save training**{% endif %}.

## After you created a training pool {#after-creating}

1. [Upload tasks to the pool and mark them up](pool.md) (add correct responses and hints). All tasks must be [training](../../glossary.md#training-task). You can upload tasks that are already marked up.

    {% cut "What should be a good hint?" %}

    Avoid wordings like: “You answered incorrectly, please provide the correct response”. The Toloker learns when the hint explains the essence of their mistake.

    Make the hints clear. Explain which response should be chosen and why.

    {% endcut %}

1. Link the training to the main pool. For this, [edit the main pool](pool-edit.md) by filling in the fields:

    - {% if locale == "en-com" %}**Training**{% endif %} — Name of the training pool.

    - {% if locale == "en-com" %}**Level required**{% endif %} — Percentage of correct responses in training tasks (from 5 to 100) required to be admitted to the main pool. The calculation is based on the first response the Toloker gave in each task.

## Training settings {#parameters}

#|
||**Field** | **Overview**||
||{% if locale == "en-com" %}**Guidelines**{% endif %} | [Instructions](../../glossary.md#instructions) for the training tasks.

By default, the [project instructions](instruction.md) are displayed. To write separate instructions for training, deselect the {% if locale == "en-com" %}**Use project instructions**{% endif %} box.||
||{% if locale == "en-com" %}**Training title**{% endif %} | Name of the training pool (not visible to the Toloker).||
||{% if locale == "en-com" %}**Adult content**{% endif %} | Whether the training tasks have porn content.||
||{% if locale == "en-com" %}**Time on task**{% endif %} | The time allowed for completing a [task suite](../../glossary.md#task-suite), in seconds.||
||{% if locale == "en-com" %}**Retry after**{% endif %} | The number of days after which the Toloker can access the training again. If not specified, [training skill](../../glossary.md#training-skill) is issued for an indefinite time, and the value is fixed.

[Learn more about how it works](train.md).||
||{% if locale == "en-com" %}**Issue in task uploading order**{% endif %} | If this option is enabled, tasks are assigned to the Toloker in the order they are listed in the [file with tasks](../../glossary.md#tsv).||
||{% if locale == "en-com" %}**Shuffle on page**{% endif %} | If this option is enabled, tasks on the page are shown to the Toloker in random order.||
||{% if locale == "en-com" %}**Complete passing**{% endif %} | If this option is enabled, the Toloker must complete all the tasks in this pool to pass the training.

You can load more training tasks than required for passing the training and specify the number of pages required for setting the skill and accessing the linked pools.||
||{% if locale == "en-com" %}**Required for passing**{% endif %} | The number of assignments the Toloker must complete to pass the training.
|#

## Repeated training {#repeat-train}

After completing the training (successfully or not), the Toloker is assigned a [training skill](../../glossary.md#training-skill), and the value is fixed.

New training pools in the project **aren't shown** to the Toloker, as long as they have a training skill.

The lifespan of the skill and the need for retraining depends on what you specify in the {% if locale == "en-com" %}**Retry after**{% endif %} field.

{% cut "How does it work?" %}

{% cut "Repeated training isn't set up" %}

The training skill is assigned for an indefinite time, so the training pools in this project are no longer available to the Toloker until you delete the training skill manually.

{% endcut %}

{% cut "Repeated training" %}

The training skill is deleted after the specified number of days if the Toloker didn't complete tasks in the linked pools.

This means that:

- Those who failed to complete the training tasks can complete the training again after the specified number of days.

- Those who didn't complete tasks for a long time have to repeat the training.

- Those who actively perform tasks don't have to spend the time on retraining.

{% note info %}

Completing tasks in pools that aren't linked to the training pool isn't taken into account.

{% endnote %}

{% endcut %}

{% endcut %}

{% cut "How do I set it up?" %}

{% cut "Send only inactive Tolokers for retraining" %}

Repeated training isn't needed if the Toloker already completes tasks in the linked pools.

Enter the period in which the Toloker must complete at least one task in the linked pools to avoid retraining and keep the skill in the {% if locale == "en-com" %}**Retry after**{% endif %} field.

{% note warning %}

Don't forget to link the main and training pools. Completing tasks in pools that aren't linked to the training pool isn't taken into account. The training skill will be lost.

{% endnote %}

{% endcut %}

{% cut "Forbid repeated training" %}

Leave the {% if locale == "en-com" %}**Retry after**{% endif %} empty. Then the skill will be assigned to the Toloker for an indefinite time, and the value is fixed.

You can delete a skill or change the value manually.

{% note info %}

Tolokers will get access only to those pools for which their skill value is higher than the value in the **Level required** field.

{% endnote %}

{% endcut %}

{% endcut %}

## How to archive a training pool {#archive-train}

A pool with the {% if locale == "en-com" %}“Archived”{% endif %} status can't be started or edited.

By default, archived training pools are not visible in the list of project trainings. To view them:

1. Open the project page.

1. In the {% if locale == "en-com" %}**Training**{% endif %} tab, select {% if locale == "en-com" %}**Archived**{% endif %}.

The training pool is automatically archived if no action is performed in it for 30 days.

To archive a training pool manually, click {% if locale == "en-com" %}**![Drop-down button](../_images/drop-down.svg) → Archive**{% endif %} at the top of the pool page or ![](../_images/other/pool-action-archive.svg) in the list of training options on the project page.

If these buttons don't work, make sure that all the main pools that the training pool is linked to are [sent to the archive](pool-archive.md).

## What's next {#what_next}

- {% if locale == "en-com" %}[Top up your account](refill.md).{% endif %}
- [Start the pool](pool-run-and-stop.md).
- To view the training statistics, go to the [Skills]({{ skills }}) page and choose a skill named `<project name> - training`.

## See also {#see-also}

- [{#T}](distribute-tasks-by-pages.md)

## For developers {#for-developers}

- [Toloka API: Training](../../api/concepts/training.md)
- [Toloka-Kit: Creating training](../../toloka-kit/reference/toloka.client.TolokaClient.create_training.md)

## Troubleshooting {#troubleshooting}

{% cut "Setting up training" %}

{% include [faq-precede-with-control-questions](../_includes/faq/adding-tasks-to-the-pool/precede-with-control-questions.md) %}

{% include [faq-optional-parameters](../_includes/faq/adding-tasks-to-the-pool/optional-parameters.md) %}

{% cut "Why do I have an infinite number of pages in the training pool?" %}

Tasks have infinite overlap in the training pool. As long as the training pool is open and the training is running, Tolokers can access the tasks. Learn more about [training pools](train.md).

{% endcut %}

{% cut "How do I insert a link in the GOLDEN field?" %}

Text in the GOLDEN field must match the control text exactly.

Usually, if you copy site links from the browser, the copied links have the same format. But this is not the case when the link is trimmed or typed manually.

Check the links that you use. There are several ways to unify links:

- Add requirements for the link format in your instructions and hints in your training pool.

- Use RegExp in your JS to trim the received links and write the result to the new output field, and then match the received value against the control value.

{% endcut %}

{% include [faq-using-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/using-smart-mixing.md) %}

{% include [faq-pause-accepting](../_includes/faq/adding-tasks-to-the-pool/pause-accepting.md) %}

{% cut "How do I check that the Tolokers don't cheat during training?" %}

Training helps Tolokers learn how to complete your task and figure out the instructions.

Based on the training results, you can select the Tolokers who did well enough to be added to the main pool.

However, the mere fact that a Toloker completes your training pool successfully doesn't guarantee that they will afterwards demonstrate high quality on your general tasks. Tolokers who show a high level of accuracy during the training could have obtained correct responses from others.

Besides the training, be sure to add quality control rules and [control tasks](control.md) to your main pools. This way you can ensure the quality throughout the task performance process.

If the task requires that the Tolokers send free-format responses or data files, use **non-automatic acceptance** to pay for tasks after they are reviewed.

{% endcut %}

{% include [faq-distribute-tasks-training](../_includes/faq/adding-tasks-to-the-pool/distribute-tasks-training.md) %}

{% include [faq-two-training-pools](../_includes/faq/adding-tasks-to-the-pool/two-training-pools.md) %}

{% include [faq-admitted-to-general-task](../_includes/faq/adding-tasks-to-the-pool/admitted-to-general-task.md) %}

{% include [faq-file-with-training-tasks](../_includes/faq/adding-tasks-to-the-pool/file-with-training-tasks.md) %}

{% include [faq-all-tasks-training-pool](../_includes/faq/adding-tasks-to-the-pool/all-tasks-training-pool.md) %}

{% include [faq-optional-training](../_includes/faq/adding-tasks-to-the-pool/optional-training.md) %}

{% include [faq-training-without-correct-responses](../_includes/faq/adding-tasks-to-the-pool/training-without-correct-responses.md) %}

{% include [faq-manual-review-training](../_includes/faq/adding-tasks-to-the-pool/manual-review-training.md) %}

{% endcut %}

{% endcut %}

{% cut "Training skill" %}

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

{% cut "More Tolokers were trained than the training skill shows" %}

The pool shows the total number of Tolokers that completed at least one assignment. A training skill can be lost over time if you set [repeated training](train.md) in the pool settings. This setting allows a Toloker to pass the training again after a certain period if the Toloker didn't complete any tasks in associated pools or if there was a large time gap between completing tasks (for example, because of a [ban](../../glossary.md#banning-tolokers)). The training skill displays the Tolokers who either recently completed training, or regularly complete your tasks so that the skill doesn't expire.

{% endcut %}

{% include [faq-skill-expiration](../_includes/faq/adding-tasks-to-the-pool/skill-expiration.md) %}

{% include [faq-particular-toloker-got-skill](../_includes/faq/adding-tasks-to-the-pool/particular-toloker-got-skill.md) %}

{% endcut %}

{% cut "Test and retry" %}

{% include [faq-exam-main-pool](../_includes/faq/adding-tasks-to-the-pool/exam-main-pool.md) %}

{% include [faq-retry](../_includes/faq/adding-tasks-to-the-pool/retry.md) %}

{% include [faq-exam-preset](../_includes/faq/adding-tasks-to-the-pool/exam-preset.md) %}

{% include [faq-training-with-exam](../_includes/faq/adding-tasks-to-the-pool/training-with-exam.md) %}

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}