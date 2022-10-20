{% include [image-styles](../../../_includes/image-styles.md) %}

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

    {% note warning %}

    The video player supports only MP4 format with H.264 or H.265 encoding.

    {% endnote %}

- Make sure that the video clips look the same in the desktop and mobile versions of Toloka. A video clip may not play or play incorrectly in the mobile version. In this case, when creating a pool, you will need to restrict access to the pool for the Tolokers with mobile devices.

    Learn more about [configuring tasks for mobile devices](../concepts/mobile.md).

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ video-moderation-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the {% if locale == "en-com" %}**Hand gesture classification**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose solution**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show performers**{% endif %}: In 2–5 words, state the general idea of the project.

    - {% if locale == "en-com" %}**Description for performers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-create-project-step-1.png)

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Using the {% if locale == "en-com" %}**Visual editor**{% endif %}, add your data to the {% if locale == "en-com" %}**Config**{% endif %} section:

        - {% if locale == "en-com" %}**Question performers will see in your task**{% endif %}: Write a question that matches the responses Tolokers need to choose from. All tasks in a project use the same question.

        - {% if locale == "en-com" %}**Paste link to a sample video**{% endif %}: This video is only used to display the task interface preview on the right.

    1. {% if locale == "en-com" %}**Set answer options**{% endif %} is pre-filled with sample answers. Replace the samples with your categories. Note that {% if locale == "en-com" %}**Other**{% endif %} and {% if locale == "en-com" %}**Error**{% endif %} are separate entities.

        - {% if locale == "en-com" %}**Answer option for performers**{% endif %}: This is the label that Tolokers will see. Make sure it is clear and correct.

        - {% if locale == "en-com" %}**Name in labeling results**{% endif %}: This is the value you will see in the file with the labeling results.

    1. {% cut "If you use videos from YouTube" %}

        To display videos from YouTube, you should transform links to them. For example, the `https://www.youtube.com/watch?v=your_video_example` link should be replaced with `https://www.youtube.com/embed/your_video_example`.

        1. In the {% if locale == "en-com" %}**Paste link to a sample video**{% endif %} field, specify the `https://www.youtube.com/embed/your_video_example` link. You can use a link to any of your videos. It is only used to display the task interface preview on the right.

            [![Create a project. Step 2.3.1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-youtube-link.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-youtube-link.png)

        1. Go to the {% if locale == "en-com" %}**Code editor**{% endif %} tab. In the {% if locale == "en-com" %}**Config**{% endif %} section, replace the `view.video` value with `view.iframe`.

            [![Create a project. Step 2.3.2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-iframe.png =480x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-iframe.png)

            {% note info %}

            To learn about other properties of the {% if locale == "en-com" %}**Config**{% endif %} section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/templates/video-moderation.md).

            {% endnote %}

        {% endcut %}

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - {% if locale == "en-com" %}**Input data**{% endif %}: Parameters in the file with raw task data.

        - {% if locale == "en-com" %}**Output data**{% endif %}: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. To save your data and continue, click {% if locale == "en-com" %}**Create a project**{% endif %}.

    {% include [tutorials-create-project-image](../_includes/tutorials/create-project-image.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click {% if locale == "en-com" %}**Create new pool**{% endif %}.

1. Under {% if locale == "en-com" %}**General information**{% endif %}, set the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear {% if locale == "en-com" %}**My tasks may contain shocking or pornographic content**{% endif %} if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        {% include [tutorials-language-filter-image](../_includes/tutorials/language-filter-image.md) %}

    1. Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results:

    1. Keep the preconfigured quality control rules as is:

        - {% if locale == "en-com" %}**Fast responses**{% endif %}: This rule filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they respond to 4 out of 5 tasks in less than 15 seconds.

        - {% if locale == "en-com" %}**Majority vote**{% endif %}: This rule accepts the most popular response as the correct one, and allows you to filter out Tolokers who answer incorrectly. The default settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 1 day. {% if locale == "en-com" %}**Accept as majority**{% endif %} set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

    1. To filter out Tolokers who often make mistakes in the control tasks, click {% if locale == "en-com" %}**Add a quality control rule → Control tasks**{% endif %}. Enter the following values:

        [![Create a pool. Control rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-control-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-control-rule.png)

        This means that if a Toloker completed more than three control tasks and gave incorrect answers in more than 60% of them, they will be blocked and won't be able to complete tasks on this project for 10 days.

        The rule will work if you specify the correct answers for the control tasks. You will do that later in this tutorial.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–20 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        The default value (`3`) means that each task will have 3 responses.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In {% if locale == "en-com" %}**Additional settings**{% endif %}, specify the {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}.

    This time should be enough to read the instructions, load the task, watch the video clips, and respond (for example, 1,200 seconds).

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.

1. Create the tasks for Tolokers:

    1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

        For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:video`, and the values are links to the video clips.

        ```plaintext
        INPUT:video
        https://yang.s3.yandex.net/finger gestures/20210723_113648.mp4
        https://yang.s3.yandex.net/finger gestures/20210723_113736.mp4
        https://yang.s3.yandex.net/finger gestures/20210723_113521.mp4
        ```

    1. Open the downloaded file, and replace the sample links with links to your video clips.

    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.

    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    - {% if locale == "en-com" %}**General tasks**{% endif %}: These are tasks for Tolokers to label.

    - {% if locale == "en-com" %}**Control tasks**{% endif %}: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.

    - {% if locale == "en-com" %}**Training tasks**{% endif %}: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

    For example, you can add 9 general tasks and 1 control task per suite:

    [![Upload data. Smart mixing](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-upload-data.png =600x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-upload-data.png)

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

1. {% include [toloka-requester-source-add-control-tasks](../_includes/toloka-requester-source/id-toloka-requester-source/add-control-tasks.md) %}

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.

        [![Upload data. Edit control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-edit.png =610x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-edit.png)

    1. {% include [toloka-requester-source-create-control-button](../_includes/toloka-requester-source/id-toloka-requester-source/create-control-button.md) %}

        [![Upload data. Create control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-create-control-button.png =500x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-create-control-button.png)

    1. Check the {% if locale == "en-com" %}**result**{% endif %} checkbox, and select the correct answer for a task. Then, click the {% if locale == "en-com" %}**Save and go to next**{% endif %} button. Add several control tasks this way.

        [![Upload data. Create control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-creating-control-task.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-creating-control-task.png)

        {% include [toloka-requester-source-control-percent](../_includes/toloka-requester-source/id-toloka-requester-source/control-percent.md) %}

    1. Note the {% if locale == "en-com" %}**Distribution of correct responses for control tasks**{% endif %} graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.

        [![Upload data. Distribution of correct responses for control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-distribution.png =430x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-distribution.png)

    1. When you are done adding control tasks, click the pool name in the menu.

        [![Upload data. Create control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-pool-name.png =600x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-pool-name.png)

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling. Step 2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-start-labeling.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-start-labeling.png)

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

1. {% include [toloka-requester-source-labeling-progress](../_includes/toloka-requester-source/id-toloka-requester-source/labeling-progress.md) %}

    [![See results. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-see-results-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/video-moderation/video-moderation-see-results-step-1.png)

1. When the labeling is complete, click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button and choose {% if locale == "en-com" %}**Run Dawid-Skene model**{% endif %} from the drop-down menu. Click {% if locale == "en-com" %}**Yes**{% endif %} in the pop-up window.

    [![See results. Step 2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/see-results-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/see-results-step-2.png)

1. Open the same drop-down menu again, and click {% if locale == "en-com" %}**View aggregations list**{% endif %}.

1. Wait until the aggregation is complete, and click {% if locale == "en-com" %}**Download**{% endif %}. You will get the TSV file with the labeling results:

    - {% if locale == "en-com" %}**INPUT**{% endif %}: The data you uploaded for labeling.

    - {% if locale == "en-com" %}**OUTPUT**{% endif %}: The results of labeling (answers given by Tolokers).

    - {% if locale == "en-com" %}**CONFIDENCE**{% endif %}: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).

## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder — video analysis](../../template-builder/templates/video-moderation.md)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://labs-images-testing.s3.yandex.net/presets/sidepanel/06_videoModeration/EN/sample-files.zip)

{% include [contact-support](../_includes/contact-support-help.md) %}