# Reviewing Tolokers' responses

You started a pool with [non-automatic acceptance](offline-accept.md), and the Tolokers completed all your tasks. What next?

- Review the Tolokers' responses before the end of the **Review period** that you specified. At the end of the period, unchecked responses will be accepted automatically.
- If a Toloker didn't complete the task well, reject their response.
- The Toloker can challenge your decision by submitting an [appeal](#appeal).

## How do I review the tasks? {#acception}

#### In the Toloka interface. This option is suitable for a small number of tasks.

To accept or reject responses:

If you set [non-automatic acceptance](offline-accept.md) in the pool settings, you need to review the Tolokers' responses within the time limit set in the **Deadline** field. Tolokers may challenge a rejected response by submitting an [appeal](#appeal).

You can review assignments online or upload review results in a [TSV file](../../glossary.md#tsv-file-definition-ru).

{% note info %}

Note that you can't change the task status if the task pool was [archived](pool-archive.md).

{% endnote %}


#### Online review of one task.

To accept or reject one task:

1. Click the {% if locale == "en-com" %}**Review assignments**{% endif %} button on the pool page.

1. Choose an assignment.

    If responses include files uploaded by the Tolokers, click the {% if locale == "en-com" %}{% endif %} button to download them. To download all files from submitted responses in a ZIP archive, click {% if locale == "en-com" %}{% endif %} on the assignments review page.

1. Check the responses, click {% if locale == "en-com" %}**Accept**{% endif %} or {% if locale == "en-com" %}**Decline**{% endif %}. For rejected responses, enter a comment (specify the reason).


#### In the TSV file with the results. You will need the file to filter the results and process them programmatically.

{% note info %}

This review method is also suitable when the result is not displayed in the interface.

Example 1: The task uses JS code, and the response contains initially hidden fields.

Example 2: The task where you need to download files attached by the Toloker (for example, video or audio recordings) to check the responses.

{% endnote %}


To accept or reject responses:

1. Click the {% if locale == "en-com" %}**Review assignments**{% endif %} button on the pool page.

1. To download responses that you didn't review yet: on the pool page, click {% if locale == "en-com" %}**Download results**{% endif %}. In the window that opens:

    1. In {% if locale == "en-com" %}**Status**{% endif %} leave only the {% if locale == "en-com" %}**Submitted**{% endif %} option enabled.

    1. In {% if locale == "en-com" %}**Columns**{% endif %} leave only the {% if locale == "en-com" %}**assignment ID**{% endif %} option enabled.

    1. Disable the {% if locale == "en-com" %}**Separate assignments with empty row**{% endif %} option.

    1. Click {% if locale == "en-com" %}**Download results**{% endif %}.

1. If your task requires Tolokers to submit photos, videos or audio files, download them for review in an archive.

    Click {% if locale == "en-com" %}{% endif %}.

    {% note info %}

    **What does the response archive contain?**

    The system automatically assigns names to files when they are uploaded by the Toloker. You can rename the files manually or with a script if necessary.

    - `Response archive`

    - `Folder1_ID_ responses`

    - `File1_ID_attachments`

    - `File2_ID_attachments`

    - `Folder2_ID_ responses`

    You can match responses and attachments by their IDs. Attachment ID is included in the TSV file, in the column with the output field where the file was uploaded.

    - `TSV file`

    - `Column1_with_output_field`

    - `ID_attachments`

    - `Column2_with_output_field`

    - `ID_attachments`

    {% endnote %}

1. Open the [file with responses](result-of-eval.md).

    For a single response ID, you need to fill in the verdict and comment only once. The rest should be left empty or deleted.

    - If there is one task on the page, add a verdict and a comment to each response ID (if there is a deviation).
    - If there is more than one task on the page, then different tasks on the page will have the same response ID.

    **Explanation**

    - `ASSIGNMENT:assignment_id` — ID of the assigned task suite.

    - `ACCEPT:verdict` — Review result:

    - <q>+</q> if you accept the responses.

    - <q>-</q> if you reject the responses.

    - `ACCEPT:comment` — Comments for Tolokers if responses were rejected (for example, specify which part of the [instructions](../../glossary.md#task-instruction-ru) wasn't followed).

1. Upload the edited TSV file to Toloka ().


#### Delegate assignment review to other Tolokers.

Place a separate task for Tolokers to review the responses. To learn how to do it, see the [last project](image-segmentation-project3.md) in the [Selecting an image area](image-segmentation-overview.md). It implements assignment review with the help of Tolokers.

{% note info %}

Note that you can't change the task status if the task pool was [archived](pool-archive.md).

{% endnote %}


## Appeal {#appeal}

Within 7 days after the review, the Toloker can challenge the result by [filing an appeal]({{ appeal }}).

You will receive a message from them that contains:

- Toloker ID (`assignment_id`) in the subject.
- Explanation of why responses should be accepted (optional).

To consider an appeal, you need the response ID. If the Toloker wrote to you from the rejected response page, the response ID is automatically attached to their message as a link. If there is no ID, request it from the Toloker.

Do the following:

- If the responses were mistakenly rejected, accept them.
- Consider all appeals and respond on time — within 9 days (from the moment when the task was rejected).


## Acceptance procedure {#acceptance-procedure}

1.1. The Customer shall accept the Services through the Customer’s Personal Account or API. Two types of acceptance are possible: automatic and non-automatic. The type of acceptance shall be defined by the Customer when placing the Task through the Customer’s Personal Account or API.

1.2. If the Customer chooses automatic acceptance when placing the Task, all Tasks performed during the term specified in the Tasks shall be deemed automatically accepted by the Customer from the moment when every particular Task is completed by the User, and the Services shall be deemed duly provided by Toloka and subject to payment regardless of any other conditions. If the Customer chooses automatic acceptance, no discrepancy between results of the Task and the requirements set by Toloka in the Instruction shall constitute a basis for refusing to accept the relevant Services.

1.3. If the Customer chooses non-automatic acceptance when placing the Task, the Customer shall designate a term, which extends from the moment of completing the Task by the User and may include from 1 to 21 calendar days, within which the Customer is entitled to check results of the Tasks and accept the Services via the Customer's Personal Account or API (hereinafter referred to as the “Term of Non-automatic Acceptance”). If the Customer fails to accept the Services within the Term of Non-automatic Acceptance, the Services shall be deemed to be accepted on the last day of the Term of Non-automatic Acceptance, duly provided and payable.

1.4. The Customer is only entitled to refuse to accept the Services, if all of the following conditions are present:

a) when placing the relevant Task, the Customer has chosen non-automatic acceptance;

b) the Term of Non-automatic Acceptance has not expired;

c) the Customer placed an instruction which contain the algorithm to be followed to get proper results of the Task and comprehensive requirements to such results (hereinafter referred to as the “Instruction”);

d) the result of the Task does not comply with the Instruction.

1.5. If the Customer, pursuant to cl. 1.4. hereof, refuses to accept the Services, including the cases of considering the objections under cl. 1.7. hereof, the Customer is entitled to use the amount contributed as prepayment for the relevant Services pursuant to the Agreement to pay for the Services when placing new Tasks within the term of the Agreement.

1.6. If the Customer, pursuant to cl. 1.4 hereof, refuses to accept the Services, the Customer shall specify, which provisions of the Instruction have been violated when performing the Task, using the Interfaces of Toloka Web-Site (including API).

1.7. If the Customer, pursuant to cl. 1.4 hereof, refuses to accept the Services, Toloka is entitled to forward objections to the Customer via the Interfaces of Toloka Web Site within seven (7) calendar days from the day when the Customer has refused to accept the respective Task. The Parties undertake to settle the dispute not later than within nine (9) calendar days from the day when the Customer has refused to accept the respective Task. Having considered the objections, the Customer may decide to accept the Services or reject them again. If, as a result of considering the objections, the Customer chooses to accept the Services, the Services shall be deemed accepted on the day when the Customer performs the respective action in the Customer’s Personal Account or via API.


## Troubleshooting {#troubleshooting}

#### Can I ask a Toloker to redo the task if they made mistakes in it?

No. After sending a task, the Toloker can't make any changes to it. You can add tasks that were [completed](../../glossary.md#submitted-answers-ru) incorrectly to a new pool.

#### Can I fix something in a completed task myself?

No, you can't fix anything in the task itself. However, you can do this manually in the results file.

#### What should I do if I want to accept a completed task but the pool is already archived or the Toloker wrote to me after the allowed time?

Simply [give the Toloker a separate reward](bonus.md) without changing the task status. You can't change the task status in the pool in this case.

#### What should I do if I rejected a task for a reason that isn't specified in the instructions?

Accept the task and update the instructions. Otherwise, you violate the [**Requester Agreement**]({{ customeragreement }}) that requires you to clearly state the task requirements and the results expected from the Toloker.

#### Can I reject part of the responses on the page and accept part of them?

No. For example, there are 10 tasks in a suite that costs $0.1, and the Toloker did 2 of them incorrectly.

You can't accept the correct answers and pay for this part ($0.08). Response pages are accepted or rejected in their entirety.

{% include [contact-support](../_includes/contact-support-help.md) %}