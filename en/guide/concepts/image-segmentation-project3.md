# Project 3. Are the bounding boxes correct?

In this [project](../../glossary.md#project), Tolokers will determine if traffic signs were selected correctly on the images in [project 1](image-segmentation-project1.md), and submit the responses in [project 2](image-segmentation-project2.md).

## Create a project {#create-project}

#### In the interface:

1. Choose a preset:

    1. Click **Create project**.
    1. Select the **Object recognition & detection** preset.
    1. Click **Choose this preset**.

1. Provide general information:

    1. In the **Name for Tolokers** field, enter `Are the traffic signs outlined correctly?`.
    1. In the **Description for Tolokers** field, enter `Look at the image and decide whether the traffic signs are outlined correctly or not`.
    1. Optionally add a **Private comment**.

1. Edit the task interface. The output data format depends on the interface editor, so choose the same editor as in [Project 2](image-segmentation-project2.md#interface-tb-html).

   {% list tabs %}

    - Template Builder

      1. Create a template based on the [Checking the selected area](https://ya.cc/t/Z9GC6HzT3ttEf6) example that uses [Component for image labeling](../../template-builder/reference/field.image-annotation.md).

      1. To see the input and output data fields, click **Show specifications** in the **Data specification** section.

          Input data fields used in the project:

          - `image` — image address;
          - `result` — an array with the selected area coordinates;
          - `assignment_id` — task ID.

          The Toloker's response will be recorded in the `verdict` output data field.

      1. Turn on the **Define data specification manually** option.

      1. Click ![](../_images/other/code.svg) to switch graphic mode to JSON format.

      1. Remove the template code from the **Input data** field and enter the following code:

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

      1. Remove the template code from the **Output data** field and enter the following code:

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

      1. Prepare **Task interface**:

          1. Connect the $TOLOKA_ASSETS/js/image-annotation.js library (click ![](../_images/settings.svg) in the **Task interface** block on the project page).

          1. In the **html** block, replace the current code with the following:
              

              ```plaintext
              <!-- editor for selecting objects that lets you add an area in advance -->
              {{field type="image-annotation" name="object" src=image annotations=selection}}

              <!-- buttons for responses -->
              {{field type="radio" name="result" value="OK" label="Correct" hotkey="1"}}
              {{field type="radio" name="result" value="BAD" label="Incorrect" hotkey="2"}}
              ```

              

          1. In the **css** block, replace the code with the following:

              

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

             

      1. Configure the **Data specification** section:

         1. Click ![](../_images/other/code.svg) to switch graphic mode to JSON format.

         1. Remove the template code from the **Input data** field and enter the following code:

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

         1. Remove the template code from the **Output data** field and enter the following code:

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

           Learn more about **Specifications** in [Input and output data](incoming.md).

      1. Click the ![](../_images/tutorials/image-segmentation/preview-button.svg) **Preview task** button to view the task.

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

    

    ```plaintext
    Look at the image and answer the question: **Are all traffic signs outlined correctly?**
    If there are, click **Yes**.
    If there isn't, click **No**.
    For example, road signs are outlined correctly, so the correct answer is **Yes**.
    ```

    

    {% note tip %}

    If you want to add a task examples in the instruction, complete it yourself in the preview mode. Take screenshots, upload them to photo hosting or cloud storage and insert image links in the instructions by clicking the ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button.svg) button on the toolbar.

    {% endnote %}

1. Click **Create project**.

## Create a pool {#create_pool}

1. Open the project page titled **Are the traffic signs outlined correctly?**.

1. Click **Add a pool** on the project page.

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. {% include [tutorials-language-filter](../_includes/tutorials/language-filter.md) %}

    1. {% include [tutorials-shocking-content](../_includes/tutorials/shocking-content-filter.md) %}

    1. {% include [tutorials-platform-filter](../_includes/tutorials/platform-filter.md) %}

    1. Add another filter. Click **Add filter**.

    1. Find the **Skills** block in the list and select the **My skills** skill.

    1. In the **Skills** field, select **Area selection**.

    1. In the **?** field specify `=`.

    1. Leave the **Missing** field blank.

1. (optional) In the **Speed/quality balance** section, specify the desired quality level. Improving quality may reduce the speed of task completion because the pool will be available to fewer Tolokers. Learn more in the [Speed/quality balance](adjust.md) section.

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite, $**, set the amount of money to pay per task suite done by one Toloker. For example, `0.01`.

    1. Enter `3` in the **Overlap** field.

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. Click **Add a quality control rule**.

    1. Find the **Rules** block in the list and choose **Majority vote**.

    1. In the **Accept as majority** field, soecify `2`.

    1. Set the rule: if **number of responses** **≥ 10** and **correct responses (%)** **< 50**, then **ban** the Toloker **on project** for **10 days**. Specify the reason **Doesn't match the majority**.

        {% note info %}

        The rule takes effect when the number of responses for the task is equal to the [overlap](../../glossary.md#overlap).

        {% endnote %}

    Learn more in [Quality control](control.md).

1. At the **Add optional pool settings** step:

    1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

        The time should be long enough to read the instructions and wait for task data to load. For example, `600` seconds.

    1. Turn on the **Keep task order** option.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

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

        You can prepare the file in **Notepad**. To transfer data to **Microsoft Excel**, use **Text Import Wizard** and disable the **Text qualifier** option.

        {% endnote %}

    1. Upload the file to the **Are the traffic signs outlined correctly?** pool:

        1. Open the **Are the traffic signs outlined correctly?** pool.

        1. Click **Upload**. 

        1. Click **Drop file here or select**, and upload the file you’ve just made.

        1. Click **Continue**.

        1. Choose **Set manually**.

        1. In the **Tasks per suite** field, specify `10`.

        1. Click **Combine tasks into suites**.

        1. On the pool page, click **Preview**. Make sure that the task displays images with the selected objects.

            {% note tip %}

            If there are no outlined objects, make sure that quotes are properly used in the **INPUT:selection** column in the file. Make sure that the [interface parameters](#task-interface) are set correctly.

            {% endnote %}

1. Click ![](../_images/other/b-start-pool.svg) to start the pool.

## Download the reviewed results {#get_results}

1. Next to the **Download results** button, click ![Drop-down button](../_images/other/drop-down.svg).

1. Choose **Dawid-Skene aggregation model** from the list. Learn more about [Result aggregation based on the Dawid-Skene model](result-aggregation.md#dawid-skene).

1. In the window that opens, click **Yes**.

1. At the top of the page, click **View the list of operations**.

    {% note info %}

    To track the progress, refresh the page from time to time. Aggregation takes from 5 to 20 minutes. You can start designing another project meanwhile.

    {% endnote %}

1. When the operation is complete, download the results file. To do this, click **Download** in the **Files** column.

1. Use the results file in [project 2](image-segmentation-project2.md).

## Check the completed tasks {#check_results}

Since the [manual review](image-segmentation-project2.md) option is enabled in the pool settings for **project 2**, you should check the Tolokers' responses within the time limit set in the **Review period** field.

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

    1. Click **Review assignments**.

    1. Click **Upload results**.

    1. In the window that opens, choose the results file you want to upload and click **Open**.

    1. In the window that opens, compare the number of tasks in the **Processed successfully** and **Total submitted** fields on the pool page.

    1. Click **Add**.

    1. In the window that opens, click **Close**.

    1. When setting up a pool in the [second project](image-segmentation-project2.md) you turned on the **Recompletion of the rejected tasks** option.

        In this case, the pool automatically reopens and the assignments are reassigned to other Tolokers. When they're completed, send the results for review. Then download the results, check them, and upload the reviewed results. You can reject assignments as many times as you want to get more accurate results.

- Review assignments in the pool interface

    1. Open the pool page in [project 2](image-segmentation-project2.md).

    1. Click **View assignments**.

    1. Hover over the line of the assignment you want to check.

    1. In the **Status** column, you will see the buttons for accepting (![](../_images/tutorials/image-segmentation/wsdm-tutorial-button-yes.svg)) or rejecting (![](../_images/tutorials/image-segmentation/wsdm-tutorial-button-no.svg)) the completed assignment. If you reject the assignment, enter a comment in the window that opens and click **Done**.

{% endlist %}

## What's next {#what-next}

- Learn more about [decomposition](solution-architecture.md).

{% include [contact-support](../_includes/contact-support.md) %}