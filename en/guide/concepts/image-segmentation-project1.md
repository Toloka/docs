# Project 1. Does the image contain a specific object?

In this [project](../../glossary.md#project), you ask the Tolokers if a photo contains traffic signs.

## Create a project {#create-project}

#### In the interface:

1. Choose a template:

    1. Open [Toloka for requesters]({{ yandex-toloka }}).

    1. Click the {% if locale == "en-com" %}**+ Create project**{% endif %} button.

    1. In the window that opens, find the {% if locale == "en-com" %}**Image classification**{% endif %} template and click {% if locale == "en-com" %}**Select**{% endif %}.

1. Provide general information:

    1. In the {% if locale == "en-com" %}**Name to show Tolokers**{% endif %} field, enter `Are there traffic signs in the picture?`.

    1. In the {% if locale == "en-com" %}**Description for Tolokers**{% endif %} field, enter `Look at the picture and answer whether or not it shows any traffic signs.`

    1. Save the changes.

1. Edit the task interface in the editor you selected:

    {% list tabs %}

    - Template Builder

        1. The task interface describes how the elements should be arranged in the task.

        The template has pre-configured validation. The Toloker won't be able to submit a response without selecting one of the options.

        For more information, see the Template Builder Help:

        - [Setting up conditions]({{ tb-conditions }}).
        - [Image classification]({{ tb-image-classification }}) template.

        1. On the **Configuration** panel, replace lines 19 to 28 in the code:

        {% if locale == "en-com" %}

        ```json
        "label": "What is the cat's mood?",
        "options": [
        {
        "label": "Good",
        "value": "ok"
        },
        {
        "label": "Bad",
        "value": "bad"
        },
        ```

        {% endif %}
        with:
        {% if locale == "en-com" %}

        ```json
        "label": "Are there traffic signs in the picture?",
        "options": [
        {
        "label": "Yes",
        "value": "ok"
        },
        {
        "label": "No",
        "value": "bad"
        },
        ```

        {% endif %}

        1. Click **Show specifications** to see the input and output data fields.

           Input data fields are created from the code on the **Example of input data** tab.

           The output data fields depend on the components that use `data.output` and values supported by it.

           Learn more about [input and output data fields]({{ tb-create-specs }}) in the Template Builder Help.

           - Input data field: `image` — A link to an image.

             Change the data type to string to add links to your files.

           - Output data field: `result` — string for saving the Toloker's response.

            {% cut "What are input and output data?" %}

            **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

            **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

            If you add interface elements to the task template, the corresponding fields in the **Data specification** block will be created automatically.

            {% endcut %}

    - HTML/CSS/JS editor

        1. Edit the **HTML** block in the {% if locale == "en-com" %}**Task interface**{% endif %}.

        1. After the line with the image, enter the question:

        1. Change the labels on the response options: **Good** → **Yes**, **Bad** → **No**:

        1. Click the ![](../_images/tutorials/image-segmentation/preview-button.png) {% if locale == "en-com" %}**Preview task**{% endif %} button to view the task.

           {% if locale == "en-com" %}

           {{field type="radio" name="result" value="OK" label="Yes" hotkey="1"}}
           {{field type="radio" name="result" value="BAD" label="No" hotkey="2"}}
           {{field type="radio" name="result" value="404" label="Loading error" hotkey="3"}}
            ```
           {% endif %}

        1. Leave the **JS**, **CSS**, and {% if locale == "en-com" %}**Data specification**{% endif %} blocks unchanged.

           Learn more about {% if locale == "en-com" %}**Specifications**{% endif %} in [Input and output data](incoming.md).

        1. Click ![](../_images/tutorials/image-segmentation/preview-button.png) to see the Toloker's view of the task.

   1. Exit preview mode. In the lower-left corner, click {% if locale == "en-com" %}**Exit**{% endif %}. If there were errors when testing, check the code blocks that you entered.

   {% endlist %}

1. Save the changes.

1. In the {% if locale == "en-com" %}**Instructions for Tolokers**{% endif %} field, enter the [instructions](../../glossary.md#task-instruction) and add an image.

    1. **Instructions:**{% if locale == "en-com" %}

    ```
    Look at the image and answer whether there are any **traffic signs** in it.
    If there are, click **Yes**.
    If there aren't, click **No**.
    For example, there are traffic signs in the image, so the correct answer is **Yes**.
    ```

    {% endif %}

    1. To add an image, click ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button.png) and provide a link to the image you want to use as an example.
    1. Save the changes.

1. In the upper-right corner, click {% if locale == "en-com" %}**Finish**{% endif %}
    Learn more about working with the project in the [Project](project.md) section.

## Create a pool {#create-pool}

1. Open the page of the project titled **Are there traffic signs on the picture?**.

1. Click the {% if locale == "en-com" %}**Add a pool**{% endif %} button.

1. Specify the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. (optional) Add a {% if locale == "en-com" %}**Private comment**{% endif %}. This information is available only to you.

1. In the {% if locale == "en-com" %}**Audience**{% endif %} block in the {% if locale == "en-com" %}**Tolokers**{% endif %} section, filter Tolokers by language:

    1. Click {% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Add the {% if locale == "en-com" %}**Region by phone number**{% endif %} and {% if locale == "en-com" %}**Languages**{% endif %} filters and select Tolokers from Russia, Ukraine, Kazakhstan, and Belarus who indicated in their profiles that they know Russian.

    Tasks in pools will be automatically available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

1. (optional) In the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} section, specify the desired quality level. Improving quality may reduce the speed of task completion because the pool will be available to fewer Tolokers. Learn more in the [Speed/quality balance](adjust.md) section.

1. In the {% if locale == "en-com" %}**Price**{% endif %} block, find the {% if locale == "en-com" %}**Price per task suite**{% endif %} field and specify the price. For example, `0.01`.

1. In the {% if locale == "en-com" %}**Quality control**{% endif %} block, set up [quality control settings](control.md) for the pool:

    1. Click {% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Find the {% if locale == "en-com" %}**Rules**{% endif %} block in the list and choose {% if locale == "en-com" %}**Control tasks**{% endif %}.

    1. Set a rule for [control task](../../glossary.md#control-task): if the {% if locale == "en-com" %}**number of responses**{% endif %} to the control questions is **≥ 3** and {% if locale == "en-com" %}**correct responses (%)**{% endif %} to the control questions is **< 60**, then {% if locale == "en-com" %}**ban**{% endif %} the Toloker {% if locale == "en-com" %}**on project**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. Specify the **Control task** as a reason.

       Learn more in [Quality control](control.md).

1. In the {% if locale == "en-com" %}**Task overlap**{% endif %} section, enter `3` in the {% if locale == "en-com" %}**The number of Tolokers to complete each task**{% endif %} field.

1. In the {% if locale == "en-com" %}**Additional settings**{% endif %} block, enter `600` in the {% if locale == "en-com" %}**Time per task suite**{% endif %} field.

1. Click {% if locale == "en-com" %}**Create a pool**{% endif %}.


## Upload tasks {#upload-file}

Download the sample upload file. You can find it on the pool page. Use it to prepare your own [file](../../glossary.md#tsv-file-definition) with tasks.

1. Click {% if locale == "en-com" %}**Upload**{% endif %}. In the window that opens, you can download the file template.
    #### Use sample data

    If you want to see what your project will look like after the launch, but you don't have any labeling tasks yet, you can upload ready-made sample data to the pool.

    Click {% if locale == "en-com" %}**Use sample data**{% endif %} next to {% if locale == "en-com" %}**Attach the prepared file with data**{% endif %}. This lets you avoid any additional actions with files.

    Once you've finished working with the sample data and everything looks good, prepare your data and upload it to the pool.

1. In the window that opens, configure the file upload settings:

    1. Choose {% if locale == "en-com" %}**Smart mixing**{% endif %}.

    1. In the {% if locale == "en-com" %}**General tasks**{% endif %} field, specify `9`.

    1. In the {% if locale == "en-com" %}**Training tasks**{% endif %} field, specify `0`.

    1. In the {% if locale == "en-com" %}**Control tasks**{% endif %} field, specify `1`.

    1. Click {% if locale == "en-com" %}**Upload**{% endif %}.

    1. In the window that opens, choose the [file](../../glossary.md#tsv-file-definition) with tasks to upload and click {% if locale == "en-com" %}**Open**{% endif %}.

    1. In the window that opens, check the number of tasks and click {% if locale == "en-com" %}**Add**{% endif %}.

1. Create a [control task](goldenset.md).

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.

    {% note info %}

    If you selected something else instead of **smart mixing**, click **Edit**. If this button is missing, delete the file and upload it again.

    {% endnote %}

    1. In the window that opens, click {% if locale == "en-com" %}**Create control tasks**{% endif %}.

    1. In the window that opens, turn on the **result** option in the {% if locale == "en-com" %}**Create control task**{% endif %} section.

    1. Choose the correct answer to the question.

    1. Click {% if locale == "en-com" %}**Save and go to next**{% endif %}.

    1. Click **Are there traffic signs in the photo?** to exit the [task markup](../../glossary.md#task-markup) mode.

    {% note info %}

    In small pools, control tasks should be 10-20% of all tasks. Include different versions of correct responses in equal amounts. View the distribution of responses on the {% if locale == "en-com" %}**Edit tasks**{% endif %} page, {% if locale == "en-com" %}**Control tasks**{% endif %} tab.

    {% endnote %}

1. Click ![](../_images/other/b-start-pool.png) to start the pool.

    {% note warning %}

    The tasks will be completed by real Tolokers in Toloka. Recheck your project setup before you start the pool.

    {% endnote %}


## Get the results {#get-results}

1. Next to the {% if locale == "en-com" %}**Download results**{% endif %} button, click ![](../_images/other/drop-down.png).

1. Choose {% if locale == "en-com" %}**Dawid-Skene aggregation model**{% endif %} from the list. Learn more about [Result aggregation based on the Dawid-Skene model](result-aggregation.md#dawid-skene).

1. In the window that opens, click {% if locale == "en-com" %}**Yes**{% endif %}.

1. At the top of the page, click {% if locale == "en-com" %}**View the list of operations**{% endif %}.

    {% note info %}

    To track the progress, refresh the page from time to time. Aggregation takes from 5 to 20 minutes. You can start designing another project meanwhile.

    {% endnote %}

1. When the operation is complete, download the results file. To do this, click {% if locale == "en-com" %}**Download**{% endif %} in the {% if locale == "en-com" %}**Files**{% endif %} column.

1. Use the results file in [project 2](image-segmentation-project2.md).



## What's next {#what-next}

- Create [Project 2](image-segmentation-project2.md) to select objects.

{% include [contact-support](../_includes/contact-support-help.md) %}
