# Project 2. Select an object in the image

In this [project](../../glossary.md#project), Tolokers will select image areas that contain a traffic sign. Use the results from [project 1](image-segmentation-project1.md) as source images.

## Create a project {#create-project}

#### In the interface:

1. Choose a preset:

    1. Click **Create project**.
    1. Select the **Object recognition & detection** preset.
    1. Click **Choose this preset**.

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

        1. To see the input and output data fields, click **Show specifications** in the **Data specification** section.

            - Input data field: `image` — A link to an image.

            - Output data field: `result` — The field that will contain the information about the labeled image after it is uploaded.

    - HTML/CSS/JS editor

        1. In **Task interface**, leave the **HTML** block unchanged.

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

        1. Click the ![](../_images/tutorials/image-segmentation/preview-button.svg) **Preview task** button to view the task.

            {% note info %}

            The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

            {% endnote %}

        1. In the window that opens, check if the task options work correctly. In the lower-right corner, click **Submit**.

        1. Exit preview mode. In the lower-left corner, click **Exit**. If there were errors when testing, check the code blocks that you entered.

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

1. Click **Add a pool** on the project page.

1. {% include [toloka-requester-pool-type](../../../_includes/toloka-requester-source/id-toloka-requester-source/pool-type.md) %}

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. {% include [tutorials-language-filter](../_includes/tutorials/language-filter.md) %}

    1. {% include [tutorials-shocking-content](../_includes/tutorials/shocking-content-filter.md) %}

    1. {% include [tutorials-platform-filter](../_includes/tutorials/platform-filter.md) %}

    1. Add a new skill. Click **Add skill**.

    1. In the window that opens, enter `Area selection` in the **Title** field.

    1. Click **Add**.

1. (optional) In the **Speed/quality balance** section, specify the desired quality level. Improving quality may reduce the speed of task completion because the pool will be available to fewer Tolokers. Learn more in the [Speed/quality balance](adjust.md) section.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite, $**, set the amount of money to pay per task suite done by one Toloker. For example, `0.01`.

        {% cut "What is a task suite?" %}

        A task suite can contain one or several tasks that are shown on the same page. If the tasks are simple, you can add 10–20 tasks per suite. Don't make task suites too long because it slows down loading speed for Tolokers.

        Tolokers get paid for completing the entire task suite.

        The number of tasks per suite is set when uploading tasks.

        {% endcut %}

        {% cut "What is a fair price for a task suite?" %}

        The general rule of pricing is the more time the Toloker spends to complete the task, the higher the price is.

        You can register in Toloka as a Toloker and find out how much other requesters pay for tasks.

        {% endcut %}

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        For image area selection tasks, it is usually `1`.

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. Turn on the **Review task responses manually** option.

        {% cut "What is manual review?" %}

        The [manual review](offline-accept.md) option allows you to review [completed assignments](../../glossary.md#completed-tasks) before accepting them and paying for them. If the Toloker didn't follow instructions, you can reject the assignment. The maximum allowed period for the review is set in the **Deadline** field.

        {% endcut %}

        In the **Review period in days** field, specify the number of days for checking the task.

    1. Add the following quality control rules:

        - **Recompletion of rejected assignments** — sends the tasks you rejected to other Tolokers according to the specified rules.

            1. Click **Add a quality control rule**.

            1. Find the **Rules** block in the list and select **Processing rejected and accepted assignments**.

            1. Set a rule for a rejected task: if **assignment becomes rejected**, then **extend overlap by** **1**. Turn on the **Open pool if closed** option.

                This means that the rejected task will be returned to the pool and shown to another Toloker.

        - **Submitted responses** — allows you to limit the number of pool tasks available for the Toloker per day.

            1. Click **Add a quality control rule**.

            1. Find **Rules** block in the list and choose **Submitted responses**.

            1. Set a rule for the completed task: if **submitted assignments** **≥ 1**, then **assign skill value** **Area selection** equal to **1**.

                These parameters allow you to mark the Toloker who completed at least one task in the pool.

                {% note tip %}

                If the **Area selection** skill isn't displayed in the list, save the pool and reopen it for editing.

                {% endnote %}

        - **Fast responses** —Filters out Tolokers who respond too quickly.

            1. Click **Add a quality control rule**.

            1. Find the **Rules** block in the list and choose **Fast responses**.

            1. In the **Recent tasks suites to use** field, enter the number of recent task suites submitted by the Toloker. For example, `5`.

            1. In the **Minimum time per task suite** field, enter the time in seconds. For example, `20`.

            1. Set a rule for a fast response: if the **number of fast responses** **≥ 1**, then **ban** **on requester** for **10 days**. In the **Reason** field, enter **Fast responses**.

                This means that a user who completes a [task suite](../../glossary.md#task-suite) in less than 20 seconds will be suspended for 10 days and won't be able to access your tasks.

        - **Results of assignment review** — restricts the pool access for Tolokers who often make mistakes.

            1. Click **Add a quality control rule**.

            1. Find the **Rules** block in the list and choose **Results of assignment review**.

            1. Set a rule for rejected tasks: if **total reviewed responses** **≥ 3** and **rejected responses (%)** **> 35**, then  **ban**  **on requester** for  **15 days**.

                This means that if 35% or more of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

        [Control tasks](../../glossary.md#control-task) and [majority vote](../../glossary.md#majority-vote) aren't used for this project type, since the area markup provided by the Tolokers must match (which is almost impossible). Learn more in [Quality control](control.md).

        {% note info %}

        You can copy quality control settings from another pool. To do this, in the **Tolokers** section of the **Audience** block, click **copy them from another pool**.

        {% endnote %}

1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

    The time should be long enough to read the instructions and wait for task data to load. For example, `1200` seconds.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

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

        1. Click **Drop file here or select**, and upload the file you’ve just made.

        1. Click **Continue**.

        1. Choose **Set manually**.

        1. In the **Tasks per suite** field, specify `1`.

        1. Click **Combine tasks into suites**.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

1. Click ![](../_images/other/b-start-pool.svg) to start the pool.

## Get the results {#get-results}

1. On the pool page, click **Download results**. In the window that opens:

    1. In **Status** leave only the **Submitted** option enabled.

    1. In **Columns** leave only the **assignment ID** option enabled.

    1. Disable the **Separate assignments with empty row** option.

    1. Click **Download results**.

1. Use the results file in [project 3](image-segmentation-project3.md).

## What's next {#what-next}

- Create [Project 3](image-segmentation-project3.md) to review assignments.

{% include [contact-support](../_includes/contact-support.md) %}