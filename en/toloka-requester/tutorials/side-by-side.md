# Image comparison (Side-by-side)

In this tutorial, you will learn how to run side-by-side comparisons of images in Toloka. We will use a project preset designed specifically for this type of data labeling.

Image comparison is a type of data labeling task with two images and a finite number of response options.

Use this type of project when you need to:

- Understand which interface design users like best.

- Test different images in targeted ads.

- Choose the best images for publications, illustrations, or desktop backgrounds.

Tolokers compare two images and choose one of the given response options.

## Prerequisites

Before you begin make sure that:

- You are [registered](https://toloka.ai/docs/guide/concepts/access.html) in Toloka as a requester.

- You have [topped up](https://toloka.ai/docs/guide/concepts/refill.html) your Toloka account. If you are unsure about the budget, you can do that later in this tutorial. Toloka will display the budget estimate for your project.

## Choose a preset

We recommend starting with a project preset for easier configuration and better results.

1. Follow [this link](https://toloka.yandex.com/requester/templates?choosedCard=jYWa4jxeqqrhJn7BZpeb), or create a project manually:

   1. In the main menu, choose the **Projects** tab, and click **Create a project**.

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/choose-preset-step-1.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/choose-preset-step-1.png" alt="Choose a preset. Step 1" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

   1. Select the **Image comparison (Side-by-side)** preset.

1. Click **Choose solution** in the pop-up tab.

## Create a project

Set up how your tasks will look for Tolokers. Tolokers are people around the world who get paid for completing your tasks.

1. Under **General information**, add the project name and description.

   - **Name to show performers**: In 2–5 words, state the general idea of the project.

   - **Description for performers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

   <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/create-project-step-1.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/create-project-step-1.png" alt="Create a project. Step 1" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. In the **Task interface** section, set up what your tasks will look like. This preset has a task template with validation, keyboard shortcuts, and task layout pre-configured.

   {% note info %}

   This tutorial uses [Template Builder](https://toloka.ai/en/docs/template-builder/), but you can use the [HTML/JS/CSS editor](https://toloka.ai/docs/guide/concepts/spec.html) for the same purpose.

   {% endnote %}

   1. Add your data to the **Config** section:

      1. Write a question Tolokers will see in your task. All tasks in a project use the same question.

         <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/image-comparison-step-2.1.1.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/image-comparison-step-2.1.1.png" alt="Create a project. Step 2.1.1" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

      1. Set answer options. In the `options` list, replace the sample answers with your values in the following properties:

         - `label`: This is the label that Tolokers will see. Make sure it is clear and correct.

         - `value`: This is the value you will see in the file with the labeling results.

         <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/image-comparison-step-2.1.2.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/image-comparison-step-2.1.2.png" alt="Create a project. Step 2.1.2" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

      1. Configure keyboard shortcuts for the answers. Replace the values of the `payload` properties with the values you’ve already specified in the `value` properties.

         <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/image-comparison-step-2.1.3.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/image-comparison-step-2.1.3.png" alt="Create a project. Step 2.1.3" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

   {% note info %}

   To learn about other properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](https://toloka.ai/en/docs/template-builder/templates/sbs-image).

   {% endnote %}

   1. In the **Input data example** section, add links to sample images. These images are only used to display the task interface preview on the right.

   <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/image-comparison-step-2.2.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/image-comparison-step-2.2.png" alt="Create a project. Step 2.2" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

   1. Raw task data and labeling results are stored in a table format. The **Data specification** section determines which columns the files with data might have.

      Click **Show specifications** and check the values:

      - **Input data**: Сolumns in the file with raw task data.

      - **Output data**: Сolumns in the file with labeling results.

      **Input data** and **Output data** [match the task interface](https://toloka.ai/en/docs/template-builder/operations/create-specs) you set up in **Template Builder**. Check that there are fields for all data types you use for your tasks, and for the ones you want to see in the results file.

1. Under **Instructions for performers**, add the instructions Tolokers will see when they start doing your tasks. You can add text, tables, and images to your instructions.

   Check the sample text of the instructions, and update it to fit your project.

   {% note tip %}

   When writing instructions, remember that most Tolokers don’t know anything about your tasks beforehand. Make sure your instructions are as clear as possible, but not too wordy. For successful data labeling, try to strike a balance between covering all the essentials and keeping it short. Learn more in our [knowledge base](https://toloka.ai/knowledgebase/instruction/).

   {% endnote %}

1. To save your data and continue, click **Create a project**.

   <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/create-project-step-4.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/create-project-step-4.png" alt="Create a project. Step 4" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

## Create a pool

A _pool_ is a set of tasks sent out to Tolokers at the same time. One project can have many pools. When creating a pool, you set up pricing, audience filters for Tolokers, and quality control.

1. Click **Create new pool**.

1. Under **General information**, set the **Pool name**.

1. Under **Audience**, set up filters to select Tolokers for your pool.

   1. Uncheck **My tasks may contain shocking or pornographic content** if your project has none of those.

   1. To select Tolokers based on their language, location, age, gender, and other parameters, click the **Add filter** button. For example, add the **Languages** filter:

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/create-pool-step-3.2.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/create-pool-step-3.2.png" alt="Create a pool. Step 3.2" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

   1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/create-pool-step-3.3.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/create-pool-step-3.3.png" alt="Create a pool. Step 3.3" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. Under **Quality control**, the **Image comparison (Side-by-side)** preset has preconfigured quality control rules for more accurate results. In most cases, you can keep them as is:

   - **Fast responses**: This rule filters out Tolokers who complete tasks too fast. The default settings mean that Tolokers are banned from the project for 1 day if they respond to 4 out of 5 tasks in less than 15 seconds.

   - **Majority vote**: This rule accepts the most popular response as the correct one, and allows you to filter out Tolokers who answer incorrectly. The default settings mean that Tolokers who give correct responses to less than 40% of tasks are banned from the project for 1 day. **Accept as majority** set to `2` means that 2 similar responses out of all responses given to a single task will be considered as the correct answer.

1. In **Price**, set up how much a single task will cost for you.

   1. In **Price per task suite**, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks. It can contain one or several tasks. If the tasks are simple, you can add 10–20 tasks per suite.

   1. In the **Overlap** field, define how many Tolokers must do each task. The default value (`3`) means that each task will have 3 responses.

   1. At the bottom of the **Price** section, you see **Price per 1 task**. This is the amount of money paid per task.

1. To save the settings and continue, click **Create pool**.

## Upload data

At this step, upload your task data to Toloka.

1. Click **Upload data**.

1. Create the tasks for Tolokers:

   1. To download a template, click **Template for general tasks in XLSX** or **Template for general tasks in TSV**.

      For this type of project, the file with tasks must have two columns. The headers of the columns equal `INPUT:image_left` and `INPUT:image_right`, and the column values are links to the images.

   ```plaintext
   INPUT:image_left	INPUT:image_right
   https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_dandelion_icon.png	https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_sunrise_icon.png
   https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_dandelion_icon.png	https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_sunrise_icon.png
   https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_dandelion_icon.png	https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_sunrise_icon.png
   ```

   1. Open the downloaded file, and replace the sample links with links to your images.

   1. Click **Drop file here or select**, and upload the file you’ve just made.

   1. Click **Continue**.

1. Tasks are shown to Tolokers in suites. A suite is a single page with multiple tasks. Define how many tasks to include per suite:

   - **General tasks**: These are the tasks for Tolokers to label.
   - **Control tasks**: These are tasks with predefined answers used to control the quality of responses. You will create them in the next step.
   - **Training tasks**: These are tasks with predefined answers and explanations for Tolokers. Normally you use training tasks in separate training pools. You don’t have to include them.

      For example, you can add 9 general tasks and 1 control task per suite:

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.png" alt="Upload your file. Step 3" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. Click **Combine tasks into suites**.

1. To create control tasks, add correct answers to some of your tasks.

   1. Click **Edit**.

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.1.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.1.png" alt="Upload your file. Step 3.1" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

   1. On the **Edit tasks page**, click **Create control tasks**.

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.2.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.2.png" alt="Upload your file. Step 3.2" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

   1. Check the **result** checkbox, and select the correct answer for a task. Then, click the **Save and go to next** button. Add several control tasks this way.

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.3.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.3.png" alt="Upload your file. Step 3.3" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

      {% note tip %}

      For large pools (over 1000 tasks), we recommend adding at least 1% of control tasks to the pool. For small pools (around 100 tasks), you need 10% control tasks.

      {% endnote %}

   1. Note the **Distribution of correct responses for control tasks** graph on the right side of the page. It shows how many control tasks of each type you have. We recommend adding an equal quantity of each correct response.

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.4.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.4.png" alt="[![Upload your file. Step 3.4" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:340px;" /></a>

   1. When you are done adding control tasks, click the pool name in the menu.

      <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.5.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/upload-data-step-3.5.png" alt="Upload your file. Step 3.5" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

## Start labeling

1. Make sure you have [topped up your account](https://toloka.ai/docs/guide/concepts/refill.html).

1. To send the tasks to Tolokers and begin the labeling process, click **Start labeling**.

   <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/start-labeling-step-2.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/start-labeling-step-2.png" alt="Start labeling. Step 2" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. In the pop-up panel, review the budget and click **Launch**.

## See the results

1. You can see the labeling progress on the pool page. Wait until the labeling is completed. Refresh the page to check the progress.

   <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/see-results-step-1.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/see-results-step-1.png" alt="See the results. Step 1" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. When the labeling is complete, click the arrow next to the **Download results** button and choose **Run Dawid-Skene model** from the drop-down menu. Click **Yes** in the pop-up window.

   <a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/see-results-step-2.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/guide/tutorials/side-by-side/see-results-step-2.png" alt="See the results. Step 2" style="border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. Open the same drop-down menu again, and click **View aggregations list**.

1. Wait until the aggregation is complete, and click **Download**. You will get TSV files with the labeling results:

   - **INPUT**: The data you uploaded for labeling.
   - **OUTPUT**: The results of labeling (answers given by Tolokers).
   - **CONFIDENCE**: The response significance according to the [Dawid-Skene model](https://toloka.ai/docs/guide/concepts/result-aggregation.html#aggr__dawid-skene).

## See also

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Template Builder — image comparison](https://toloka.ai/en/docs/template-builder/templates/sbs-image)
- [Toloka-Kit — image comparison](https://github.com/Toloka/toloka-kit/blob/main/examples/4.ranking/side_by_side_image_comparision/side_by_side_comparision.ipynb)

## Datasets and reference

- [Sample dataset file with tasks](https://tlk.s3.yandex.net/dataset/toloka_logos/sbs.tsv)