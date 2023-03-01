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

    1. Select the **Audio classification** preset.

1. Click **Choose this preset** in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-create-project-step-1.png)

1. In the **Task interface** section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Add your data to the **Config** section:

        1. Write a question Tolokers will see in your task. All tasks in a project use the same question.

            [![Create a project. Config question](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-question.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-question.png)

        1. Set answer options. In the `options` list, replace the sample answers with your values in the following properties:

            - `label`: This is the label that Tolokers will see. Make sure it is clear and correct.

            - `value`: This is the value you will see in the file with the labeling results.

            [![Create a project. Config answers](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-answers.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-answers.png)

        1. Configure keyboard shortcuts for the answers. Replace the values of the `payload` properties with the values you’ve already specified in the `value` properties.

            [![Create a project. Config shortcuts](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-shortcuts.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-config-shortcuts.png)

        {% note info %}

        To learn about other properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/reference/index.md).

        {% endnote %}

    1. In the **Input data example** section, add a link to a sample audio. This audio is only used to display the task interface preview on the right.

        [![Create a project. Input data example](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-input-example.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-input-example.png)

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - **Input data**: Parameters in the file with raw task data.

        - **Output data**: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. To save your data and continue, click **Create a project**.

    {% include [tutorials-create-project-image](../_includes/tutorials/create-project-image.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click **Add a pool** on the project page.

1. {% include [toloka-requester-pool-type](../_includes/toloka-requester-source/id-toloka-requester-source/pool-type.md) %}

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

    1. To select Tolokers based on their location, age, gender, and other parameters, click the **Add filter** button.

        If you need Tolokers who understand the speech in your audio recordings, use the **Languages** filter.

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-language-filter.png)

    1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. To filter out Tolokers who complete tasks too fast, edit the pre-configured **Fast responses** rule. Specify the following values:

        [![Create a pool. Fast responses](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-fast-responses.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-fast-responses.png)

        These settings mean that a Toloker who completes 3 or more task suites in less than 15 seconds will be blocked and won't be able to access your tasks anymore.

        A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–12 tasks per suite.

        {% note tip %}

        To determine the **Minimum time per task suite** value, complete your task suite and record the time. If you ban users for one fast response, then set a minimal time. If you do it after several fast responses, increase the time slightly.

        {% endnote %}

    1. Add a rule to filter out Tolokers who often make mistakes.

        - If your tasks don’t have the only right answers, use the pre-configured **Majority vote** rule. It accepts the most popular response as the correct one. Specify the following values:

            [![Create a pool. Majority vote](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-majority-vote.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-majority-vote.png)

            These settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 7 days. **Accept as majority** set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

        - If your tasks have the only right answers, add the **Control tasks** rule. Set the following values:

            [![Create a pool. Control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-control-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-control-rule.png)

            This means that if a Toloker completed more than three control tasks and gave incorrect answers in more than 60% of them, they will be blocked and won't be able to complete tasks on this project for 10 days.

            The rule will work if you specify the correct answers for the control tasks. You will do that later in this tutorial.

    1. Restrict access for Tolokers who skip multiple task suites in a row. Click **Add a quality control rule → Skipped assignments** and enter the following values:

        [![Create a pool. Skipped assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-skipped.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-skipped.png)

        This means that if a Toloker skips more than two task suites in a row, they will be blocked and won't be able to complete tasks on this project for 1 day.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite, $**, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–12 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        The default value (`3`) means that each task will have 3 responses.

1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

    This time should be enough to read the instructions, load the task suite, listen to all the audio recordings in it, and respond (for example, 900 seconds).

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

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

        [![Upload data. Tasks per suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-upload-data.png =600x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-upload-data.png)

    1. Click **Combine tasks into suites**.

1. {% include [toloka-requester-source-add-control-tasks](../_includes/toloka-requester-source/id-toloka-requester-source/add-control-tasks.md) %}

    1. Check the **result** checkbox, and select the correct answer for a task. Then, click the **Save and go to next** button. Add several control tasks this way.

        {% include [toloka-requester-source-control-percent](../_includes/toloka-requester-source/id-toloka-requester-source/control-percent.md) %}

    1. Note the **Distribution of correct responses for control tasks** graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.

        [![Upload data. Distribution of correct responses for control tasks](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-distribution.png =330x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-distribution.png)

1. {% include [tutorials-upload-tasks](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

1. At the **Add optional pool settings** step, set up advanced pool settings.

    {% note info %}

    This step will be enabled after you complete the previous steps. You can skip this step by clicking **Use default settings**.

    {% endnote %}

{% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-start-labeling.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-start-labeling.png)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

1. {% include [toloka-requester-source-labeling-progress](../_includes/toloka-requester-source/id-toloka-requester-source/labeling-progress.md) %}

    [![See the results. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-see-results-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-see-results-step-1.png)

1. When the labeling is complete, click the arrow next to the **Download results** button and choose **Run Dawid-Skene model** from the drop-down menu. Click **Yes** in the pop-up window.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audio-classification/audio-classification-step-2.png)

1. Open the same drop-down menu again, and click **View aggregations list**.

1. Wait until the aggregation is complete, and click **Download**. You will get the TSV file with the labeling results:

    - **INPUT**: The data you uploaded for labeling.

    - **OUTPUT**: The results of labeling (answers given by Tolokers).

    - **CONFIDENCE**: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://labs-images-testing.s3.yandex.net/presets/sidepanel/28_audioClassification/EN/sample-files.zip)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles.md) %}