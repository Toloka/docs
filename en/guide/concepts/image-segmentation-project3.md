# Project 3. Are the bounding boxes correct?

In this [project](../../glossary.md#project), Tolokers will determine if traffic signs were selected correctly on the images in [project 1](image-segmentation-project1.md), and submit the responses in [project 2](image-segmentation-project2.md).

## Create a project {#create-project}

#### In the interface:

1. Choose a preset:

    1. Click **Create project**.
    1. Select the **Object recognition & detection** preset.
    1. Click **Choose solution**.

1. Provide general information:

    1. In the **Name for Tolokers** field, enter `Are the traffic signs outlined correctly?`.
    1. In the **Description for Tolokers** field, enter `Look at the image and decide whether the traffic signs are outlined correctly or not`.
    1. Optionally add a **Private comment**.

1. Edit the task interface. The output data format depends on the interface editor, so choose the same editor as in [Project 2](image-segmentation-project2.md#interface-tb-html).

   {% list tabs %}

    - Template Builder

      1. Create a template based on the [Checking the selected area](https://clck.ru/sFyNY) example that uses [Component for image labeling](../../template-builder/reference/field.image-annotation.md).

      1. To see the input and output data fields, click {% if locale == "en-com" %}**Show specifications**{% endif %} in the {% if locale == "en-com" %}**Data specification**{% endif %} section.

          Input data fields used in the project:

          - `image` — image address;
          - `result` — an array with the selected area coordinates;
          - `assignment_id` — task ID.

          The Toloker's response will be recorded in the `verdict` output data field.

      1. Turn on the **Define data specification manually** option.

      1. Click ![](../_images/other/code.png) to switch graphic mode to JSON format.

      1. Remove the template code from the {% if locale == "en-com" %}**Input data**{% endif %} field and enter the following code:

          ```json
          {
            "image": {
              "type": "url",
              "hidden": false,
              "required": true
            },
            "result": {
              "type": "array_json",
              "hidden": false,
              "required": false
            },
              "assignment_id": {
              "type": "string",
              "hidden": true,
              "required": true
            }
          }
          ```

      1. Remove the template code from the {% if locale == "en-com" %}**Output data**{% endif %} field and enter the following code:

          ```json
          {
            "verdict": {
              "type": "string",
              "hidden": false,
              "required": true,
              "allowed_values": [
                "OK",
                "BAD"
              ]
            }
          }
          ```

    - HTML/CSS/JS editor

      1. Prepare {% if locale == "en-com" %}**Task interface**{% endif %}:

          1. Connect the $TOLOKA_ASSETS/js/image-annotation.js library (click ![](t-components/../../_images/settings.svg) in the **Task interface** block on the project page).

          1. In the **html** block, replace the current code with the following:
              {% if locale == "en-com" %}

              ```plaintext
              <!-- editor for selecting objects that lets you add an area in advance -->
              {{field type="image-annotation" name="object" src=image annotations=selection}}

              <!-- buttons for responses -->
              {{field type="radio" name="result" value="OK" label="Correct" hotkey="1"}}
              {{field type="radio" name="result" value="BAD" label="Incorrect" hotkey="2"}}
              ```

              {% endif %}

          1. In the **css** block, replace the code with the following:

              {% if locale == "en-com" %}

              ```css
              /* hide the button for polygon selection */
              .image-annotation-editor__shape-polygon {
                  display: none;
              }

              /* adjust the interface height */
              .image-annotation-editor__annotation-layer {
                  height: max-content;
              }
              ```

             {% endif %}

      1. Configure the **Data specification** section:

         1. Click ![](../_images/other/code.png) to switch graphic mode to JSON format.

         1. Remove the template code from the {% if locale == "en-com" %}**Input data**{% endif %} field and enter the following code:

            ```json
            {
              "image": {
                "type": "url",
                "hidden": false,
                "required": true
              },
              "selection": {
                "type": "array_json",
                "hidden": false,
                "required": false
              },
              "assignment_id": {
                "type": "string",
                "hidden": true,
                "required": true
              }
            }
            ```

         1. Remove the template code from the {% if locale == "en-com" %}**Output data**{% endif %} field and enter the following code:

            ```json
            {
              "result": {
                "type": "string",
                "hidden": false,
                "required": true,
                "allowed_values": [
                  "OK",
                  "BAD"
                ]
              }
            }
            ```

           Learn more about {% if locale == "en-com" %}**Specifications**{% endif %} in [Input and output data](incoming.md).

      1. Click the ![](../_images/tutorials/image-segmentation/preview-button.png) {% if locale == "en-com" %}**Preview task**{% endif %} button to view the task.

         {% note info %}

         The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

         {% endnote %}

      1. Click **Change input data**.
      1. In the **selection** field, add an example of input data:

          ```
          [{"data":{"p1":{"x":0.472,"y":0.413},"p2":{"x":0.932,"y":0.877}},"type":"rectangle"},
          {"data":[{"x":0.143,"y":0.807},{"x":0.317,"y":0.87},{"x":0.511,"y":0.145},{"x":0.328,"y":0.096},{"x":0.096,"y":0.554}],"type":"polygon"}]
          ```

      1. If everything is OK, close the preview tab. If not, check the data you inserted in the code blocks.

   {% endlist %}

1. Save the changes.

1. Write instructions for Tolokers:

    **Instructions:**

    {% if locale == "en-com" %}

    ```plaintext
    Look at the image and answer the question: **Are all traffic signs outlined correctly?**
    If there are, click **Yes**.
    If there isn't, click **No**.
    For example, road signs are outlined correctly, so the correct answer is **Yes**.
    ```

    {% endif %}

    {% note tip %}

    If you want to add a task examples in the instruction, complete it yourself in the preview mode. Take screenshots, upload them to photo hosting or cloud storage and insert image links in the instructions by clicking the ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button.png) button on the toolbar.

    {% endnote %}

1. Click **Create project**.

## Create a pool {#create_pool}

1. Open the project page titled **Are the traffic signs outlined correctly?**.

1. Click the {% if locale == "en-com" %}**Add a pool**{% endif %} button.

1. Specify the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. (optional) Add a {% if locale == "en-com" %}**Private comment**{% endif %}. This information is available only to you.

1. Filter Tolokers in the {% if locale == "en-com" %}**Tolokers**{% endif %} section of the {% if locale == "en-com" %}**Audience**{% endif %} block:

    1. Click {% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Add the {% if locale == "en-com" %}**Region by phone number**{% endif %} and {% if locale == "en-com" %}**Languages**{% endif %} filters and select Tolokers from Russia, Ukraine, Kazakhstan, and Belarus who indicated in their profiles that they know Russian.

    1. Add another filter. Click {% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Find the {% if locale == "en-com" %}**Skills**{% endif %} block in the list and select the {% if locale == "en-com" %}**My skills**{% endif %} skill.

    1. In the {% if locale == "en-com" %}**Skills**{% endif %} field, select **Area selection**.

    1. In the **?** field specify `=`.

    1. Leave the {% if locale == "en-com" %}**Missing**{% endif %} field blank.

    Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

1. (optional) In the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} section, specify the desired quality level. Improving quality may reduce the speed of task completion because the pool will be available to fewer Tolokers. Learn more in the [Speed/quality balance](adjust.md) section.

1. In the {% if locale == "en-com" %}**Price**{% endif %} block, find the {% if locale == "en-com" %}**Price per task suite**{% endif %} field and specify the price. For example, `0.01`.

1. In the {% if locale == "en-com" %}**Quality control**{% endif %} block, set up [quality control settings](control.md) for the pool:

    1. Click {% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Find the {% if locale == "en-com" %}**Rules**{% endif %} block in the list and choose {% if locale == "en-com" %}**Majority vote**{% endif %}.

    1. In the {% if locale == "en-com" %}**Accept as majority**{% endif %} field, soecify `2`.

    1. Set the rule: if {% if locale == "en-com" %}**number of responses**{% endif %} **≥ 10** and {% if locale == "en-com" %}**correct responses (%)**{% endif %} **< 50**, then {% if locale == "en-com" %}**ban**{% endif %} the Toloker {% if locale == "en-com" %}**on project**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. Specify the reason **Doesn't match the majority**.

        {% note info %}

        The rule takes effect when the number of responses for the task is equal to the [overlap](../../glossary.md#overlap).

        {% endnote %}

    Learn more in [Quality control](control.md).

1. In the {% if locale == "en-com" %}**Task overlap**{% endif %} section, enter `3` in the {% if locale == "en-com" %}**The number of Tolokers to complete each task**{% endif %} field.

1. In the {% if locale == "en-com" %}**Additional settings**{% endif %} block:

    1. Enter `600` in the {% if locale == "en-com" %}**Time per task suite**{% endif %} field.

    1. Turn on the {% if locale == "en-com" %}**Keep task order**{% endif %} option.

1. Click {% if locale == "en-com" %}**Create a pool**{% endif %}.


## Prepare and upload the results file. {#upload_file}

1. Prepare a [file](../../glossary.md#tsv) with tasks.

    1. In the text or spreadsheet editor, open the file that you received after aggregating the results in [project 2](image-segmentation-project2.md).
    1. Leave the `INPUT:image` column unchanged.

    1. Change the `OUTPUT:result` column name to `INPUT:selection`.

    1. Rename the `ASSIGNMENT:assignment_id` column to `INPUT:assignment_id`.

    1. Delete the `ACCEPT:verdict:` and `ACCEPT:comment:` columns:

    1. Add input data, for example:
    ```
    [{""type"":""rectangle"",""data"":{""p1"":{""x"":0.2421,""y"":0.98871},""p2"":{""x"":0.93663,""y"":0.8776}}}]
    ```
    and save the file.

    {% note tip %}

    You can prepare the file in {% if locale == "en-com" %}**Notepad**{% endif %}. To transfer data to **Microsoft Excel**, use {% if locale == "en-com" %}**Text Import Wizard**{% endif %} and disable the {% if locale == "en-com" %}**Text qualifier**{% endif %} option.

    {% endnote %}

1. Upload the file to the **Are the traffic signs outlined correctly?** pool:

    1. Open the **Are the traffic signs outlined correctly?** pool.

    1. Click {% if locale == "en-com" %}**Upload**{% endif %}. In the window that opens, configure the file upload settings.

    1. Choose {% if locale == "en-com" %}**Set manually**{% endif %}.

    1. In the {% if locale == "en-com" %}**Tasks per suite**{% endif %} field, specify `10`.

    1. Click {% if locale == "en-com" %}**Upload**{% endif %}.

    1. In the window that opens, choose the tasks file you want to upload and click {% if locale == "en-com" %}**Open**{% endif %}.

    1. In the window that opens, check the number of tasks and click {% if locale == "en-com" %}**Add**{% endif %}.

    1. On the pool page, click {% if locale == "en-com" %}**Preview**{% endif %}. Make sure that the task displays images with the selected objects.

        {% note tip %}

        If there are no outlined objects, make sure that quotes are properly used in the **INPUT:selection** column in the file. Make sure that the [interface parameters](#task-interface) are set correctly.

        {% endnote %}

1. Click ![](../_images/other/b-start-pool.png) to start the pool.

    {% note warning %}

    The tasks will be completed by real Tolokers in Toloka. Recheck your project setup before you start the pool.

    {% endnote %}

## Download the reviewed results {#get_results}

1. Next to the {% if locale == "en-com" %}**Download results**{% endif %} button, click ![](../_images/other/drop-down.png).

1. Choose {% if locale == "en-com" %}**Dawid-Skene aggregation model**{% endif %} from the list. Learn more about [Result aggregation based on the Dawid-Skene model](result-aggregation.md#dawid-skene).

1. In the window that opens, click {% if locale == "en-com" %}**Yes**{% endif %}.

1. At the top of the page, click {% if locale == "en-com" %}**View the list of operations**{% endif %}.

    {% note info %}

    To track the progress, refresh the page from time to time. Aggregation takes from 5 to 20 minutes. You can start designing another project meanwhile.

    {% endnote %}

1. When the operation is complete, download the results file. To do this, click {% if locale == "en-com" %}**Download**{% endif %} in the {% if locale == "en-com" %}**Files**{% endif %} column.

1. Use the results file in [project 2](image-segmentation-project2.md).

## Check the completed tasks {#check_results}

Since the [Non-automatic acceptance](image-segmentation-project2.md) option is enabled in the pool settings for {% if locale == "en-com" %}**project 2**{% endif %}, you should check the Tolokers' responses within the time limit set in the {% if locale == "en-com" %}**Review period**{% endif %} field.

You can check the results in two ways:

- In the results file.
- In the pool interface.

{% list tabs %}

- Review assignments in the results file

    1. In the text or spreadsheet editor, open the file you received after aggregating the results.

    1. Prepare the file:

        1. Add a column named `ACCEPT:verdict` with the review results.

        1. Add a column named `ACCEPT:comment` with comments for Tolokers if responses were rejected. For example, comment on which part of the instructions wasn't followed.

        1. Rename the `INPUT:assignment_id` column to `ASSIGNMENT:assignment_id`.

    1. Fill in the `ACCEPT:verdict:` and `ACCEPT:comment:` columns:

        - If the aggregate result of the assignment is OK, put `+` to accept it.

        - If the aggregate result of the assignment is incorrect or it doesn't open, put `-` to reject it. Enter the reason for rejecting the task in the `ACCEPT:comment:` field, for example, `The object isn't selected or is selected incorrectly.`

        {% note tip %}

        You can use the awk commands to outline images on Linux and MacOS devices:

        ```shell
        awk 'BEGIN {FS=OFS="\t";} NR>1 {if($4~"OK"){ print $1, "+", ""; }else{ print $1, "-", "The object isn't selected or is selected incorrectly.";}}' <post_accept_res>.tsv > <review_res>.tsv
        ```

        {% endnote %}

    1. Delete all the other columns.

    1. Save the file in `TSV` format.

    1. Open the pool page in [project 2](image-segmentation-project2.md).

    1. Click {% if locale == "en-com" %}**Review assignments**{% endif %}.

    1. Click {% if locale == "en-com" %}**Upload results**{% endif %}.

    1. In the window that opens, choose the results file you want to upload and click {% if locale == "en-com" %}**Open**{% endif %}.

    1. In the window that opens, compare the number of tasks in the {% if locale == "en-com" %}**Processed successfully**{% endif %} and {% if locale == "en-com" %}**Total submitted**{% endif %} fields on the pool page.

    1. Click {% if locale == "en-com" %}**Add**{% endif %}.

    1. In the window that opens, click {% if locale == "en-com" %}**Close**{% endif %}.

    1. When setting up a pool in the [second project](image-segmentation-project2.md) you turned on the {% if locale == "en-com" %}**Recompletion of the rejected tasks**{% endif %} option.

        In this case, the pool automatically reopens and the assignments are reassigned to other Tolokers. When they're completed, send the results for review. Then download the results, check them, and upload the reviewed results. You can reject assignments as many times as you want to get more accurate results.

- Review assignments in the pool interface

    1. Open the pool page in [project 2](image-segmentation-project2.md).

    1. Click {% if locale == "en-com" %}**View assignments**{% endif %}.

    1. Hover over the line of the assignment you want to check.

    1. In the {% if locale == "en-com" %}**Status**{% endif %} column, you will see the buttons for accepting (![](../_images/tutorials/image-segmentation/wsdm-tutorial-button-yes.png)) or rejecting (![](../_images/tutorials/image-segmentation/wsdm-tutorial-button-no.png)) the completed assignment. If you reject the assignment, enter a comment in the window that opens and click {% if locale == "en-com" %}**Done**{% endif %}.

{% endlist %}

## What's next {#what-next}

- Learn more about [decomposition](solution-architecture.md).

{% include [contact-support](../_includes/contact-support-help.md) %}