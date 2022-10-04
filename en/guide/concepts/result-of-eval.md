# Receiving responses

You can download Tolokers' responses in a file as tasks are completed.

If tasks were distributed with an [overlap](../../glossary.md#overlap-ru) of more than 2, run [aggregation](result-aggregation.md). Toloka will process all Tolokers' responses for the task and form the resulting response.

## Getting the file with responses {#tsv}

To get a file with Tolokers' responses, click the {% if locale == "en-com" %}**Download results**{% endif %} button on the [pool](../../glossary.md#pool-ru) page.

#### Fields in the file with responses

- `INPUT:<name of the [input data](incoming.md) field>` — Input data for tasks.

- `OUTPUT:<name of the [output data](incoming.md) field>` — The Tolokers' responses. For [training tasks](../../glossary.md#training-task-ru), the field includes first attempted answers.

- `GOLDEN:<name of the [output data](incoming.md) field>` — Responses for [control tasks](../../glossary.md#control-task-ru).

- `HINT:text` — Hints for training tasks.

- Information about the task completion (the same for all tasks on the page):

    - `ASSIGNMENT:link` — Link for viewing the [task suite](../../glossary.md#task-page-ru).

    - `ASSIGNMENT:assignment_id` — ID of the assigned task suite.

    - `ASSIGNMENT:worker_id` — ID of the Toloker who completed the task.

    - `ASSIGNMENT:started` — Date and time the task suite was assigned.

    - `ASSIGNMENT:status` — Task status: `SUBMITTED` — completed, `APPROVED` — accepted, `REJECTED` — declined.


#### Sample file
![](../_images/results/tsv-result.png)

{% note warning %}

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

- Use the [Toloka API]({{ api-toloka-attachments }}) to download files with responses.



## Troubleshooting {#troubleshooting}

#### Can I ask a Toloker to redo the task if they made mistakes in it?

No. After sending a task, the Toloker can't make any changes to it. You can add tasks that were [completed](../../glossary.md#submitted-answers-ru) incorrectly to a new pool.

#### Can I fix something in a completed task myself?

No, you can't fix anything in the task itself. However, you can do this manually in the results file.

#### How do I send an assignment back to the Toloker for revision?

You can only accept or reject an assignment.

#### Can I disable tasks for Tolokers who do a poor job on tasks?

You can deny access to the pool if the Toloker's responses are [too fast](quick-answers.md), if they don't match the [majority vote](mvote.md), or if the Toloker makes too many mistakes in [control tasks](goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](restore-task-overlap.md).

#### What should I do if I want to accept a completed task but the pool is already archived or the Toloker wrote to me after the allowed time?

Simply [give the Toloker a separate reward](bonus.md) without changing the task status. You can't change the task status in the pool in this case.

#### What should I do if I rejected a task for a reason that isn't specified in the instructions?

Accept the task and update the instructions. Otherwise, you violate the [**Requester Agreement**]({{ customeragreement }}) that requires to clearly state the task requirements and the results expected from the Toloker.

#### Can I reject part of the responses on the page and accept part of them?

No. For example, there are 10 tasks in a suite that costs $0.10, and the Toloker did 2 of them incorrectly.

You can't accept the correct answers and pay for this part ($0.08). Response pages are accepted or rejected in their entirety.

#### How can I notify the Toloker of changes in the instructions?

Add the notification to the project description (for example: "Attention! The instructions changed") and send a message to all the people who completed your tasks. To do this:
- Assign them a hidden skill, or use an existing [skill](nav-assign.md) linked to the pool.
- Go to **Messages** and click **Write** → **Group** → **Add filter** → **Choose your skill** → **<skill name>**.
- If you created a new skill, specify the value you assigned to the chosen group, (for example, 1). If you use an existing skill, specify the minimum value.

#### How can I increase the project's rating?

The project rating is the average rating across all categories. Pay particular attention to the categories for which you got the least points.
#### Low rating for "Will you take similar tasks in the future"

Perhaps the Tolokers found your tasks too difficult. Try to simplify them.

#### Low rating for "Clarity of instructions"

Shorten instructions and rewrite using simpler language. Add pictures and examples.

#### Low rating for "Task interface usability"

Make the interface [more user-friendly](spec.md) and don't make the Toloker complete unnecessary actions. Use keyboard shortcuts.

Starting from December 15, 2021, tasks in pools are automatically available in the web version of Toloka and the mobile app. If your task isn't available on mobile devices, it means that you might have forgotten to add the {% if locale == "en-com" %}**Client**{% endif %} filter.

#### Low rating for "Communication with the requester"

Reply to [messages from Tolokers](messaging.md) regularly. Try to provide feedback as fast as possible. Correct errors promptly and use mailing lists to notify Tolokers of changes.
If you don't understand what the problem is, run a mini-survey and ask the Tolokers who completed your tasks what they like and what they don't like.

#### Why do I get blank spaces inside my file?

When you upload a file with rows, double quotes indicate an area where you can use special characters (tabs or line breaks). Toloka merges everything in between the quotes into one row to make up one task. To use double quotes inside such an area, you need to escape them with another quote. [Read more here](pool_csv.md#string).

#### What is the result of processing an empty text field?
If a Toloker typed some text and then deleted it, the result is `null`, otherwise, it's `undefined`.
#### The results include the responses of users who I banned

The results show the responses of all users, including those who are banned. To exclude their responses from the results, select the option **Exclude assignments by banned users**. It will delete the responses from users who were banned at the moment the results were downloaded, not when the pool was labeled.

#### Can I get the exact start and end time from the Toloker with the results of the task?

When you download the results file, select the **Start time** and **Submit time** checkboxes. The downloaded file will include the exact UTC date and time when the Toloker accepted the assignment and submitted it.

{% include [contact-support](../_includes/contact-support-help.md) %}
