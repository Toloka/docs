# Ban

Tolokers can be banned in two ways:

1. [By the requester](#ban-yourself).
1. [By the platform](#ban-platform).

## How to ban a Toloker {#ban-yourself}

You can block a Toloker's access to one or more [projects](../../glossary.md#project). This lets you control manually which Tolokers will complete tasks. For example, you can choose all Tolokers with a [skill](../../glossary.md#skill) value lower than N and block their access to tasks. You can also unblock access.

To block access to tasks for a single Toloker:

1. Select a Toloker on the [Tolokers]({{ users }}) page.

1. Click {% if locale == "en-com" %}**Actions → Ban**{% endif %}, then fill in the fields:

    #|
    || Field | Overview ||
    || {% if locale == "en-com" %}**Ban type**{% endif %} | Where to apply the ban:

    - {% if locale == "en-com" %}**In all my projects**{% endif %} — All projects.
    - {% if locale == "en-com" %}**In the project**{% endif %} — A single project (choose one from the list).||
    || {% if locale == "en-com" %}**Ban expires**{% endif %} | Set when to lift the ban.

    We recommend blocking access temporarily in order to maintain the desired number of Tolokers for completing tasks.||
    || {% if locale == "en-com" %}**Reason**{% endif %} | The reason for banning (only seen by the requester).||
    |#

To block access to tasks for multiple Tolokers:

1. Select Tolokers by using the [filters](../../glossary.md#filters) on the [Tolokers]({{ users }}) page or upload a TSV file:

    {% if locale == "en-com" %}

    ```plaintext
    <annotator id 1>
    <annotator id 2>
    ...
    <annotator id n>
    ```

    {% endif %}

1. Click {% if locale == "en-com" %}**Ban**{% endif %}, then fill in the fields (see the table above).

You can view information about access to tasks on the Toloker's page (on the [Tolokers]({{ users }}) page, go to the {% if locale == "en-com" %}**Bans**{% endif %} tab). To unblock access to tasks, hover over the ban line and click ![](../_images/location-job/task-edit/task-action-delete.svg).

{% note warning %}

The assignments submitted by banned Tolokers will be taken into account if they are not rejected manually using assignment review They can be reassigned by setting up the [Recompletion of assignments from banned users](restore-task-overlap.md) rule.

{% endnote %}

## Banning on the platform {#ban-platform}

Toloka has dedicated [anti-fraud system](https://toloka.ai/anti-fraud/) for banning dishonest Tolokers. It monitors user behavior and blocks suspicious accounts.

The main reasons for banning:

1. Disclosure of confidential information.
1. Using scripts and bots or any form of cheating.
1. Poor response quality.
1. Providing false data during registration.
1. Frequently skipping captchas or entering them incorrectly.
1. Using multiple accounts.

{% note info %}

If a Toloker's behavior seems suspicious, [write to support](../troubleshooting/support.md#cheater). We'll conduct an additional review. If the Toloker is violating the user agreement, they'll be blocked in the system and will no longer be able to complete tasks.

You can also [ban](#ban) this Toloker from your project.

{% endnote %}

## Troubleshooting {#troubleshooting}

{% cut "My project has a trusted Toloker who was banned by the system" %}

Unfortunately, this Toloker has violated the user agreement and will no longer be able to complete tasks. You can find new Tolokers or customize [filters](filters.md) so that they better match the project requirements.

{% endcut %}

{% cut "Can I disable tasks for Tolokers who do a poor job on tasks?" %}

You can deny access to the pool if the Toloker's responses are [too fast](quick-answers.md), if they don't match the [majority vote](mvote.md), or if the Toloker makes too many mistakes in [control tasks](goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](restore-task-overlap.md).

{% endcut %}

{% cut "Can I ask a Toloker to redo the task if they made mistakes in it?" %}

No. After sending a task, the Toloker can't make any changes to it. You can add tasks that were [completed](../../glossary.md#completed-tasks) incorrectly to a new pool.

{% endcut %}

{% cut "Can I fix something in a completed task myself?" %}

No, you can't fix anything in the task itself. However, you can do this manually in the results file.

{% endcut %}

{% cut "Fraudulent Tolokers submit assignments with empty response fields. Are they going to be banned before the responses of other Tolokers are known?" %}

Fraudulent Tolokers aren't banned before the [majority vote](mvote.md) is known. That's why we recommend that you have new Tolokers complete [training](train.md) or a test. Then you can select the Tolokers that successfully completed the training to do your tasks.

{% endcut %}

{% cut "Are the cheaters who were banned for incorrect responses paid anyway?" %}

If the Toloker was already paid for the tasks, you can't cancel the payment.

{% endcut %}

{% cut "Tolokers completed the training successfully, but have poor results in the general task" %}

During the training, Tolokers follow the task instructions and practice completing your tasks. Based on the training results, the requester can select Tolokers who did well enough to get access to the main pool. However, the mere fact that the Toloker completes your training pool successfully does not guarantee that they will continue to demonstrate high-quality performance. Tolokers who did well on the training but had inadequate results in the general task might have obtained correct training responses from other people.

In addition to the training, be sure to set up [quality control rules](control.md) in your main pools. This lets you control the quality throughout the task completion process. If the task requires that users send free-format responses or data files, use [non-automatic acceptance](offline-accept.md) to pay for them only after reviewing the responses.

{% endcut %}

{% cut "The results include the responses of users who I banned" %}

The results show the responses of all users, including those who are banned. To exclude their responses from the results, select the option **Exclude assignments by banned users**. It will delete the responses from users who were banned at the moment the results were downloaded, not when the pool was labeled.

{% endcut %}

{% cut "How can I ban a user and reject all their responses?" %}

You can't automatically reject the responses of a banned Toloker.

But you can do it yourself if you want. When downloading the results, select the option **Exclude assignments by banned users** to delete the responses of Tolokers who were banned at the moment of downloading. You can also forward all the assignments from banned users to other Tolokers using the [Re-completion of assignments from banned users](restore-task-overlap.md) rule.

{% endcut %}

{% cut "Report suspicious Tolokers" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10035353.388b5c1d02f16762f4a79b515beaa9740148362a/?lang=en&iframe=1&service=toloka-ai"></iframe>

{% endcut %}