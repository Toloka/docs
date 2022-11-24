{% include [image-styles](../../../_includes/image-styles.md) %}

# Audio classification

In this tutorial, you will learn how to run audio classification in Toloka. We will use a project preset designed specifically for this type of data labeling.

Audio classification is a type of data labeling task with an audio player and a finite number of response options.

Use Toloka to classify audio recordings into categories that you define. Tolokers listen to the audio and choose one of the given classes. After you collect the labeled data, you can use your dataset for training and evaluating text-to-speech models and audio classifiers.

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ audio-classification-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the {% if locale == "en-com" %}**Audio classification**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose this preset**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show Tolokers**{% endif %}: In 2–5 words, state the general idea of the project.

    - {% if locale == "en-com" %}**Description for Tolokers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-create-project-step-1.png)

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Add your data to the {% if locale == "en-com" %}**Config**{% endif %} section:

        1. Write a question Tolokers will see in your task. All tasks in a project use the same question.

            [![Create a project. Config question](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-question.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-question.png)

        1. Set answer options. In the {% if locale == "en-com" %}`options`{% endif %} list, replace the sample answers with your values in the following properties:

            - {% if locale == "en-com" %}`label`{% endif %}: This is the label that Tolokers will see. Make sure it is clear and correct.

            - {% if locale == "en-com" %}`value`{% endif %}: This is the value you will see in the file with the labeling results.

            [![Create a project. Config answers](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-answers.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-answers.png)

        1. Configure keyboard shortcuts for the answers. Replace the values of the {% if locale == "en-com" %}`payload`{% endif %} properties with the values you’ve already specified in the {% if locale == "en-com" %}`value`{% endif %} properties.

            [![Create a project. Config shortcuts](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-shortcuts.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-shortcuts.png)

        {% note info %}

        To learn about other properties of the {% if locale == "en-com" %}**Config**{% endif %} section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/reference/index.md).

        {% endnote %}

    1. In the {% if locale == "en-com" %}**Input data example**{% endif %} section, add a link to a sample audio. This audio is only used to display the task interface preview on the right.

        [![Create a project. Input data example](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-input-example.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-input-example.png)

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

    1. To select Tolokers based on their location, age, gender, and other parameters, click the {% if locale == "en-com" %}**Add filter**{% endif %} button.

        If you need Tolokers who understand the speech in your audio recordings, use the {% if locale == "en-com" %}**Languages**{% endif %} filter.

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-language-filter.png)

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results:

    1. To filter out Tolokers who complete tasks too fast, edit the pre-configured {% if locale == "en-com" %}**Fast responses**{% endif %} rule. Specify the following values:

        [![Create a pool. Fast responses](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-fast-responses.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-fast-responses.png)

        These settings mean that a Toloker who completes 3 or more task suites in less than 15 seconds will be blocked and won't be able to access your tasks anymore.

        A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–20 tasks per suite.

        {% note tip %}

        To determine the {% if locale == "en-com" %}**Minimum time per task suite**{% endif %} value, complete your task suite and record the time. If you ban users for one fast response, then set a minimal time. If you do it after several fast responses, increase the time slightly.

        {% endnote %}

    1. Add a rule to filter out Tolokers who often make mistakes.

        - If your tasks don’t have the only right answers, use the pre-configured {% if locale == "en-com" %}**Majority vote**{% endif %} rule. It accepts the most popular response as the correct one. Specify the following values:

            [![Create a pool. Majority vote](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-majority-vote.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-majority-vote.png)

            These settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 7 days. {% if locale == "en-com" %}**Accept as majority**{% endif %} set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

        - If your tasks have the only right answers, add the **Control tasks** rule. Set the following values:

            [![Create a pool. Control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-control-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-control-rule.png)

            This means that if a Toloker completed more than three control tasks and gave incorrect answers in more than 60% of them, they will be blocked and won't be able to complete tasks on this project for 10 days.

            The rule will work if you specify the correct answers for the control tasks. You will do that later in this tutorial.

    1. Restrict access for Tolokers who skip multiple task suites in a row. Click {% if locale == "en-com" %}**Add a quality control rule → Skipped assignments**{% endif %} and enter the following values:

        [![Create a pool. Skipped assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-skipped.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-skipped.png)

        This means that if a Toloker skips more than two task suites in a row, they will be blocked and won't be able to complete tasks on this project for 1 day.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–12 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        The default value (`3`) means that each task will have 3 responses.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In {% if locale == "en-com" %}**Additional settings**{% endif %}, specify the {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}.

    This time should be enough to read the instructions, load the task suite, listen to all the audio recordings in it, and respond (for example, 900 seconds).

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.

1. Attach a prepared dataset or media files.

    {% list tabs %}

    - A prepared dataset

        1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

            For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:audio`, and the values are links to the audio recordings.

            ```plaintext
            INPUT:audio
            https://tlklab.s3.yandex.net/audioClassification/demo/actual/audio_4.mp3
            https://tlklab.s3.yandex.net/audioClassification/demo/actual/audio_6.mp3
            https://tlklab.s3.yandex.net/audioClassification/demo/actual/audio_8.mp3
            ```

        1. Open the downloaded file, and replace the sample links with the links to your audio recordings.

        1. Click {% if locale == "en-com" %}**Select prepared dataset**{% endif %}, and upload the file you’ve just made.

    - Media files

        {% include [media-files](../_includes/toloka-requester-source/id-toloka-requester-source/media-files.md) %}

    {% endlist %}

1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    - {% if locale == "en-com" %}**General tasks**{% endif %}: These are tasks for Tolokers to label.

    - {% if locale == "en-com" %}**Control tasks**{% endif %}: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.

    - {% if locale == "en-com" %}**Training tasks**{% endif %}: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

    For example, you can add 9 general tasks and 1 control task per suite:

    [![Upload data. Tasks per suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-upload-data.png =600x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-upload-data.png)

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

1. {% include [toloka-requester-source-add-control-tasks](../_includes/toloka-requester-source/id-toloka-requester-source/add-control-tasks.md) %}

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.

        [![Upload data. Edit](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-edit.png =610x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-edit.png)

    1. {% include [toloka-requester-source-create-control-button](../_includes/toloka-requester-source/id-toloka-requester-source/create-control-button.md) %}

        [![Upload data. Create control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-create-control-button.png =500x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-create-control-button.png)

    1. Check the {% if locale == "en-com" %}**result**{% endif %} checkbox, and select the correct answer for a task. Then, click the {% if locale == "en-com" %}**Save and go to next**{% endif %} button. Add several control tasks this way.

        [![Upload data. Create control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-creating-control-task.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-creating-control-task.png)

        {% include [toloka-requester-source-control-percent](../_includes/toloka-requester-source/id-toloka-requester-source/control-percent.md) %}

    1. Note the {% if locale == "en-com" %}**Distribution of correct responses for control tasks**{% endif %} graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.

        [![Upload data. Distribution of correct responses for control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-distribution.png =330x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-distribution.png)

    1. When you are done adding control tasks, click the pool name in the menu.

        [![Upload data. Click pool name](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-pool-name.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-pool-name.png)

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-start-labeling.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-start-labeling.png)

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

1. {% include [toloka-requester-source-labeling-progress](../_includes/toloka-requester-source/id-toloka-requester-source/labeling-progress.md) %}

    [![See the results. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-see-results-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-see-results-step-1.png)

1. When the labeling is complete, click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button and choose {% if locale == "en-com" %}**Run Dawid-Skene model**{% endif %} from the drop-down menu. Click {% if locale == "en-com" %}**Yes**{% endif %} in the pop-up window.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-step-2.png)

1. Open the same drop-down menu again, and click {% if locale == "en-com" %}**View aggregations list**{% endif %}.

1. Wait until the aggregation is complete, and click {% if locale == "en-com" %}**Download**{% endif %}. You will get the TSV file with the labeling results:

    - {% if locale == "en-com" %}**INPUT**{% endif %}: The data you uploaded for labeling.

    - {% if locale == "en-com" %}**OUTPUT**{% endif %}: The results of labeling (answers given by Tolokers).

    - {% if locale == "en-com" %}**CONFIDENCE**{% endif %}: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).

## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://labs-images-testing.s3.yandex.net/presets/sidepanel/28_audioClassification/EN/sample-files.zip)

{% include [contact-support](../_includes/contact-support-help.md) %}