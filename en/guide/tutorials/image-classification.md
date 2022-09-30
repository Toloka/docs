# Image classification

In this tutorial, you will learn how to run image classification in Toloka. We will use a project preset designed specifically for this type of data labeling.

Image classification is a type of data labeling task with a finite number of response options.

Use Toloka to classify a set of images into categories that you define. Tolokers look at the images and choose one of the given categories. After you collect all the labeled images, you can apply your dataset for model training.

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ image-classification-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the {% if locale == "en-com" %}**Image classification**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose solution**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show performers**{% endif %}: In 2–5 words, state the general idea of the project.

    - {% if locale == "en-com" %}**Description for performers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/create-project-step-1.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/create-project-step-1.png" alt="Create a project. Step 1" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Using the {% if locale == "en-com" %}**Visual editor**{% endif %}, add your data to the {% if locale == "en-com" %}**Config**{% endif %} section:

        - {% if locale == "en-com" %}**Question performers will see in your task**{% endif %}: Write a question that matches the responses Tolokers need to choose from. All tasks in a project use the same question.

        - {% if locale == "en-com" %}**Paste link to a sample image**{% endif %}: This image is only used to display the task interface preview on the right.

    1. {% if locale == "en-com" %}**Set answer options**{% endif %} is pre-filled with sample answers. Replace the samples with your categories. Note that {% if locale == "en-com" %}**Other**{% endif %} and {% if locale == "en-com" %}**Error**{% endif %} are separate entities.

        - {% if locale == "en-com" %}**Answer option for performers**{% endif %}: This is the label that Tolokers will see. Make sure it is clear and correct.

        - {% if locale == "en-com" %}**Name in labeling results**{% endif %}: This is the value you will see in the file with the labeling results.

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

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, the {% if locale == "en-com" %}**Image classification**{% endif %} preset has preconfigured quality control rules for more accurate results. In most cases, you can keep them as is:

    - {% if locale == "en-com" %}**Fast responses**{% endif %}: This rule filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they complete tasks in 4 out of 5 task suites in less than 15 seconds.

    - {% if locale == "en-com" %}**Majority vote**{% endif %}: This rule accepts the most popular response as the correct one, and allows you to filter out Tolokers who answer incorrectly. The default settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 1 day. {% if locale == "en-com" %}**Accept as majority**{% endif %} set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–20 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        The default value (`3`) means that each task will have 3 responses.

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.

1. Create the tasks for Tolokers:

    1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

        For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:image`, and the values are links to the images.

        ```plaintext
        INPUT:image
        https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/041adb571f4342e7a42e47712f492101.jpg
        https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg
        https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/05334365c060421ab25264166bbb4fd1.jpg
        ```

    1. Open the downloaded file, and replace the sample links with links to your images.

    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.

    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    - {% if locale == "en-com" %}**General tasks**{% endif %}: These are tasks for Tolokers to label.

    - {% if locale == "en-com" %}**Control tasks**{% endif %}: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.

    - {% if locale == "en-com" %}**Training tasks**{% endif %}: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

    For example, you can add 9 general tasks and 1 control task per suite:

    <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.png" alt="Upload your file. Step 3" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

1. {% include [toloka-requester-source-add-control-tasks](../_includes/toloka-requester-source/id-toloka-requester-source/add-control-tasks.md) %}

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.

        <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.1.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.1.png" alt="Upload your file. Step 5.1" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

    1. {% include [toloka-requester-source-create-control-button](../_includes/toloka-requester-source/id-toloka-requester-source/create-control-button.md) %}

        <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.2.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.2.png" alt="Upload your file. Step 5.2" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

    1. Check the {% if locale == "en-com" %}**result**{% endif %} checkbox, and select the correct answer for a task. Then, click the {% if locale == "en-com" %}**Save and go to next**{% endif %} button. Add several control tasks this way.

        <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.3.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.3.png" alt="Upload your file. Step 5.3" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

        {% include [toloka-requester-source-control-percent](../_includes/toloka-requester-source/id-toloka-requester-source/control-percent.md) %}

    1. Note the {% if locale == "en-com" %}**Distribution of correct responses for control tasks**{% endif %} graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.

        <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.4.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.4.png" alt="Upload your file. Step 5.4" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:420px;" /></a>

    1. When you are done adding control tasks, click the pool name in the menu.

        <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.5.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/upload-data-step-3.5.png" alt="Upload your file. Step 5.5" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/start-labeling-step-2.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/start-labeling-step-2.png" alt="Start labeling. Step 2" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

1. {% include [toloka-requester-source-labeling-progress](../_includes/toloka-requester-source/id-toloka-requester-source/labeling-progress.md) %}

    <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/see-results-step-1.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/see-results-step-1.png" alt="See the results. Step 1" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. When the labeling is complete, click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button and choose {% if locale == "en-com" %}**Run Dawid-Skene model**{% endif %} from the drop-down menu. Click {% if locale == "en-com" %}**Yes**{% endif %} in the pop-up window.

    <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/see-results-step-2.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/image-classification/see-results-step-2.png" alt="See the results. Step 2" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. Open the same drop-down menu again, and click {% if locale == "en-com" %}**View aggregations list**{% endif %}.

1. Wait until the aggregation is complete, and click {% if locale == "en-com" %}**Download**{% endif %}. You will get the TSV file with the labeling results:

    - {% if locale == "en-com" %}**INPUT**{% endif %}: The data you uploaded for labeling.

    - {% if locale == "en-com" %}**OUTPUT**{% endif %}: The results of labeling (category picked by Tolokers).

    - {% if locale == "en-com" %}**CONFIDENCE**{% endif %}: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).

## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder — image classification](../../template-builder/templates/image-classification.md)
- [Toloka-Kit — image classification](https://github.com/Toloka/toloka-kit/blob/main/examples/1.computer_vision/image_classification/image_classification.ipynb)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://tlk.s3.yandex.net/toloka-kit/knowledge-base/catsdogs.tsv)