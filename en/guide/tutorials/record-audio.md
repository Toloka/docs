# Voice recording

In this tutorial, you will learn how to run voice recording in Toloka. We will use a project preset designed specifically for this type of data labeling.

Voice recording is a type of data labeling task with the text block to read and the voice recorder button. Using the Toloka mobile app, Tolokers should tap the button and read the text aloud. After getting the results, you can listen to the recordings and download them.

{% note info %}

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](../concepts/solution-architecture.md).

{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Create a project {#project}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ voice-recording-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Click **Do it myself**.

    1. Select the **Voice recording** preset.

1. Click **Choose this preset** in the pop-up tab.

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    ![Create a project. Step 1](../_images/tutorials/record-audio/voice-recording-create-project-step-1.png =700x)

1. In the **Task interface** section, set up what your tasks will look like. This preset has a task template with layout and validation pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. In the **Config** section, you can edit the code to change the appearance and layout of the task elements. For a trial pool, keep the code as is.

        To learn about the properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/reference/index.md).

    1. In the **Input data example** section, you can change the sample text. This text is only used to display the task interface preview on the right.

        ![Create a project. Input data example](../_images/tutorials/record-audio/voice-recording-input-example.png =700x)

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - **Input data**: Parameters in the file with raw task data.

        - **Output data**: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. {% include [save-project](../_includes/tutorials/save-project.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click **Create new pool** on the project page.

1. {% include [toloka-requester-pool-type](../_includes/toloka-requester-source/id-toloka-requester-source/pool-type.md) %}

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        1. For example, add the **Languages** filter:

            ![Create a pool. Languages filter](../_images/tutorials/record-audio/voice-recording-language-filter.png =700x)

        1. It is best to launch voice recording tasks in the Toloka mobile app so that Tolokers can record audio directly in a task using the device's built-in voice recorder. Add the **Client** filter and select **Toloka for mobile**.

    1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. Click the **Review task responses manually** toggle, and specify the number of days for checking the task in the **Review period in days** field (for example, 21).

        {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

    1. The **Voice recording** preset has the pre-configured quality control rules:

        - In most cases, you can keep the **Fast responses** rule as is. It filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they complete tasks in 4 out of 5 task suites in less than 15 seconds.

        - Delete the pre-configured **Majority vote** rule.

    1. For a trial pool, the settings you’ve just made are enough. You can get better results if you set the additional quality control rules.

        {% cut "The additional quality control rules" %}

        1. Add the **Results of assignment review** quality control rule and enter the following values:

            ![Create a pool. Results of assignment review](../_images/tutorials/record-audio/voice-recording-offline-accept.png =700x)

            This means that if 35% or more of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

        1. Add the [Processing rejected and accepted assignments](../concepts/reassessment-after-accepting.md) rule:

            ![Create a pool. Processing rejected and accepted assignments](../_images/tutorials/record-audio/record-audio-rejected.png =700x)

            This means that if you reject assignments during the review, they'll be sent for re-completion to another Toloker.

        {% endcut %}

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite**, set the amount of money to pay per task suite done by one Toloker.

        A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 8–10 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        The value depends on how many recordings of the same phrase you want to collect. If one is enough, set `1`.

    1. At the bottom of the **Price** section, you see **Price per 1 task**. This is the amount of money paid per task.

1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

    This time should be enough to read the instructions and load the task (for example, 1,200 seconds).

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

    1. Create the tasks for Tolokers:

        1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

            For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:text`, and the values are texts.

            ```plaintext
            INPUT:text
            Does white chocolate have cocoa?
            How many rings are there in the Olympic Games symbol?
            What is the capital of Australia?
            ```

        1. Open the downloaded file, and replace the sample values with your texts.

        1. Click **Drop file here or select**, and upload the file you’ve just made.

        1. Click **Continue**.

    1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

        - **General tasks**: These are tasks for Tolokers to label.

        - **Control tasks**: These are tasks with predefined answers used to control the quality of responses. For this project, you don’t need control tasks.

        - **Training tasks**: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

        For example, you can add 5 general tasks per suite:

        ![Upload data. Tasks per suite](../_images/tutorials/record-audio/voice-recording-upload-data.png =700x)

    1. Click **Combine tasks into suites**.

1. {% include [tutorials-double-check](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

{% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    ![Start labeling. Step 2](../_images/tutorials/record-audio/voice-recording-start-labeling-step-2.png =700x)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

Track the labeling progress on the pool page. You can start the review when the first results are received.

After the time period specified in step 4.1 of [creating the pool](#pool), all responses are automatically accepted, regardless of their quality.

1. Go to the pool, and click **Review assignments**.

    ![See the results. Step 1](../_images/tutorials/record-audio/voice-recording-review-results.png =700x)

1. Choose an assignment.

1. Check the responses, and click **Accept** or **Decline**. For rejected responses, enter a comment to specify the reason.

    {% note info %}

    To learn about other ways of review, see the [Reviewing Tolokers' responses](../concepts/accept.md) section.

    {% endnote %}

1. After checking all the assignments, click **Download results**.

    ![See the results. Download results](../_images/tutorials/record-audio/voice-recording-results-download.png =700x)

    You will get the TSV file with the labeling results.

1. To download the recordings, click the arrow next to the **Download results** button. Choose **Download attachments** from the drop-down menu.

    ![See the results. Download attachments](../_images/tutorials/record-audio/voice-recording-download-attachments.png =700x)

## Troubleshooting {#troubleshooting}

{% cut "How do I show two different versions of the text to Tolokers?" %}

If you pass texts to the input data, you can upload 2 different tasks to the pool: pass Text 1 in the `INPUT: <input field name>` field of Task 1. In Task 2, use this field to pass Text 2.

If the text is specified in the task interface, then clone the project. To limit a Toloker to doing only one task in your project, use the [Submitted responses](../concepts/submitted-answers.md) rule. You can assign a skill or ban the Toloker after they submit one response.

{% endcut %}

{% cut "How do I make an image expand to its maximum size on click?" %}

The `popup` property of the component [view.image](../../template-builder/reference/view.image.md) specifies whether opening a full-size image with a click is allowed. By default, it is `true` (allowed).

{% endcut %}

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}