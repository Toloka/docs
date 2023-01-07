# All questions on one page

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

#### If you aren't using Toloka yet and need advice

[Ask a question](support.md)

#### If you have a problem working with Toloka

In the section contents, select the stage where you encountered the problem and find the appropriate solution in the list. If not found, contact [support](support.md).

## Registration and getting started {#register-and-start}

{% include [troubleshooting-no-sms](../_includes/troubleshooting/register-and-start/no-sms.md) %}

{% include [troubleshooting-phone-belongs-another-user](../_includes/troubleshooting/register-and-start/phone-belongs-another-user.md) %}

## Sandbox {#sandbox}

{% include [troubleshooting-dont-see-task](../_includes/troubleshooting/sandbox/dont-see-task.md) %}

{% include [troubleshooting-export-error](../_includes/troubleshooting/sandbox/export-error.md) %}

{% include [troubleshooting-submit](../_includes/troubleshooting/sandbox/submit.md) %}

{% include [troubleshooting-cant-add-trusted-user](../_includes/troubleshooting/sandbox/cant-add-trusted-user.md) %}

## Setting up a project {#project}

### Instructions {#instruction}

{% cut "Some tags disappear after I save the instructions." %}

You can't use unsupported tags because they are deleted when you save the project. [List of supported tags](../concepts/instruction.md#html).

{% endcut %}

{% cut "What do I do if the radio button attributes are displayed correctly in the preview, but disappear after saving?" %}

If the tags or attributes disappear after you save the instructions (for example, `checked="true"`), it means that they are not supported. For the full list of tags that can be used in the instructions, see the [Guide](../concepts/instruction.md#html-yes).

{% endcut %}

### Configuring the task interface {#concept_gss_fkp_smb}

{% cut "My Tolokers can't upload a file with the assignment" %}

If none of the Tolokers can submit the assignment, the most likely reason is JS validation. Run JS validation again.

Export your project to the sandbox and try to complete the task in the sandbox yourself.

{% endcut %}

{% cut "Why is the iframe content not displayed when I add the input and output data to the HTML interface in the preview mode?" %}

Try to disable extensions in your browser. They might block iframe loading.

{% endcut %}

{% cut "I selected one checkbox, but all the checkboxes are selected." %}

The names of the output fields must differ: each checkbox must have its own unique name. For more information about this component, see [here](../concepts/t-components/checkboxes.md).

{% endcut %}

{% cut "Why doesn't the “Submit” button work in the task?" %}

The issue is probably in the JS block. Try deleting its content, then test the **Submit** button in the preview mode.

{% endcut %}

{% cut "What should the Toloker do if there is no selectable object in the image in an area selection task?" %}

There are four options:

- [ Decompose the task](../concepts/solution-architecture.md): First select images with the items you need, then select areas in them.

- Select an arbitrary area in the image. For example, put a square in the upper-right corner.

    Mention this in your instructions for reviewers.

- Ask the Toloker to skip the task and report it in a personal message. Messages are reviewed by the requester. If the selectable object is missing, the task is deleted from the pool (by resetting the overlap).

- Add the “No object” checkbox to the interface and make sure that your JS checks that either the object is selected or the checkbox is selected.

    For control purposes, add information about the value of this checkbox to the task interface.

{% endcut %}

## Setting up a pool {#pool-settings}

{% cut "I created a project and a pool, but the Next button doesn't work or the preview shows a blank screen." %}

Toloka lets you know that something is wrong with the project. The blank screen often appears when there are errors in the [task interface](../../glossary.md#task-interface), including the JavaScript code. The **Next** button may be disabled if the output specification lacks some field or contains invalid values, or if, for example, you configured validation for a nonexistent field in JavaScript.

{% endcut %}

{% cut "The Tolokers completed training for the first pool and got the skill. A week later, we cloned the pool, but all the Tolokers lost their skill. Which parameter affects skill expiration? Do all the Tolokers need to complete the training again?" %}

The validity period of the training skills is controlled by the **Retry after** parameter. The skill is deleted after a period specified in days in the **Retry after** field, if the Toloker:

- Has a skill value lower than the one specified in the **Level required** field.

- Didn't complete any tasks linked to training during this period.

Your users will need to be trained again.

{% endcut %}

{% cut "Why is my project not available in the mobile version of Toloka?" %}

Tasks in pools are automatically available in the web version of Toloka and the mobile app. Check the pool settings. You might have the `Client = Toloka web version`[filter](../concepts/filters.md) on.

{% endcut %}

### Quality control {#quality-control}

{% cut "I set up quality control, then I copied my user requirements. All my quality control settings were deleted and replaced with the copied settings. Is that normal?" %}

Yes. When you copy the filter and quality control settings, the settings you previously added manually are overwritten. You should see a warning about this in the copy settings window.

{% endcut %}

{% cut "I created a training pool with one task containing a hint. The Toloker fails to complete the task on the first attempt, but finally succeeds. The Toloker gets the skill `0`. How do I grant to the Toloker access to my tasks? The minimum required level that you can set is `10`." %}

Technically, if you have only one task in your training pool, you don't have this option. The skill will be either `0` or `100`. We recommend that you add several tasks, or at least 2 so that the Toloker will practice on the first task and will be able to do the second task correctly. In this case, you can admit users to your main pool starting from the skill value of `50`.

You can also create a training pool based on the main pool. Assign a skill using the [Control tasks](../concepts/goldenset.md) rule: in this case, you can admit users with any skill level to your main pool, even if the value is zero. But we don't advise giving tasks to people who failed training.

{% endcut %}

{% cut "When I export a project from the Sandbox, the task files are not exported. Is this how it's supposed to work? I suddenly lost the markup of the control tasks that I created in the sandbox." %}

The tasks themselves are not exported, only the project configuration and the settings of the selected pool. However, you can download your marked up tasks from the **Sandbox** pool and import them to the pool you created. To download the control tasks only (if you marked them up in the interface), go to **Mark up**, then click **Control tasks** and **Download**.

{% endcut %}

{% cut "I want to create an exam with three tasks. If a user does two out of three tasks correctly, they get the skill. So I try to use `3` in the **Recent control task responses to use** field, but I get an error that the value is too small. Can I get around this without increasing the number of tasks to five?" %}

The **Recent control task responses to use** field is for the number of recent responses from the Toloker. If you use non-automatic acceptance for your task, then to set up your intended rule you need to specify `3` in **Total reviewed responses**.

{% endcut %}

{% cut "I want to create training and exam pools to match the entered text against a sample, and sometimes the matching fails. How do I implement this?" %}

For a control or training assignment to be counted as correct, it must exactly match the control assignment. To do this, you need to normalize the response text using JavaScript: remove spaces, punctuation marks, special characters, and capital letters, and write the result in a separate output field. Now you can match the processed assignment text against your control text.

Another option for selecting Tolokers for a project of this type is assignment review (non-automatic acceptance).

{% endcut %}

{% cut "Why has the speed of pool completion dropped?" %}

Possible reasons:

- You've stopped the [main pool](../../glossary.md#training-pool). This could limit the number of Tolokers with access to the pool. Start the training pool again. There will be more Tolokers who can access the tasks.

- The filters you set are too strict. For example, a strong restriction on a certain skill that most users don't have.

- Too many users are banned. Ease the quality control rules.

{% endcut %}

### Overlap {#overlap}

{% cut "Why is the maximum number of submitted assignments in the progress bar less than the total number of uploaded tasks?" %}

The progress bar shows the number of task suites including the overlap. If the overlap is greater than one, the number of task suites is different from the total number of tasks.

{% endcut %}

## Adding tasks to a pool {#add-task-to-pool}

### Uploading tasks {#concept_iy1_3kh_5mb}

{% include [troubleshooting-preview-all-photos](../_includes/troubleshooting/adding-tasks-to-the-pool/preview-all-photos.md) %}

{% include [troubleshooting-commas-inside-array](../_includes/troubleshooting/adding-tasks-to-the-pool/commas-inside-array.md) %}

{% include [troubleshooting-double-quotas-disappear](../_includes/troubleshooting/adding-tasks-to-the-pool/double-quotas-disappear.md) %}

{% include [troubleshooting-marked-as-training](../_includes/troubleshooting/adding-tasks-to-the-pool/marked-as-training.md) %}

{% include [troubleshooting-syntax-error](../_includes/troubleshooting/adding-tasks-to-the-pool/syntax-error.md) %}

{% include [troubleshooting-photos-split-across-pages](../_includes/troubleshooting/adding-tasks-to-the-pool/photos-split-across-pages.md) %}

{% include [troubleshooting-uploading-tasks-errors](../_includes/troubleshooting/adding-tasks-to-the-pool/uploading-tasks-errors.md) %}

{% include [troubleshooting-same-task-on-different-pages](../_includes/troubleshooting/adding-tasks-to-the-pool/same-task-on-different-pages.md) %}

### Training-exam-retry {#concept_i2g_kkh_5mb}

{% include [troubleshooting-more-tolokers-trained](../_includes/troubleshooting/adding-tasks-to-the-pool/more-tolokers-trained.md) %}

{% include [troubleshooting-infinite-number.md](../_includes/troubleshooting/adding-tasks-to-the-pool/infinite-number.md) %}

{% include [faq-distribute-tasks-training](../_includes/faq/adding-tasks-to-the-pool/distribute-tasks-training.md) %}

### Changing a running pool {#concept_olz_kkh_5mb}

{% include [faq-delete-one-of-file](../_includes/faq/adding-tasks-to-the-pool/delete-one-of-file.md) %}

## Working with results {#result-questions}

### Aggregation {#results}

{% include [troubleshooting-dawid-skene-result](../_includes/troubleshooting/result-questions/dawid-skene-result.md) %}

{% include [troubleshooting-skill-unavailable](../_includes/troubleshooting/result-questions/skill-unavailable.md) %}

{% include [troubleshooting-cant-aggregate-by-skill](../_includes/troubleshooting/result-questions/cant-aggregate-by-skill.md) %}

### Processing the results file {#results_1}

{% include [troubleshooting-blank-spaces](../_includes/troubleshooting/result-questions/blank-spaces.md) %}

### Assignment review {#results_2}

{% include [troubleshooting-low-rating-instructions](../_includes/troubleshooting/result-questions/low-rating-instructions.md) %}

{% include [troubleshooting-low-rating-interface](../_includes/troubleshooting/result-questions/low-rating-interface.md) %}

{% include [troubleshooting-low-rating-communication](../_includes/troubleshooting/result-questions/low-rating-communication.md) %}

## Payments {#finance}

### Adding funds to your account {#concept-1}

{% include [troubleshooting-amount-greater-than-planned](../_includes/troubleshooting/finance/amount-greater-than-planned.md) %}

[Get closing documents and invoices](support.md)

[Refund money transferred to the Toloka account](support.md)

## Tolokers {#annotators}

### Data about Tolokers {#user-info}

{% cut "More than 500 Tolokers passed the training, but the training skill shows only 30." %}

The pool shows the total number of Tolokers that completed at least one assignment. A training skill can be lost over time if you set repeated training in the pool settings. This setting allows a Toloker to pass the training again after a certain period if the Toloker didn't complete any tasks in associated pools or if there was a large time gap between completing tasks (for example, because of the [ban](../../glossary.md#banning-tolokers)). The training skill displays the Tolokers who either recently completed training, or regularly complete your tasks so that the skill doesn't expire.

{% endcut %}

### Cheaters {#cheaters}

{% cut "Tolokers completed the training successfully, but have poor results in the general task" %}

During the training, Tolokers follow the task instructions and practice completing your tasks. Based on the training results, the requester can select Tolokers who did well enough to get access to the main pool. However, the mere fact that the Toloker completes your training pool successfully does not guarantee that they will continue to demonstrate high-quality performance. Tolokers who did well on the training but had inadequate results in the general task might have obtained correct training responses from other people.

In addition to the training, be sure to set up [quality control rules](../concepts/control.md) in your main pools. This lets you control the quality throughout the task completion process. If the task requires that users send free-format responses or data files, use [non-automatic acceptance](../concepts/offline-accept.md) to pay for them only after reviewing the responses.

{% endcut %}

{% cut "The results include the responses of users who I banned" %}

The results show the responses of all users, including those who are banned. To exclude their responses from the results, select the option **Exclude assignments by banned users**. It will delete the responses from users who were banned at the moment the results were downloaded, not when the pool was labeled.

{% endcut %}

{% cut "My project has a trusted Toloker who was banned by the system" %}

Unfortunately, this Toloker has violated the Toloker agreement and will no longer be able to complete tasks. You can find new Tolokers or customize [filters](../concepts/filters.md) so that they better match the project requirements.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}