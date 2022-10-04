# Import source

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder]({{ tb-quickstart }}).

{% endnote %}


{% note info %}

This section describes how to edit the specification in an HTML/JS/CSS editor. You can also learn how to edit the specification in the [Template Builder]({{ tb-create-specs }}).

{% endnote %}


{% note info %}

This tutorial shows how to create a task interface in the **HTML/JS/CSS editor**. You can try creating a task interface in [Template Builder]({{ tb-quickstart }}).

{% endnote %}


Click {% if locale == "en-com" %}**Create project**{% endif %} and select the {% if locale == "en-com" %}**Transcribing audio recordings**{% endif %} template.

Click {% if locale == "en-com" %}**Create project**{% endif %}.

Select the {% if locale == "en-com" %}**Image classification**{% endif %} template.

Select the {% if locale == "en-com" %}**Product photo search**{% endif %} template.

Select the {% if locale == "en-com" %}**Image comparison (Side-by-side)**{% endif %} template.

Select the {% if locale == "en-com" %}**Customer survey**{% endif %} template.

Select the {% if locale == "en-com" %}**Product search relevance**{% endif %} template.

Select the {% if locale == "en-com" %}**Saptial Crowdsourcing**{% endif %} template.

Select the {% if locale == "en-com" %}**Photos of product and price tag**{% endif %} template.

1. Provide general information:

    1. Enter a clear name and a short description for the project. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

    1. Click **Save**.


Edit the task interface in the editor you selected:

Define which objects you are going to pass to the Tolokers and receive from them in response. To do this, add input and output fields in the **Data specification** section.

**Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

**Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

If you add interface elements to the task template, the corresponding fields in the **Data specification** block will be created automatically.

The project defines what the task will look like for a Toloker.

The task interface describes how the elements should be arranged in the task.

In the HTML interface, use the standard HTML tags and [special expressions](concepts/t-components.md) in double curly brackets for input and output data fields.

For this project, leave the **HTML**, **JS**, and **CSS** blocks unchanged.

In the **Task interface**, edit the **HTML** block.

To go back to the {% if locale == "en-com" %}**Projects**{% endif %}page, click {% if locale == "en-com" %}**Finish editing**{% endif %}.

To go back to the {% if locale == "en-com" %}**Projects**{% endif %}page, click {% if locale == "en-com" %}**Finish**{% endif %}.

Write short and clear [instructions](../glossary.md#task-instruction-ru).

Save the changes.

1. Click the ![](images/tutorials/image-segmentation/preview-button.png) {% if locale == "en-com" %}**Preview task**{% endif %} button to view the task.

    {% note info %}

    The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

    {% endnote %}


1. 1. Write short and clear instructions. Describe what needs to be done and give examples in them.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

    1. Click **Finish**.


1. Write short and clear instructions. Describe what needs to be done and give examples.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

    Field task instructions should be easy to read on a mobile phone screen.

1. Click **Finish**.


1. To add an image, click ![](images/tutorials/image-segmentation/wsdm-tutorial-button.png) and provide a link to the image you want to use as an example.


Download the sample upload file. You can find it on the pool page. Use it to prepare your own [file](../glossary.md#tsv-file-definition-ru) with tasks.

Click **Show specifications** to see the input and output data fields.

Input data fields are created from the code on the **Example of input data** tab.

The output data fields depend on the components that use `data.output` and values supported by it.

Learn more about [input and output data fields]({{ tb-create-specs }}) in the Template Builder Help.

To specify what data you will pass to the Toloker and receive in response, create input and output data fields.

#### What are input and output data?

**Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

**Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

Input data fields are created from the code on the **Example of input data** tab.

The output data fields depend on the components that use `data.output` and values supported by it.

Click **Show specifications** to see the input and output data fields.

Learn more about [input and output data fields]({{ tb-create-specs }}) in the Template Builder Help.

Learn more about [input and output data fields]({{ tb-create-specs }}) in the Template Builder Help.

1. In the window that opens, check if the task options work correctly. In the lower-right corner, click **Submit**.

1. Exit preview mode.

    In the lower-left corner, click **Exit**. If there were errors when testing, check the code blocks that you entered.


Learn more about the **Specification** parameters in [Input and output data](concepts/incoming.md).

To exit preview mode, click **Exit** in the lower-left corner.

Learn more in the [Project](concepts/project.md) section

The **Name** and **Description** fields are used to help the Toloker distinguish one task from another when they choose a task on the map. In this project, these fields contain links to the input data fields to show the point's name and address. You can leave these fields unchanged or write something else in them.

The **Settings for displaying field tasks** block is used to help the Toloker distinguish one task from another when they select a task on the map. In this project, the **Header format** and **Short description format** fields contain links to the input data fields to show the point's name and address. You can leave these fields unchanged or write something else in them.

1. Click ![](images/tutorials/image-segmentation/preview-button.png) to see the Toloker's view of the task.

    {% note info %}

    The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

    {% endnote %}

    Check if the task options work correctly. In the lower-right corner, click **Submit**.

    To exit preview mode, click **Exit** in the lower-left corner. If there were errors when testing, check the code blocks that you entered.


1. Click ![](images/tutorials/image-segmentation/preview-button.png) to see the Toloker's view of the task.

    {% note info %}

    The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

    {% endnote %}

    Check if the task options work correctly. In the lower-right corner, click **Submit**.

    To exit preview mode, click **Exit** in the lower-left corner.


1. In the template, the **Map** option is enabled automatically. So a user will see tasks as points on the map and be able to choose the ones they want.

    The **Name** and **Description** fields are used to help the Toloker distinguish one task from another when they choose a task on the map. In this project, these fields contain links to the input data fields to show the point's name and address. You can leave these fields unchanged or write something else in them.


1. The **Settings for displaying field tasks** block is used to help the Toloker distinguish one task from another when they select a task on the map. In this project, the **Header format** and **Short description format** fields contain links to the input data fields to show the point's name and address You can leave these fields unchanged or write something else in them.


1. Attach the documents:

    #### For individuals

    - A copy of the photo page of your passport.

    #### For legal entities

    - A certificate of incorporation.

    - A business card with bank details and contact information.


The service delivery report and the tax invoice are formed on the first day of each month following the reporting month for the amount spent in the previous month (excluding the promo code bonus).

Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

New tutorials

Step 1. Choose a preset

We recommend starting with a project preset for easier configuration and better results.

1. 1. In the main menu, choose the {% if locale == "en-com" %}**Projects**{% endif %} tab, and click {% if locale == "en-com" %}**Create a project**{% endif %}.
    1. Select the {% if locale == "en-com" %}**Image classification**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose solution**{% endif %} in the pop-up tab.

Step 2. Project settings

Set up how your tasks will look for Tolokers. Tolokers are people around the world who get paid for completing your tasks.

1. Under {% if locale == "en-com" %}**General information**{% endif %}, add the project name and description.

    - {% if locale == "en-com" %}**Name to show performers**{% endif %}: In 2–5 words, state the general idea of the project.
    - {% if locale == "en-com" %}**Description for performers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

1. {% note info %}

    This tutorial uses [Template Builder](https://toloka.ai/en/docs/template-builder/), but you can use the [HTML/JS/CSS editor](concepts/spec.md) for the same purpose.

    {% endnote %}

    1. Raw task data is stored in the XSLX, TSV, or JSON format. The labeling results are presented in a TSV file. The {% if locale == "en-com" %}**Data specification**{% endif %} section determines which parameters these files might contain.

    Click {% if locale == "en-com" %}**Show specifications**{% endif %} and check the values:

    - {% if locale == "en-com" %}**Input data**{% endif %}: Parameters in the file with raw task data.
    - {% if locale == "en-com" %}**Output data**{% endif %}: Parameters in the file with labeling results.

    {% if locale == "en-com" %}**Input data**{% endif %} and {% if locale == "en-com" %}**Output data**{% endif %} [match the task interface](https://toloka.ai/en/docs/template-builder/operations/create-specs) you set up in {% if locale == "en-com" %}**Template Builder**{% endif %}. Check that there are fields for all data types you use for your tasks, and for the ones you want to see in the results file.

1. Under {% if locale == "en-com" %}**Instructions for performers**{% endif %}, add the instructions Tolokers will see when they start doing your tasks. You can add text, tables, and images to your instructions.

    Check the sample text of the instructions, and update it to fit your project.

    {% note info %}

    When writing instructions, remember that most performers don’t know anything about your tasks beforehand. Make sure your instructions are as clear as possible, but not too wordy. For successful data labeling, try to strike a balance between covering all the essentials and keeping it short. Learn more in our [knowledge base](https://toloka.ai/knowledgebase/instruction/).

    {% endnote %}

1. To save your data and continue, click {% if locale == "en-com" %}**Create a project**{% endif %}.

Step 3. Create a pool

A _pool_ is a set of tasks sent out to Tolokers at the same time. One project can have many pools. When creating a pool, you set up pricing, audience filters for Tolokers, and quality control.

1. Click {% if locale == "en-com" %}**Create new pool**{% endif %}.
1. Under {% if locale == "en-com" %}**General information**{% endif %}, set the {% if locale == "en-com" %}**Pool name**{% endif %}.
1. Under {% if locale == "en-com" %}**Audience**{% endif %}, set up filters to select Tolokers for your pool.

    1. Clear {% if locale == "en-com" %}**My tasks may contain shocking or pornographic content**{% endif %} if your project has none of those.
    1. To select Tolokers based on their language, location, age, gender, and other parameters, click the {% if locale == "en-com" %}**Add filter**{% endif %} button.

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

1. In {% if locale == "en-com" %}**Price**{% endif %}, set up how much a single task will cost for you.

    1. In the {% if locale == "en-com" %}**Overlap**{% endif %} field, define how many Tolokers must do each task.

    1. At the bottom of the {% if locale == "en-com" %}**Price**{% endif %} section, you see {% if locale == "en-com" %}**Price per 1 task**{% endif %}. This is the amount of money paid per task.

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

Step 4. Upload data

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.
1. Create the tasks for Tolokers:
    1. To download a template, click one of the buttons:
    - {% if locale == "en-com" %}**Template in XLSX**{% endif %}
    - {% if locale == "en-com" %}**Template in TSV**{% endif %}
    - {% if locale == "en-com" %}**Template in JSON**{% endif %}

    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.
    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. Tasks are shown to Tolokers in suites. A suite is a single page with multiple tasks. Define how many tasks to include per suite:

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.
1. To create control tasks, add correct answers to some of your tasks.

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.
    1. On the {% if locale == "en-com" %}**Edit tasks**{% endif %} page, click {% if locale == "en-com" %}**Create control tasks**{% endif %}.

    1. {% note info %}

    For large pools (over 1000 tasks), we recommend adding at least 1% of control tasks to the pool. For small pools (around 100 tasks), you need 10% control tasks.

    {% endnote %}


Step 5. Start labeling

1. Make sure you have [topped up your account](concepts/refill.md).
1. To send the tasks to Tolokers and begin the labeling process, click {% if locale == "en-com" %}**Start labeling**{% endif %}.

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

Step 6. See the results

1. You can see the labeling progress on the pool page. Wait until the labeling is completed.

1. Open the same drop-down menu again, and click {% if locale == "en-com" %}**View aggregations list**{% endif %}.

- Make sure you are [registered](concepts/access.md) in Toloka as a requester.
- [Top up](concepts/refill.md) your Toloka account. If you are unsure about the budget, you can do that later in this tutorial. Toloka will display the budget estimate for your project.
