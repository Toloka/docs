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

{% include [faq-disable-tasks](../_includes/faq/result-questions/disable-tasks.md) %}

{% include [troubleshooting-pool-archived](../_includes/troubleshooting/result-questions/pool-archived.md) %}

{% include [troubleshooting-rejected-task](../_includes/troubleshooting/result-questions/rejected-task.md) %}

{% include [faq-reject-part](../_includes/faq/result-questions/reject-part.md) %}

{% include [faq-notify](../_includes/faq/result-questions/notify.md) %}

{% include [faq-increase-rating](../_includes/faq/result-questions/increase-rating.md) %}

{% include [troubleshooting-low-rating-similar-tasks](../_includes/troubleshooting/result-questions/low-rating-similar-tasks.md) %}

{% include [troubleshooting-low-rating-instructions](../_includes/troubleshooting/result-questions/low-rating-instructions.md) %}

{% include [troubleshooting-low-rating-interface](../_includes/troubleshooting/result-questions/low-rating-interface.md) %}

{% include [troubleshooting-low-rating-communication](../_includes/troubleshooting/result-questions/low-rating-communication.md) %}

{% include [troubleshooting-blank-spaces](../_includes/troubleshooting/result-questions/blank-spaces.md) %}

{% include [faq-empty-text-field](../_includes/faq/result-questions/empty-text-field.md) %}

{% include [troubleshooting-include-responses](../_includes/troubleshooting/users/include-responses.md) %}

{% include [faq-get-time](../_includes/faq/result-questions/get-time.md) %}

{% include [contact-support](../_includes/contact-support.md) %}