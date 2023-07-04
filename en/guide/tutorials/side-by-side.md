# Image comparison (Side-by-side)

In this tutorial, you will learn how to run side-by-side comparisons of images in Toloka. We will use a project preset designed specifically for this type of data labeling.

Image comparison is a type of data labeling task with two images and a finite number of response options.

Use this type of project when you need to:

- Understand which interface design users like best.

- Test different images in targeted ads.

- Choose the best images for publications, illustrations, or desktop backgrounds.

Tolokers compare two images and choose one of the given response options.

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Create a project {#project}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ image-comparison-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Click **Do it myself**.

    1. Select the **Image comparison (Side-by-side)** preset.

1. Click **Choose this preset** in the pop-up tab.

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    ![Create a project. Step 1](../_images/tutorials/side-by-side/create-project-step-1.png =700x)

1. In the **Task interface** section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Add your data to the **Config** section:

        1. Write a question Tolokers will see in your task. All tasks in a project use the same question.

            ![Create a project. Step 2.1.1](../_images/tutorials/side-by-side/image-comparison-step-2.1.1.png =700x)

        1. Set answer options. In the `options` list, replace the sample answers with your values in the following properties:

            - `label`: This is the label that Tolokers will see. Make sure it is clear and correct.

            - `value`: This is the value you will see in the file with the labeling results.

            ![Create a project. Step 2.1.2](../_images/tutorials/side-by-side/image-comparison-step-2.1.2.png =700x)

        1. Configure keyboard shortcuts for the answers. Replace the values of the `payload` properties with the values you’ve already specified in the `value` properties.

            ![Create a project. Step 2.1.3](../_images/tutorials/side-by-side/image-comparison-step-2.1.3.png =700x)

        {% note info %}

        To learn about other properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/templates/sbs-image.md).

        {% endnote %}

    1. In the **Input data example** section, add links to sample images. These images are only used to display the task interface preview on the right.

        ![Create a project. Step 2.2](../_images/tutorials/side-by-side/image-comparison-step-2.2.png =700x)

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

        ![Create a pool. Step 3.2](../_images/tutorials/side-by-side/create-pool-step-3.2.png =700x)

    1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. Under **Quality control**, set quality control rules for more accurate results.

    1. In most cases, you can keep the preconfigured quality control rules as is:

        - **Fast responses**: This rule filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they complete tasks in 4 out of 5 task suites in less than 15 seconds.

        - **Majority vote**: This rule accepts the most popular response as the correct one, and allows you to filter out Tolokers who answer incorrectly. The default settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 1 day. **Accept as majority** set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

    1. To filter out Tolokers who often make mistakes in the control tasks, click **Add a quality control rule → Control tasks**. Enter the following values:

        ![Create a pool. Control rule](../_images/tutorials/side-by-side/image-comparison-control-rule.png =700x)

        This means that if a Toloker completed more than three control tasks and gave incorrect answers in more than 60% of them, they will be blocked and won't be able to complete tasks on this project for 10 days.

        The rule will work if you specify the correct answers for the control tasks. You will do that later in this tutorial.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite**, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–20 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        The default value (`3`) means that each task will have 3 responses.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

    1. Create the tasks for Tolokers:

        1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

            For this type of project, the file with tasks must have two parameters. Their names equal `INPUT:image_left` and `INPUT:image_right`, and the values are links to the images.

            ```plaintext
            INPUT:image_left	INPUT:image_right
            https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_blossom_icon.png	https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_dandelion_icon.png
            https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_dandelion_icon.png	https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_sunrise_icon.png
            https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_sunrise_icon.png	https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_blossom_icon.png
            ```

        1. Open the downloaded file, and replace the sample links with links to your images.

        1. Click **Drop file here or select**, and upload the file you’ve just made.

        1. Click **Continue**.

    1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

        - **General tasks**: These are tasks for Tolokers to label.

        - **Control tasks**: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.

        - **Training tasks**: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

        For example, you can add 9 general tasks and 1 control task per suite:

        ![Upload your file. Step 3](../_images/tutorials/side-by-side/upload-data-step-3.png =700x)

    1. Click **Combine tasks into suites**.

1. {% include [toloka-requester-source-add-control-tasks](../_includes/toloka-requester-source/id-toloka-requester-source/add-control-tasks.md) %}

    1. Check the **result** checkbox, and select the correct answer for a task. Then, click the **Save and go to next** button. Add several control tasks this way.

        {% include [toloka-requester-source-control-percent](../_includes/toloka-requester-source/id-toloka-requester-source/control-percent.md) %}

    1. Note the **Distribution of correct responses for control tasks** graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.

        ![Upload your file. Step 5.4](../_images/tutorials/side-by-side/upload-data-step-3.4.png =340x)

1. {% include [tutorials-double-check](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

{% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    ![Start labeling. Step 2](../_images/tutorials/side-by-side/start-labeling-step-2.png =700x)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

1. {% include [toloka-requester-source-labeling-progress](../_includes/toloka-requester-source/id-toloka-requester-source/labeling-progress.md) %}

    ![See the results. Step 1](../_images/tutorials/side-by-side/see-results-step-1.png =700x)

1. When the labeling is complete, click the arrow next to the **Download results** button and choose **Run Dawid-Skene model** from the drop-down menu. Click **Yes** in the pop-up window.

    ![See the results. Step 2](../_images/tutorials/side-by-side/see-results-step-2.png =700x)

1. Open the same drop-down menu again, and click **View aggregations list**.

1. Wait until the aggregation is complete, and click **Download**. You will get the TSV file with the labeling results:

    - **INPUT**: The data you uploaded for labeling.

    - **OUTPUT**: The results of labeling (answers given by Tolokers).

    - **CONFIDENCE**: The response significance according to the [Dawid-Skene model](../concepts/result-aggregation.md#dawid-skene).

## Troubleshooting {#troubleshooting}

{% cut "How do I create a task with a selection out of three image options with the paired image comparison?" %}

1. Use the **Image comparison (Side-by-side)** preset.

1. In the file, specify the links to the compared images.

1. In the file, create the tasks where all the images will be compared in pairs:

    - Image 1 and Image 2

    - Image 1 and Image 3

    - Image 2 and Image 3

1. Process the results.

You can also edit the project so that the user sees 3 images at once and selects one of them.

{% endcut %}

{% cut "How do I make an image expand to its maximum size on click?" %}

The `popup` property of the component [view.image](../../template-builder/reference/view.image.md) specifies whether opening a full-size image with a click is allowed. By default, it is `true` (allowed).

{% endcut %}

{% include [faq-need-convert](../_includes/faq/project-settings/need-convert.md) %}

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder: Image comparison](../../template-builder/templates/sbs-image.md)

## For developers {#for-developers}

- [Toloka-Kit: Image comparison](https://github.com/Toloka/toloka-kit/blob/main/examples/4.ranking/side_by_side_image_comparision/side_by_side_comparision.ipynb)

## Datasets and reference {#datasets}

- [Sample dataset file with tasks](https://tlk.s3.yandex.net/dataset/toloka_logos/sbs.tsv)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}