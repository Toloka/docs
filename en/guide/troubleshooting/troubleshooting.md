# All questions on one page

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

#### If you aren't using Toloka yet and need advice

[Ask a question](support.md)

#### If you have a problem working with Toloka

In the section contents, select the stage where you encountered the problem and find the appropriate solution in the list. If not found, contact [support](support.md).

## Registration and getting started {#register-and-start}

{% cut "I can't complete registration as an “individual requester”. I'm not getting an SMS code." %}

1. Check the number you entered. You might have mistyped it.

1. Check the number in Yandex ID. It must be set as your main number. If a different number is specified in Yandex ID, an SMS code will be sent to that number.

You can also use the recommendations in [Yandex ID Help]({{ phone-problems_no-code }}). If this doesn't help, contact [support]({{ passport-support }}).

{% endcut %}

{% cut "The phone number belongs to another user" %}

If you see this warning, make sure you entered the phone number correctly.

Please note that you can only have one requester account per phone number (see the [User Agreement]({{ useragreement }})).

If your [Yandex ID]({{ phones }}) is linked to the wrong number, change it. For more information about linking a phone number, see [Yandex ID Help]({{ authorization-phone }}).

If you don't remember your credentials in Toloka, use [Restoring access]({{ restore }}).

If you deleted your Toloka account, create a new Yandex ID and register in Toloka.

{% endcut %}

## Sandbox {#sandbox}

{% cut "Why don't I see my task in the Sandbox?" %}

Make sure that:

1. The [pool](../../glossary.md#pool) is started.

1. The Toloker is added as a trusted user.

1. The trusted user is registered in the sandbox as a Toloker.

1. The trusted user didn't use social networks when registering.

1. Your trusted Toloker matches the [filters](../../glossary.md#filters) you set.

{% endcut %}

{% cut "What do I do if an error occurs on the server when I try to export a project from the Sandbox?" %}

#### Try exporting the project without pools.

Select an exported project and don't select pools in the window that opens.Click **Export**.

#### If the error persists, refresh the token.

Go to [ Yandex ID]({{ passport-profile }}).Under **Sign in and device history**, click **Log out from all devices**.Request new tokens in the Sandbox and main environment.Update the token in the [Sandbox]({{ sandbox-profile-integration }})**Profile **.

{% endcut %}

{% cut "Why isn't anything happening when a test Toloker clicks **Submit** in the sandbox?" %}

Use your requester account to preview the pool and check whether it's possible to submit a task. If this fails, most likely there is an error in your project.

{% endcut %}

{% cut "I can't add a trusted user." %}

Possible reasons:

- The Toloker isn't registered in the sandbox. The account you registered in the Toloka production version won't work. Make sure you have specified the correct _Toloker's_ account as a trusted one.

- The Toloker's account is authorized via social networks.[Register]({{ register }}) a new user in Yandex.

{% endcut %}

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

{% cut "Why does the preview display all the photos from the file with tasks at once?" %}

You must use a separate row for each task in your file with tasks. For more information, see [here](../concepts/pool_csv.md).

When you create a pool, the pool will have settings for the number of tasks per suite.

{% endcut %}

{% cut "The system interprets commas inside my array elements as separators between the array elements. How do I avoid this?" %}

Escape commas with a backslash (`\`).

{% endcut %}

{% cut "Why do double quotes disappear from the output if I try to escape them using quotation marks?" %}

If you have one word enclosed in quotes, format the uploaded assignment like this: `"How many letters are there in the word ""Liechtenstein"""`. If you are escaping quotes inside your text, then the entire text must be enclosed in quotes. For more information, see the [Guide](../concepts/pool_csv.md#string).

{% endcut %}

{% cut "Why haven't I received assignments since I launched my first project, and all the uploaded assignments are marked as "Training"?" %}

Check the `hint` field. For the general tasks, this field must be empty.

{% endcut %}

{% cut "Why do I see a syntax error when I upload a task where a user has to view an image and write feedback?" %}

The error might occur if the expected input type is URL, but a string is received.

There may be two reasons:

- The input field has the "link" type.

- The pool was created for an outdated project version. It means that the pool was created before you changed the input field type.

{% endcut %}

{% cut "I have a task for photo classification. When there are more than 5 photos on the page, why does Toloka split them across 2 pages?" %}

Toloka will split the links to images in the uploaded file into task suites depending on the method you specified when uploading the file. For more information, see the [Guide](../concepts/distribute-tasks-by-pages.md).

{% endcut %}

{% cut "Errors when uploading tasks in the pool" %}

#### Errors in column headers

If the [column headings](../concepts/pool_csv.md) are incorrect, the whole file is rejected. Otherwise, Toloka specifies the number of tasks with processing errors.

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
- String values with tab characters are enclosed in [quotation marks](../concepts/pool_csv.md#string) `" "`.
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

{% endcut %}

{% cut "The same task appeared on different pages" %}

The same task may appear on different pages if:

- Dynamic overlap is used (incremental relabeling, IRL). As an example, let's say there were 5 tasks on a page. For 4 of them, responses coincided and the common response was counted as correct. The fifth task was mixed into another set because it didn't get into the final response and it needs to be “reassessed”.

- Different tasks have different overlap. Tasks with higher overlap will be additionally shown in sets with the other remaining tasks in the pool.

- If a [quality control rule](../../glossary.md#quality-control-rule) changes a task's overlap, it will appear in a different set.

{% endcut %}

### Training-exam-retry {#concept_i2g_kkh_5mb}

{% cut "More Tolokers were trained than the training skill shows" %}

The pool shows the total number of Tolokers that completed at least one assignment. A training skill can be lost over time if you set [repeated training](../concepts/train.md) in the pool settings. This setting allows a Toloker to pass the training again after a certain period if the Toloker didn't complete any tasks in associated pools or if there was a large time gap between completing tasks (for example, because of a [ban](../../glossary.md#banning-tolokers)). The training skill displays the Tolokers who either recently completed training, or regularly complete your tasks so that the skill doesn't expire.

{% endcut %}

{% cut "Why do I have an infinite number of pages in the training pool?" %}

Tasks have infinite overlap in the training pool. As long as the training pool is open and the training is running, users can access the tasks. Learn more about [training pools](../concepts/train.md).

{% endcut %}

{% cut "Why is only Smart Mixing available in Training?" %}

This is a technical limitation of [training pools](../../glossary.md#training-pool). If you want to use the {% if locale == "en-com" %}**Set manually**{% endif %} option in the training, create the main pool, set the pool type as {% if locale == "en-com" %}**Training**{% endif %}, and set the cost to zero.

{% endcut %}

### Changing a running pool {#concept_olz_kkh_5mb}

{% cut "I uploaded two files to the training pool. How do I delete one of them?" %}

After uploading, all tasks are put into one list and can't be deleted separately.

- **If the pool hasn't started yet**, delete all tasks. To do this, click **Delete** in the **Pool tasks** block. Then upload one file to the pool.

- **If the pool already started**, delete tasks [one-by-one in markup mode](../concepts/task_markup.md#delete-task).

{% endcut %}

## Working with results {#result-questions}

### Aggregation {#results}

{% cut "Why does the Dawid-Skene aggregation model return a result that the Tolokers didn't select?" %}

The method doesn't guarantee that original Toloker responses will be used for aggregation. The algorithm takes into account Tolokers' quality parameters and response patterns. Consequently, it can return a result that's different from the Tolokers' responses to this task.

{% endcut %}

{% cut "Why might aggregation by Toloker skill be unavailable?" %}

You cannot aggregate by project fields that have no valid values. Specify the possible values for all the fields of all types.

{% endcut %}

{% cut "You can't aggregate by skill. When running via the API, I get the error code `ONLY_FOR_POOL_WITH_MIXER`. Why?" %}

You need to use [smart mixing](../concepts/task_upload.md#smart-mixing_1).

{% endcut %}

### Processing the results file {#results_1}

{% cut "Why do I get blank spaces inside my TSV file?" %}

When you upload a file with rows, double quotes indicate an area where you can use special characters (tabs or line breaks). Toloka merges everything in between the quotes into one row to make up one task. To use double quotes inside such an area, you need to escape them with another quote. [Read more here](../concepts/pool_csv.md#string).

{% endcut %}

### Assignment review {#results_2}

{% cut "Low rating for “Clarity of instructions”" %}

Shorten instructions and rewrite using simpler language. Add pictures and examples.

{% endcut %}

{% cut "Low rating for “Task interface usability”" %}

Make the interface [more user-friendly](../concepts/spec.md) and don't make the Toloker complete unnecessary actions. Use keyboard shortcuts.

Starting from December 15, 2021, tasks in pools are automatically available in the web version of Toloka and the mobile app. If your task isn't available on mobile devices, it means that you might have forgotten to add the {% if locale == "en-com" %}**Client**{% endif %} filter.

{% endcut %}

{% cut "Low rating for “Communication with the requester”" %}

Reply to [messages from Tolokers](../concepts/messaging.md) regularly. Try to provide feedback as fast as possible. Correct errors promptly and use mailing lists to notify Tolokers of changes.
If you don't understand what the problem is, run a mini-survey and ask the Tolokers who completed your tasks what they like and what they don't like.

{% endcut %}

## Payments {#finance}

### Adding funds to your account {#concept-1}

{% include [troubleshooting-amount-greater-than-planned](../_includes/troubleshooting/finance/amount-greater-than-planned.md) %}

{% include [faq-how-long-paying-invoice-take](../_includes/faq/finance/how-long-paying-invoice-take.md) %}

{% include [faq-currency-exchange-rate](../_includes/faq/finance/currency-exchange-rate.md) %}

{% include [faq-add-money](../_includes/faq/finance/add-money.md) %}

[Get closing documents and invoices](support.md)

### Refund {#concept-3}

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