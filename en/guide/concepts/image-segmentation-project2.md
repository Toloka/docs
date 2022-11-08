# Project 2. Select an object in the image

In this [project](../../glossary.md#project), Tolokers will select image areas that contain a traffic sign. Use the results from [project 1](image-segmentation-project1.md) as source images.

## Create a project {#create-project}

#### In the interface:

1. Choose a template:

    1. Click **Create project**.
    1. Select the **Object recognition & detection** template.
    1. Click **Choose solution**.

1. Provide general information:

    1. In **Name to show Tolokers**, enter `Outline traffic signs in the image`.
    1. In **Description for Tolokers**, enter `Draw a box around all traffic signs in the image`.
    1. Optionally add a **Private comment**.

1. Edit the task interface in the editor you selected:

    {% list tabs %}

    - Template Builder

        1. You can use it for this project with pre-configured validation and task layout.

            The Toloker won't be able to submit a response without selecting an area in an image.

            For more information about the template and its settings, see [Object selection in an image](../../template-builder/operations/select-areas.md) in the Template Builder Help.

        1. To see the input and output data fields, click {% if locale == "en-com" %}**Show specifications**{% endif %} in the {% if locale == "en-com" %}**Data specification**{% endif %} section.

            - Input data field: `image` — A link to an image.

            - Output data field: `result` — The field that will contain the information about the labeled image after it is uploaded.

    - HTML/CSS/JS editor

        1. In {% if locale == "en-com" %}**Task interface**{% endif %}, leave the **HTML** block unchanged.

        1. Edit the **CSS** block:

            1. Set up the area selection tools. This template uses [Editor for image area selection](t-components/image-annotation.md). It features rectangle and polygon tools (by default).

                To set up rectangle selection, replace the code in the **CSS** block with the following:

                ```css
                .image-annotation-editor__shape-polygon {
                display: none;
                }
                ```

            1. Enter the code to adjust the interface height to the image size:

                ```css
                .image-annotation-editor__annotation-layer {
                height: max-content;
                }
                ```

            1. **(optional)** You can ask Tolokers to enter an annotation for the selected area or select one from a list. To do this, add an interface element in the **JS** block. For example, a text field or drop-down list.

                Learn more about [annotation](t-components/image-annotation.md#annotation).

        1. Click the ![](../_images/tutorials/image-segmentation/preview-button.svg) {% if locale == "en-com" %}**Preview task**{% endif %} button to view the task.

            {% note info %}

            The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

            {% endnote %}

        1. In the window that opens, check if the task options work correctly. In the lower-right corner, click {% if locale == "en-com" %}**Submit**{% endif %}.

        1. Exit preview mode. In the lower-left corner, click {% if locale == "en-com" %}**Exit**{% endif %}. If there were errors when testing, check the code blocks that you entered.

    {% endlist %}

1. Save the changes.

1. Write instructions for Tolokers:

    #### Instructions text:

    Click ![](../_images/tutorials/image-segmentation/rectangle-button.png) and draw a rectangle around all traffic signs in the image.

    {% note tip %}

    If you want to add a task examples in the instruction, complete it yourself in the preview mode. Take screenshots, upload them to photo hosting or cloud storage and insert image links in the instructions by clicking the ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button.svg) button on the toolbar.

    {% endnote %}

    Click **Finish**.

## Create a pool {#create-pool}

A pool is a set of paid tasks sent out for completion at the same time.

1. Open the project page **Outline the traffic signs in the image**.

1. Click the {% if locale == "en-com" %}**Add a pool**{% endif %} button.

1. Specify the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. Optionally add a {% if locale == "en-com" %}**Private comment**{% endif %}. This information is available only to you.

1. Filter Tolokers in the {% if locale == "en-com" %}**Tolokers**{% endif %} section of the {% if locale == "en-com" %}**Audience**{% endif %} block:

    1. Click {% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Add the {% if locale == "en-com" %}**Region by phone number**{% endif %} and {% if locale == "en-com" %}**Languages**{% endif %} filters and select Tolokers from Russia, Ukraine, Kazakhstan, and Belarus who indicated in their profiles that they know Russian.

    1. Add a new skill. Click {% if locale == "en-com" %}**Add skill**{% endif %}.

    1. In the window that opens, enter `Area selection` in the {% if locale == "en-com" %}**Title**{% endif %} field.

    1. Click {% if locale == "en-com" %}**Add**{% endif %}.

    Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

1. (optional) In the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} section, specify the desired quality level. Improving quality may reduce the speed of task completion because the pool will be available to fewer Tolokers. Learn more in the [Speed/quality balance](adjust.md) section.

1. In the {% if locale == "en-com" %}**Price**{% endif %} block, find the {% if locale == "en-com" %}**Price per task suite**{% endif %} field and specify the price. For example, `0.01`.

    {% cut "What is a task suite?" %}

    A task suite can contain one or several tasks that are shown on the same page. If the tasks are simple, you can add 10–20 tasks per suite. Don't make task suites too long because it slows down loading speed for Tolokers.

    Tolokers get paid for completing the entire task suite.

    The number of tasks per suite is set when uploading tasks.

    {% endcut %}

    {% cut "What is a fair price for a task suite?" %}

    The general rule of pricing is the more time the Toloker spends to complete the task, the higher the price is.

    You can register in Toloka as a Toloker and find out how much other requesters pay for tasks.

    {% endcut %}

1. [Quality control rules](control.md) allow you to filter out careless Tolokers. In the {% if locale == "en-com" %}**Quality control**{% endif %} block, set the rules for the pool:

    1. Turn on the {% if locale == "en-com" %}**Assignment review**{% endif %} option.

        {% cut "What is non-automatic acceptance (assignment review)?" %}

        The [non-automatic acceptance](offline-accept.md) option allows you to review [completed assignments](../../glossary.md#completed-tasks) before accepting them and paying for them. If the Toloker didn't follow instructions, you can reject the assignment. The maximum allowed period for the review is set in the **Deadline** field.

        {% endcut %}

        In the {% if locale == "en-com" %}**Review period in days**{% endif %} field, specify the number of days for checking the task.

    1. Add the following quality control rules:

        - {% if locale == "en-com" %}**Recompletion of rejected assignments**{% endif %} — sends the tasks you rejected to other Tolokers according to the specified rules.

            1. Click {% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

            1. Find the {% if locale == "en-com" %}**Rules**{% endif %} block in the list and select {% if locale == "en-com" %}**Processing rejected and accepted assignments**{% endif %}.

            1. Set a rule for a rejected task: if {% if locale == "en-com" %}**assignment becomes rejected**{% endif %}, then {% if locale == "en-com" %}**extend overlap by**{% endif %} **1**. Turn on the {% if locale == "en-com" %}**Open pool if closed**{% endif %} option.

                This means that the rejected task will be returned to the pool and shown to another Toloker.

        - {% if locale == "en-com" %}**Submitted responses**{% endif %} — allows you to limit the number of pool tasks available for the Toloker per day.

            1. Click {% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

            1. Find {% if locale == "en-com" %}**Rules**{% endif %} block in the list and choose {% if locale == "en-com" %}**Submitted responses**{% endif %}.

            1. Set a rule for the completed task: if {% if locale == "en-com" %}**submitted assignments**{% endif %} **≥ 1**, then {% if locale == "en-com" %}**assign skill value**{% endif %} **Area selection** equal to **1**.

                These parameters allow you to mark the Toloker who completed at least one task in the pool.

                {% note tip %}

                If the **Area selection** skill isn't displayed in the list, save the pool and reopen it for editing.

                {% endnote %}

        - {% if locale == "en-com" %}**Fast responses**{% endif %} —Filters out Tolokers who respond too quickly.

            1. Click {% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

            1. Find the {% if locale == "en-com" %}**Rules**{% endif %} block in the list and choose {% if locale == "en-com" %}**Fast responses**{% endif %}.

            1. In the {% if locale == "en-com" %}**Recent tasks suites to use**{% endif %} field, enter the number of recent task suites submitted by the Toloker. For example, `5`.

            1. In the {% if locale == "en-com" %}**Minimum time per task suite**{% endif %} field, enter the time in seconds. For example, `20`.

            1. Set a rule for a fast response: if the {% if locale == "en-com" %}**number of fast responses**{% endif %} **≥ 1**, then {% if locale == "en-com" %}**ban**{% endif %} {% if locale == "en-com" %}**on requester**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. In the {% if locale == "en-com" %}**Reason**{% endif %} field, enter **Fast responses**.

                This means that a user who completes a [task suite](../../glossary.md#task-suite) in less than 20 seconds will be suspended for 10 days and won't be able to access your tasks.

        - {% if locale == "en-com" %}**Results of assignment review**{% endif %} — restricts the pool access for Tolokers who often make mistakes.

            1. Click {% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

            1. Find the {% if locale == "en-com" %}**Rules**{% endif %} block in the list and choose {% if locale == "en-com" %}**Results of assignment review**{% endif %}.

            1. Set a rule for rejected tasks: if {% if locale == "en-com" %}**total reviewed responses**{% endif %} **≥ 3** and {% if locale == "en-com" %}**rejected responses (%)**{% endif %} **> 35**, then {% if locale == "en-com" %} **ban**{% endif %} {% if locale == "en-com" %} **on requester**{% endif %} for {% if locale == "en-com" %} **15 days**{% endif %}.

                This means that if 35% or more of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

        [Control tasks](../../glossary.md#control-task) and [majority vote](../../glossary.md#majority-vote) aren't used for this project type, since the area markup provided by the Tolokers must match (which is almost impossible). Learn more in [Quality control](control.md).

        {% note info %}

        You can copy quality control settings from another pool. To do this, in the {% if locale == "en-com" %}**Tolokers**{% endif %} section of the {% if locale == "en-com" %}**Audience**{% endif %} block, click {% if locale == "en-com" %}**copy them from another pool**{% endif %}.

        {% endnote %}

1. In the {% if locale == "en-com" %}**Task overlap**{% endif %} section, find the {% if locale == "en-com" %}**The number of Tolokers to complete every task**{% endif %} field and set the overlap, which is the number of Tolokers to complete the same task. For image area selection tasks, it is usually `1`.

1. In the {% if locale == "en-com" %}**Additional settings**{% endif %} block, specify {% if locale == "en-com" %}**Time per task suite**{% endif %}. The time should be long enough to read the instructions and wait for task data to load. For example, `1200` seconds.

1. Click {% if locale == "en-com" %}**Create a pool**{% endif %}.

## Prepare and upload tasks {#upload-file}

1. Prepare a [file](../../glossary.md#tsv) with tasks.

    1. In the text or spreadsheet editor, open the file that you received after aggregating the results in [project 1](image-segmentation-project1.md).

    1. Choose images appropriate for the current project (the **OK** value).

        {% note tip %}

        You can use the awk commands to outline images on Linux and MacOS devices:

        ```shell
        awk 'BEGIN {OFS = FS = "\t";} $2=/OK/ {print $1}' <aggregated_res>.tsv > <filtered_res>.tsv
        ```

        {% endnote %}

    1. Copy the column with the selected links to a new sheet or document.

    1. Name it `INPUT:image`. If you want to set a different name, rename the column in the source file with the results, too.

    1. Save the file.

1. Upload the tasks file:

    1. Click {% if locale == "en-com" %}**Upload**{% endif %}. In the window that opens, configure the file upload settings.

    1. Choose {% if locale == "en-com" %}**Set manually**{% endif %}.

    1. In the {% if locale == "en-com" %}**Tasks per suite**{% endif %} field, specify `1`.

    1. Click {% if locale == "en-com" %}**Upload**{% endif %}.

    1. In the window that opens, choose the tasks file you want to upload and click {% if locale == "en-com" %}**Open**{% endif %}.

    1. In the window that opens, check the number of tasks and click {% if locale == "en-com" %}**Add**{% endif %}.

1. Click ![](../_images/other/b-start-pool.svg) to start the pool.

    {% note warning %}

    The tasks will be completed by real Tolokers in Toloka. Recheck your project setup before you start the pool.

    {% endnote %}

## Get the results {#get-results}

1. On the pool page, click {% if locale == "en-com" %}**Download results**{% endif %}. In the window that opens:

    1. In {% if locale == "en-com" %}**Status**{% endif %} leave only the {% if locale == "en-com" %}**Submitted**{% endif %} option enabled.

    1. In {% if locale == "en-com" %}**Columns**{% endif %} leave only the {% if locale == "en-com" %}**assignment ID**{% endif %} option enabled.

    1. Disable the {% if locale == "en-com" %}**Separate assignments with empty row**{% endif %} option.

    1. Click {% if locale == "en-com" %}**Download results**{% endif %}.

1. Use the results file in [project 3](image-segmentation-project3.md).

## What's next {#what-next}

- Create [Project 3](image-segmentation-project3.md) to review assignments.

{% include [contact-support](../_includes/contact-support-help.md) %}