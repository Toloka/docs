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

{% include [troubleshooting-tags-disappear](../_includes/troubleshooting/project-settings/tags-disappear.md) %}

{% cut "What do I do if the radio button attributes are displayed correctly in the preview, but disappear after saving?" %}

If the tags or attributes disappear after you save the instructions (for example, `checked="true"`), it means that they are not supported. For the full list of tags that can be used in the instructions, see the [Guide](../concepts/instruction.md#html-yes).

{% endcut %}

### Configuring the task interface {#concept_gss_fkp_smb}

{% include [troubleshooting-cant-upoad-file](../_includes/troubleshooting/project-settings/cant-upoad-file.md) %}

{% include [troubleshooting-iframe-content](../_includes/troubleshooting/project-settings/iframe-content.md) %}

{% include [troubleshooting-all-checkboxes](../_includes/troubleshooting/project-settings/all-checkboxes.md) %}

{% include [troubleshooting-submit-doesnt-work](../_includes/troubleshooting/project-settings/submit-doesnt-work.md) %}

{% include [faq-no-selectable-object](../_includes/faq/project-settings/no-selectable-object.md) %}

## Setting up a pool {#pool-settings}

{% cut "I created a project and a pool, but the Next button doesn't work or the preview shows a blank screen." %}

Toloka lets you know that something is wrong with the project. The blank screen often appears when there are errors in the [task interface](../../glossary.md#task-interface), including the JavaScript code. The **Next** button may be disabled if the output specification lacks some field or contains invalid values, or if, for example, you configured validation for a nonexistent field in JavaScript.

{% endcut %}

## Filters {#filters}

{% include [troubleshooting-cloned-pool](../_includes/troubleshooting/pool-setup/cloned-pool.md) %}

{% include [troubleshooting-mobile-unavailable](../_includes/troubleshooting/pool-setup/mobile-unavailable.md) %}

### Quality control {#quality-control}

{% include [troubleshooting-control-settings-replaced](../_includes/troubleshooting/pool-setup/control-settings-replaced.md) %}

{% include [troubleshooting-hint](../_includes/troubleshooting/pool-setup/hint.md) %}

{% include [troubleshooting-export](../_includes/troubleshooting/pool-setup/export.md) %}

{% include [troubleshooting-exam-three-tasks](../_includes/troubleshooting/pool-setup/exam-three-tasks.md) %}

{% cut "I want to create training and exam pools to match the entered text against a sample, and sometimes the matching fails. How do I implement this?" %}

For a control or training assignment to be counted as correct, it must exactly match the control assignment. To do this, you need to normalize the response text using JavaScript: remove spaces, punctuation marks, special characters, and capital letters, and write the result in a separate output field. Now you can match the processed assignment text against your control text.

Another option for selecting Tolokers for a project of this type is assignment review (non-automatic acceptance).

{% endcut %}

{% include [troubleshooting-speed-dropped](../_includes/troubleshooting/pool-setup/speed-dropped.md) %}

### Overlap {#overlap}

{% include [troubleshooting-max-number](../_includes/troubleshooting/pool-setup/max-number.md) %}

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

{% include [troubleshooting-infinite-number](../_includes/troubleshooting/adding-tasks-to-the-pool/infinite-number.md) %}

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

{% include [troubleshooting-pool-archived](../_includes/troubleshooting/result-questions/pool-archived.md) %}

{% include [troubleshooting-rejected-task](../_includes/troubleshooting/result-questions/rejected-task.md) %}

{% include [faq-increase-rating](../_includes/faq/result-questions/increase-rating.md) %}

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

{% include [troubleshooting-training](../_includes/troubleshooting/users/training.md) %}

### Cheaters {#cheaters}

{% include [troubleshooting-poor-results](../_includes/troubleshooting/users/poor-results.md) %}

{% include [troubleshooting-include-responses](../_includes/troubleshooting/users/include-responses.md) %}

{% include [troubleshooting-trusted-user-banned](../_includes/troubleshooting/users/trusted-user-banned.md) %}

{% include [contact-support](../_includes/contact-support.md) %}