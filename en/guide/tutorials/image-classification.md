# Image classification

In this tutorial, you will learn how to run image classification in Toloka. We will use a project preset designed specifically for this type of data labeling.

Image classification is a type of data labeling task with a finite number of response options.

Use Toloka to classify a set of images into categories that you define. Tolokers look at the images and choose one of the given categories. After you collect all the labeled images, you can apply your dataset for model training.

## Prerequisites {#prerequisites}

Before you begin make sure that:

- You are [registered](../concepts/access.md) in Toloka as a requester.
- You have [topped up](../concepts/refill.md) your Toloka account. If you are unsure about the budget, you can do that later in this tutorial. Toloka will display the budget estimate for your project.

## Choose a preset {#preset}

We recommend starting with a project preset for easier configuration and better results.

1. Follow [this link]({{ image-classification-preset }}), or create a project manually:
    1. In the main menu, choose the {% if locale == "en-com" %}**Projects**{% endif %} tab, and click {% if locale == "en-com" %}**Create a project**{% endif %}.
    1. Select the {% if locale == "en-com" %}**Image classification**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose solution**{% endif %} in the pop-up tab.

## Create a project {#project}

Set up how your tasks will look for Tolokers. Tolokers are people around the world who get paid for completing your tasks.

1. Under {% if locale == "en-com" %}**General information**{% endif %}, add the project name and description.
    - {% if locale == "en-com" %}**Name to show performers**{% endif %}: In 2–5 words, state the general idea of the project.
    - {% if locale == "en-com" %}**Description for performers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.
    {% note info %}

    This tutorial uses [Template Builder](https://toloka.ai/en/docs/template-builder/), but you can use the [HTML/JS/CSS editor](../concepts/spec.md) for the same purpose.

    {% endnote %}

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

1. Under {% if locale == "en-com" %}**Instructions for performers**{% endif %}, add the instructions Tolokers will see when they start doing your tasks. You can add text, tables, and images to your instructions.
    Check the sample text of the instructions, and update it to fit your project.

    {% note info %}

    When writing instructions, remember that most performers don’t know anything about your tasks beforehand. Make sure your instructions are as clear as possible, but not too wordy. For successful data labeling, try to strike a balance between covering all the essentials and keeping it short. Learn more in our [knowledge base](https://toloka.ai/knowledgebase/instruction/).

    {% endnote %}

1. To save your data and continue, click {% if locale == "en-com" %}**Create a project**{% endif %}.

## Create a pool {#pool}

A _pool_ is a set of tasks sent out to Tolokers at the same time. One project can have many pools. When creating a pool, you set up pricing, audience filters for Tolokers, and quality control.

1. Click {% if locale == "en-com" %}**Create new pool**{% endif %}.
1. Under {% if locale == "en-com" %}**General information**{% endif %}, set the {% if locale == "en-com" %}**Pool name**{% endif %}.
1. Under {% if locale == "en-com" %}**Audience**{% endif %}, set up filters to select Tolokers for your pool.
    1. Uncheck {% if locale == "en-com" %}**My tasks may contain shocking or pornographic content**{% endif %} if your project has none of those.
    1. To select Tolokers based on their language, location, age, gender, and other parameters, click the {% if locale == "en-com" %}**Add filter**{% endif %} button. For example, add the {% if locale == "en-com" %}**Languages**{% endif %} filter:
    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, the {% if locale == "en-com" %}**Image classification**{% endif %} preset has preconfigured quality control rules for more accurate results. In most cases, you can keep them as is:
    - {% if locale == "en-com" %}**Fast responses**{% endif %}: This rule filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they respond to 4 out of 5 tasks in less than 15 seconds.
    - {% if locale == "en-com" %}**Majority vote**{% endif %}: This rule accepts the most popular response as the correct one, and allows you to filter out Tolokers who answer incorrectly. The default settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 1 day. {% if locale == "en-com" %}**Accept as majority**{% endif %} set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

1. In {% if locale == "en-com" %}**Price**{% endif %}, set up how much a single task will cost for you.
    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–20 tasks per suite.
    1. In the {% if locale == "en-com" %}**Overlap**{% endif %} field, define how many Tolokers must do each task. The default value (`3`) means that each task will have 3 responses.
    1. At the bottom of the {% if locale == "en-com" %}**Price**{% endif %} section, you see {% if locale == "en-com" %}**Price per 1 task**{% endif %}. This is the amount of money paid per task.

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.
1. Create the tasks for Tolokers:
    1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

    For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:image`, and the values are links to the images.

    ```json
    INPUT:image
    https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/041adb571f4342e7a42e47712f492101.jpg
    https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg
    https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/05334365c060421ab25264166bbb4fd1.jpg
    ```

    1. Open the downloaded file, and replace the sample links with links to your images.
    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.
    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. Tasks are shown to Tolokers in suites. A suite is a single page with multiple tasks. Define how many tasks to include per suite:
    - {% if locale == "en-com" %}**General tasks**{% endif %}: These are tasks for Tolokers to label.
    - {% if locale == "en-com" %}**Control tasks**{% endif %}: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.
    - {% if locale == "en-com" %}**Training tasks**{% endif %}: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

    For example, you can add 9 general tasks and 1 control task per suite:

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.
1. To create control tasks, add correct answers to some of your tasks.
    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.
    1. On the {% if locale == "en-com" %}**Edit tasks**{% endif %} page, click {% if locale == "en-com" %}**Create control tasks**{% endif %}.
    1. Check the {% if locale == "en-com" %}**result**{% endif %} checkbox, and select the correct answer for a task. Then, click the {% if locale == "en-com" %}**Save and go to next**{% endif %} button. Add several control tasks this way.
    {% note info %}

    For large pools (over 1000 tasks), we recommend adding at least 1% of control tasks to the pool. For small pools (around 100 tasks), you need 10% control tasks.

    {% endnote %}

    1. Note the {% if locale == "en-com" %}**Distribution of correct responses for control tasks**{% endif %} graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.
    1. When you are done adding control tasks, click the pool name in the menu.


## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).
1. To send the tasks to Tolokers and begin the labeling process, click {% if locale == "en-com" %}**Start labeling**{% endif %}.
1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

1. You can see the labeling progress on the pool page. Wait until the labeling is completed. Refresh the page to check the progress.
1. When the labeling is complete, click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button and choose {% if locale == "en-com" %}**Run Dawid-Skene model**{% endif %} from the drop-down menu. Click {% if locale == "en-com" %}**Yes**{% endif %} in the pop-up window.
1. Open the same drop-down menu again, and click {% if locale == "en-com" %}**View aggregations list**{% endif %}.
1. Wait until the aggregation is complete, and click {% if locale == "en-com" %}**Download**{% endif %}. You will get the TSV file with the labeling results:
    - {% if locale == "en-com" %}**INPUT**{% endif %}: The data you uploaded for labeling.
    - {% if locale == "en-com" %}**OUTPUT**{% endif %}: The results of labeling (category picked by Tolokers).
    - {% if locale == "en-com" %}**CONFIDENCE**{% endif %}: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).



## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder — image classification](https://toloka.ai/en/docs/template-builder/templates/image-classification)
- [Toloka-Kit — image classification](https://github.com/Toloka/toloka-kit/blob/main/examples/1.computer_vision/image_classification/image_classification.ipynb)


## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://tlk.s3.yandex.net/toloka-kit/knowledge-base/catsdogs.tsv)
