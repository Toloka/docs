# Object recognition & detection

In this tutorial, you will learn how to run object recognition in Toloka. We will use a project preset designed specifically for this type of data labeling.

Object recognition is a type of data labeling task with an image and an editor for selecting an image area.

Tolokers look at the image and select the objects that you need to detect. After you collect all the labeled images, you can apply your [dataset](https://toloka.ai/datasets) for computer vision training.

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ object-recognition-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the **Object recognition & detection** preset.

1. Click **Choose this preset** in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/create-project-step-1.png)

1. In the **Task interface** section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Using the **Visual editor**, set up your task in the **Config** section:

        - **Paste link to a sample image**: This image is only used to display the task interface preview on the right.

        - **Choose the shape for outlining objects in photos**: All tasks in a project use the same shape.

        [![Create a project. Visual editor](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-visual-editor.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-visual-editor.png)

    1. Select the **I want to outline multiple types of objects** checkbox if you need to detect more than one category of objects in an image. Replace the samples with your types:

        - **Object name for Tolokers**: This is the label that Tolokers will see. Make sure it is clear and correct.

        - **Name in labeling results**: This is the value you will see in the file with the labeling results.

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - **Input data**: Parameters in the file with raw task data.

        - **Output data**: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    In this type of project, Tolokers will select objects in images with the shape you’ve specified in the **Config** section.

    [![Create a project. Selection instructions](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-instructions.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-instructions.png)

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. To save your data and continue, click **Create a project**.

    {% include [tutorials-create-project-image](../_includes/tutorials/create-project-image.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click **Add a pool** on the project page.

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        For example, add the **Languages** filter:

        [![Create a pool. Step 3.2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/create-pool-step-3.2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/create-pool-step-3.2.png)

    1. Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the **Client** filter and select the desired value: **Toloka web version** or **Toloka for mobile**.

    1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. Click the **Review task responses manually** toggle, and specify the number of days for checking the task in the **Review period in days** field.

        {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

    1. Keep the pre-configured **Fast responses** rule as is. This rule filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they complete tasks in 4 out of 5 task suites in less than 15 seconds.

    1. Delete the pre-configured **Majority vote** rule.

    1. Click **Add a quality control rule → Results of assignment review**, and enter the following values:

        [![Create a pool. Selection results rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-results-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-results-rule.png)

        This means that if 35% or more of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

    It should be long enough to read the instructions and wait for task data to download (for example, 1,200 seconds).

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite**, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks.

        If the tasks are simple, you can add 8–10 tasks per suite.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        For image area selection tasks, it is usually 1. This means that each task will have 1 response.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

    1. Attach a prepared dataset or media files.

        {% list tabs %}

        - A prepared dataset

            1. {% include [toloka-requester-source-download-template](../_includes/toloka-requester-source/id-toloka-requester-source/download-template.md) %}

                For this type of project, the file with tasks must have one parameter. Its name equals `INPUT:image`, and the values are links to the images.

                ```plaintext
                INPUT:image
                https://tlk.s3.yandex.net/sdc/photos/0c7b15d0f4e5db0416189afe6486f3cb.jpg
                https://tlk.s3.yandex.net/sdc/photos/3e5d32e31dfd50fe826fd46b761481cf.jpg
                https://tlk.s3.yandex.net/sdc/photos/0fb80721932aa59ecc684141433170b6.jpg
                ```

            1. Open the downloaded file, and replace the sample links with links to your images.

            1. Click **Select prepared dataset**, and upload the file you’ve just made.

        - Media files

            {% include [media-files](../_includes/toloka-requester-source/id-toloka-requester-source/media-files.md) %}

        {% endlist %}

    1. Click **Continue**.

    1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

        - **General tasks**: These are tasks for Tolokers to label.

        - **Control tasks**: These are tasks with predefined answers used to control the quality of responses. You don’t need control tasks in area selection projects.

        - **Training tasks**: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

        For example, you can add 8 general tasks per suite:

        [![Create a pool. Step 3](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-upload-data-step-3.png =636x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-upload-data-step-3.png)

    1. Click **Combine tasks into suites**.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

{% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling. Step 2](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/start-labeling-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/start-labeling-step-2.png)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

Track the labeling progress on the pool page. You can start the review when the first results are received.

After the specified time period, all responses are automatically accepted, regardless of their quality.

1. Go to the pool, and click **Review assignments**.

    [![See results. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-review-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-review-results.png)

1. Choose an assignment.

1. Check the responses, and click **Accept** or **Decline**. For rejected responses, enter a comment to specify the reason.

    {% note info %}

    To learn about other ways of review, see the [Reviewing Tolokers' responses](../concepts/accept.md) section.

    {% endnote %}

1. After checking all the assignments, click **Download results**.

    [![See results. Step 4](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-results-download.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/selection/selection-results-download.png)

    You will get the TSV file with the labeling results. The point coordinates in the file are presented in JSON.

## Troubleshooting {#troubleshooting}

{% cut "Do I need to convert all the images in the task to the same size or can they be different?" %}

You can use different image sizes.

{% endcut %}

{% cut "How do I mark up triangles so that they close automatically when the third point is selected?" %}

Use the **X** shortcut for closing areas.

You can customize the shortcuts using the properties of the [plugin.field.image-annotation.hotkeys](../../template-builder/reference/plugin.field.image-annotation.hotkeys.md) component.

{% endcut %}

{% cut "How do I create a task for selecting objects in images?" %}

We recommend that you break down your object selection project into three projects in Toloka:

1. Sorting images containing an object.

    1. [Create a task](image-classification.md) using the **Image classification** preset.

    1. Sort the images containing the object you are looking for.

    1. Show the image to the Toloker and ask if the object is in the image. Response options: Yes/No.

1. Selecting objects in images.

    1. Select the object in the images you obtained after the previous project. You already have such a project. Run the task with manual review.

    1. Use the quality control rules: fast responses, manual review, and post-review re-assessment. [Description of rules with examples](../concepts/control.md).

1. Reviewing object selection assignments.

    1. Create a task using the **Object recognition & detection** preset.

    1. Hide the editor and ask whether the object is selected correctly. Response options: Yes/No.

    1. In the input data, pass the images and coordinates of the labeled objects from the previous task.

    Now you can run the resulting pool with an overlap of 3–5 or with dynamic overlap. After that, you can aggregate the results and then upload the data for review to Project 2.

    To prevent the users who worked on the second project from doing the review, assign a skill to them. Use this skill as a filter in the pools of the third project.

{% endcut %}

{% cut "I have a task for area selection in an image. What should the Toloker do if there is no selectable object in the image?" %}

Main options:

- Select an arbitrary area in the image (for example, put a square in the upper-right corner). In this case, the project instructions for reviewers should also reflect this.

- Ask the Toloker to skip the task and report it in a personal message. Messages are reviewed by the requester. If the object is truly missing, the task is deleted from the pool by resetting the overlap.

- Add an additional **No object** checkbox to the task interface. Make sure that your interface checks that either the object is selected or the checkbox is enabled. In this case, add information about the checkbox value in the review task interface.

{% endcut %}

{% cut "How much would 2000 images with a large number of different types of selectable objects cost? How do I create a task for this amount of work?" %}

In the case of [crowdsourcing](https://toloka.ai/knowledgebase/crowdsourcing-concepts/), it's better to break down this task. The simpler the task, the cheaper it is and the better the quality of the final result. The cost of labeling a single class of objects in photos might be about $0.01.

Base your task on the **Object recognition & detection** preset. See the step-by-step guide for creating this type of project in the [tutorial](selection.md).

{% endcut %}

{% cut "How do I implement selection of 3 different areas in an image? Select the name, image, and price in the product page screenshot." %}

In the **Config** section on the project settings page, use the **Visual editor** and select the **I want to outline multiple types of objects** checkbox. Replace the samples with your categories.

{% endcut %}

{% cut "What are the input data in the case of object labeling in an image: the coordinates of the object relative to the image, or the coordinates of the object in the Toloka user window?" %}

The coordinates are relative to the image.

{% endcut %}

{% cut "How do I use control and training tasks in the standard template with an area selection editor?" %}

In the standard template with an area selection editor, you can't use the control tasks, because in order for the assignment to be accepted by the system as correct, the object selected by the user must exactly match the control object. This is almost impossible. Therefore, you can leave the `GOLDEN` field empty in the task file or simply delete all the columns except `INPUT`.

You can't also use [training](../../glossary.md#training-pool) and the main pool with the **Training** type in an area selection project due to the same reason.

Such tasks are usually run with manual review: the Toloker submits an assignment, and then the assignment is rejected or accepted after the review.

For pre-selection of users, you can use “examination tasks”. Review the assignments and assign skills based on the percentage of accepted assignments. For this purpose, add the **Results of assignment review** rule to the pool. To make sure that only the good Tolokers are admitted to the main pool, put a skill-based filter to the pool.

{% endcut %}

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder: Object recognition](../../template-builder/templates/object-recognition.md)

## For developers {#for-developers}

- [Toloka-Kit: Object recognition](https://github.com/Toloka/toloka-kit/blob/main/examples/1.computer_vision/object_detection/object_detection.ipynb)

## [Datasets](https://toloka.ai/datasets) and reference {#datasets}

- [Sample dataset file with tasks](https://tlk.s3.yandex.net/toloka-kit/knowledge-base/road_signs.tsv)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles.md) %}