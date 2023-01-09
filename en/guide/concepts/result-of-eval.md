# Receiving responses

You can download Tolokers' responses in a file as tasks are completed.

If tasks were distributed with an [overlap](../../glossary.md#overlap) of more than 2, run [aggregation](result-aggregation.md). Toloka will process all Tolokers' responses for the task and form the resulting response.

## Getting the file with responses {#tsv}

To get a file with Tolokers' responses, click the {% if locale == "en-com" %}**Download results**{% endif %} button on the [pool](../../glossary.md#pool) page.

#### Fields in the file with responses

- `INPUT:<name of the input data field>` — Input data for tasks.

- `OUTPUT:<name of the output data field>` — The Tolokers' responses. For [training tasks](../../glossary.md#training-task), the field includes first attempted answers.

- `GOLDEN:<name of the output data field>` — Responses for [control tasks](../../glossary.md#control-task).

- `HINT:text` — Hints for training tasks.

- Information about the task completion (the same for all tasks on the page):

    - `ASSIGNMENT:link` — Link for viewing the [task suite](../../glossary.md#task-suite).

    - `ASSIGNMENT:assignment_id` — ID of the assigned task suite.

    - `ASSIGNMENT:worker_id` — ID of the Toloker who completed the task.

    - `ASSIGNMENT:started` — Date and time the task suite was assigned.

    - `ASSIGNMENT:status` — Task status: `SUBMITTED` — completed, `APPROVED` — accepted, `REJECTED` — declined.

#### Sample file

![](../_images/results/tsv-result.png)

{% note alert %}

The responses submitted by the banned Toloker before the ban will be taken into account and paid for. To exclude their responses from the results and aggregations, select the option **Exclude assignments from banned users**. It will delete the responses from users who were banned at the moment of downloading the results, not when the pool was labeled.

{% endnote %}

## Getting files {#file-download}

If the Tolokers were asked to upload files, the file with responses will contain IDs of the files received from Tolokers. To download files on your computer, click the  button on the pool page.

You can download all files in the pool in one archive up to 4 GB in size. If the archive is too large (more than 4 GB), use the following tips:

- Select a single status or pick a smaller time range.

    For example, if you need to review assignments, only download the submitted assignments rather than the accepted or rejected ones.

    If the file still exceeds the permitted size, pick a smaller time range and download the archives in several batches. The time range can be reduced to 1 day.

- On the pool page, click **Review assignments** (or **View assignments** if they have already been accepted) to go to the page with the Tolokers' responses. Each string contains the Toloker's response to one task suite.

    Select the responses you need and click . Download the archives in several batches. You can select and download no more than 100 responses at a time.

- Use the [Toloka API](../../api/concepts/attachments.md) to download files with responses.

## See also {#see-also}

- [Crowdsourcing concepts: Results](https://toloka.ai/knowledgebase/results/)

## For developers {#for-developers}

- [Toloka API: Getting responses](../../api/concepts/get-response.md)
- [Toloka API: Files in responses](../../api/concepts/attachments.md)
- [Toloka-Kit: Getting responses](../../toloka-kit/reference/toloka.client.TolokaClient.get_assignments.md)
- [Toloka-Kit: Getting attachments](../../toloka-kit/reference/toloka.client.TolokaClient.get_attachments.md)

## Troubleshooting {#troubleshooting}

{% include [faq-redo-task](../_includes/faq/users/redo-task.md) %}

{% include [faq-fix-myself](../_includes/faq/result-questions/fix-myself.md) %}

{% include [faq-send-back](../_includes/faq/result-questions/send-back.md) %}

{% cut "Can I disable tasks for Tolokers who do a poor job on tasks?" %}

You can deny access to the pool if the Toloker's responses are [too fast](quick-answers.md), if they don't match the [majority vote](mvote.md), or if the Toloker makes too many mistakes in [control tasks](goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](restore-task-overlap.md).

{% endcut %}

{% cut "What should I do if I want to accept a completed task but the pool is already archived or the Toloker wrote to me after the allowed time?" %}

Simply [give the Toloker a separate reward](bonus.md) without changing the task status. You can't change the task status in the pool in this case.

{% endcut %}

{% include [troubleshooting-rejected-task](../_includes/troubleshooting/result-questions/rejected-task.md) %}

{% include [faq-reject-part](../_includes/faq/result-questions/reject-part.md) %}

{% cut "How can I notify the Toloker of changes in the instructions?" %}

Add the notification to the project description (for example: “Attention! The instructions changed”) and send a message to all the people who completed your tasks. To do this:

- Assign them a hidden skill, or use an existing [skill](nav-assign.md) linked to the pool.

- Go to **Messages** and click {% if locale == "en-com" %}**Write** → **Group** → **Add filter** → **Choose your skill** → **&lt;skill name&gt;**{% endif %}.

- If you created a new skill, specify the value you assigned to the chosen group, (for example, 1). If you use an existing skill, specify the minimum value.

{% endcut %}

{% include [faq-increase-rating](../_includes/faq/result-questions/increase-rating.md) %}

{% include [troubleshooting-low-rating-similar-tasks](../_includes/troubleshooting/result-questions/low-rating-similar-tasks.md) %}

{% include [troubleshooting-low-rating-instructions](../_includes/troubleshooting/result-questions/low-rating-instructions.md) %}

{% cut "Low rating for “Task interface usability”" %}

Make the interface [more user-friendly](spec.md) and don't make the Toloker complete unnecessary actions. Use keyboard shortcuts.

Starting from December 15, 2021, tasks in pools are automatically available in the web version of Toloka and the mobile app. If your task isn't available on mobile devices, it means that you might have forgotten to add the {% if locale == "en-com" %}**Client**{% endif %} filter.

{% endcut %}

{% cut "Low rating for “Communication with the requester”" %}

Reply to [messages from Tolokers](messaging.md) regularly. Try to provide feedback as fast as possible. Correct errors promptly and use mailing lists to notify Tolokers of changes.

If you don't understand what the problem is, run a mini-survey and ask the Tolokers who completed your tasks what they like and what they don't like.

{% endcut %}

{% cut "Why do I get blank spaces inside my file?" %}

When you upload a file with rows, double quotes indicate an area where you can use special characters (tabs or line breaks). Toloka merges everything in between the quotes into one row to make up one task. To use double quotes inside such an area, you need to escape them with another quote. [Read more here](pool_csv.md#string).

{% endcut %}

{% include [faq-empty-text-field](../_includes/faq/result-questions/empty-text-field.md) %}

{% include [troubleshooting-include-responses](../_includes/troubleshooting/users/include-responses.md) %}

{% include [faq-get-time](../_includes/faq/result-questions/get-time.md) %}

{% include [contact-support](../_includes/contact-support.md) %}