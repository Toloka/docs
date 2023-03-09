# Video classification

In this tutorial, you will learn how to run video classification in Toloka. We will use a project preset designed specifically for this type of data labeling.

Video classification is a type of data labeling task with a video player and several response options. A Toloker watches the video clip and chooses one of the given response options.

You can use this type of project for:

- Content moderation.

- Sorting video clips by specified categories.

- Rating video clips based on how much the Tolokers like them.

- Detecting noise and other visual imperfections in the video.

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

- Upload your video clips to a storage from which you can get file links. For example, your own server, a video hosting, or a [cloud storage](../concepts/cloud-storage.md#cloud).

    {% note alert "Restriction" %}

    The video player supports only MP4 format with H.264 or H.265 encoding.

    {% endnote %}

- Make sure that the video clips look the same in the desktop and mobile versions of Toloka. A video clip may not play or play incorrectly in the mobile version. In this case, when creating a pool, you will need to restrict access to the pool for the Tolokers with mobile devices.

    Learn more about [configuring tasks for mobile devices](../concepts/mobile.md).

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ video-moderation-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the **Hand gesture classification** preset.

1. Click **Choose this preset** in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-create-project-step-1.png)

1. In the **Task interface** section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Using the **Visual editor**, add your data to the **Config** section:

        - **Question Tolokers will see in your task**: Write a question that matches the responses Tolokers need to choose from. All tasks in a project use the same question.

        - **Paste link to a sample video**: This video is only used to display the task interface preview on the right.

    1. **Set answer options** is pre-filled with sample answers. Replace the samples with your categories. Note that **Other** and **Error** are separate entities.

        - **Answer option for Tolokers**: This is the label that Tolokers will see. Make sure it is clear and correct.

        - **Name in labeling results**: This is the value you will see in the file with the labeling results.

    1. {% cut "If you use videos from YouTube" %}

        To display videos from YouTube, you should transform links to them. For example, the `https://www.youtube.com/watch?v=your_video_example` link should be replaced with `https://www.youtube.com/embed/your_video_example`.

        1. In the **Paste link to a sample video** field, specify the `https://www.youtube.com/embed/your_video_example` link. You can use a link to any of your videos. It is only used to display the task interface preview on the right.

            [![Create a project. Step 2.3.1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-youtube-link.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-youtube-link.png)

        1. Go to the **Code editor** tab. In the **Config** section, replace the `view.video` value with `view.iframe`.

            [![Create a project. Step 2.3.2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-iframe.png =480x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-iframe.png)

            {% note info %}

            To learn about other properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/templates/video-moderation.md).

            {% endnote %}

        {% endcut %}

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

1. Click **Add a pool** on the project page.

1. {% include [toloka-requester-pool-type](../_includes/toloka-requester-source/id-toloka-requester-source/pool-type.md) %}

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        {% include [tutorials-language-filter-image](../_includes/tutorials/language-filter-image.md) %}

    1. Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the **Client** filter and select the desired value: **Toloka web version** or **Toloka for mobile**.

    1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. Keep the preconfigured quality control rules as is:

        - **Fast responses**: This rule filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they respond to 4 out of 5 tasks in less than 15 seconds.

        - **Majority vote**: This rule accepts the most popular response as the correct one, and allows you to filter out Tolokers who answer incorrectly. The default settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 1 day. **Accept as majority** set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

    1. To filter out Tolokers who often make mistakes in the control tasks, click **Add a quality control rule → Control tasks**. Enter the following values:

        [![Create a pool. Control rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-control-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-control-rule.png)

        This means that if a Toloker completed more than three control tasks and gave incorrect answers in more than 60% of them, they will be blocked and won't be able to complete tasks on this project for 10 days.

        The rule will work if you specify the correct answers for the control tasks. You will do that later in this tutorial.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite**, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–20 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        The default value (`3`) means that each task will have 3 responses.

1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

    This time should be enough to read the instructions, load the task, watch the video clips, and respond (for example, 1,200 seconds).

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

    1. Attach a prepared dataset or media files.

        {% list tabs %}

        - A prepared dataset

          1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

              For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:video`, and the values are links to the video clips.

              ```plaintext
              INPUT:video
              https://yang.s3.yandex.net/finger gestures/20210723_113648.mp4
              https://yang.s3.yandex.net/finger gestures/20210723_113736.mp4
              https://yang.s3.yandex.net/finger gestures/20210723_113521.mp4
              ```

          1. Open the downloaded file, and replace the sample links with links to your video clips.

          1. Click **Select prepared dataset**, and upload the file you’ve just made.

        - Media files

          {% include [media-files](../_includes/toloka-requester-source/id-toloka-requester-source/media-files.md) %}

        {% endlist %}

    1. Click **Continue**.

    1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

        - **General tasks**: These are tasks for Tolokers to label.

        - **Control tasks**: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.

        - **Training tasks**: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

        For example, you can add 9 general tasks and 1 control task per suite:

        [![Upload data. Smart mixing](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-upload-data.png =600x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-upload-data.png)

    1. Click **Combine tasks into suites**.

1. {% include [toloka-requester-source-add-control-tasks](../_includes/toloka-requester-source/id-toloka-requester-source/add-control-tasks.md) %}

    1. Check the **result** checkbox, and select the correct answer for a task. Then, click the **Save and go to next** button. Add several control tasks this way.

        {% include [toloka-requester-source-control-percent](../_includes/toloka-requester-source/id-toloka-requester-source/control-percent.md) %}

    1. Note the **Distribution of correct responses for control tasks** graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

{% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling. Step 2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-start-labeling.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-start-labeling.png)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

1. {% include [toloka-requester-source-labeling-progress](../_includes/toloka-requester-source/id-toloka-requester-source/labeling-progress.md) %}

    [![See results. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-see-results-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-see-results-step-1.png)

1. When the labeling is complete, click the arrow next to the **Download results** button and choose **Run Dawid-Skene model** from the drop-down menu. Click **Yes** in the pop-up window.

    [![See results. Step 2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/see-results-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/see-results-step-2.png)

1. Open the same drop-down menu again, and click **View aggregations list**.

1. Wait until the aggregation is complete, and click **Download**. You will get the TSV file with the labeling results:

    - **INPUT**: The data you uploaded for labeling.

    - **OUTPUT**: The results of labeling (answers given by Tolokers).

    - **CONFIDENCE**: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder: Video analysis](../../template-builder/templates/video-moderation.md)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://labs-images-testing.s3.yandex.net/presets/sidepanel/06_videoModeration/EN/sample-files.zip)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles.md) %}