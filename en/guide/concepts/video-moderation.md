# Video classification

{% note info %}

Run the project in the [Sandbox]({{ sandbox }}) first. This helps you avoid making mistakes and spending money on a task that isn't working right.

{% endnote %}


[Projects](../../glossary.md#project-ru) of this type are intended for video classification. You can use them for:
- Content moderation.
- Sorting video clips by specified categories.
- Rating video clips based on how much the Tolokers like them.
- Detecting noise and other visual imperfections in the video.

For example, you have a lot of video clips, and you need to determine which ones are of higher quality. To do this, create a task in which the Tolokers will watch the video clips and evaluate their quality.

## Before you start {#before_start}

- To use your video clips in the project, you need to upload them to a storage from which you can get file links. For example, your server, video hosting, or cloud storage:

    - [Instructions](use-object-storage.md) on how to use files from Yandex Cloud.
    - If you use video clips from YouTube, replace the `https://www.youtube.com/watch?v=example` links with `https://www.youtube.com/embed/example`.

- Make sure that the video clips look the same in the desktop and mobile versions of Toloka. A video clip may not play or play incorrectly in the mobile version. In this case, when creating a pool, restrict access to the pool for the Tolokers with mobile devices.

    Learn more about [configuring tasks for mobile devices](mobile.md).

    {% note info %}

    The video player supports only MP4 format with H.264 or H.265 encoding.

    {% endnote %}

- If you have a complex project, register in the [sandbox](sandbox.md) and create a project there. There you can:

    1. Test the project settings as a Toloker.
    1. Then [transfer](sandbox.md#export) them to the {% if locale == "en-com" %}**production version**{% endif %}.
    1. Launch the project for real Tolokers.

    This helps you avoid making mistakes and spending unnecessary money on a task that doesn't work.


## Create a project {#create-project}

Open [Toloka for requesters]({{ yandex-toloka }}).

#### In the interface:

1. Choose a template:

    1. Click {% if locale == "en-com" %}**Create project**{% endif %}.

    1. Select the {% if locale == "en-com" %}**Hand gesture classification**{% endif %} template.

1. Provide general information:

    1. Enter a clear name and a short description for the project. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

    1. Click **Save**.

1. Edit the task interface in the editor you selected:

    #### Template Builder

    1. The task interface describes how the elements should be arranged in the task.

    Use the ready-made template for this project with pre-configured validation, keyboard shortcuts, and task layout. The Toloker won't be able to submit a response without selecting one of the options.

    For more information, see the Template Builder Help:

    - [Setting up conditions]({{ tb-conditions }}).

    - Setting up the [Video moderation]({{ tb-video-moderation }}) template.

    1. To specify what data you will pass to the Toloker and receive in response, create input and output data fields.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

    Input data fields are created from the code on the **Example of input data** tab.

    The output data fields depend on the components that use `data.output` and values supported by it.

    Click **Show specifications** to see the input and output data fields.

    Learn more about [input and output data fields]({{ tb-create-specs }}) in the Template Builder Help.

    In this project:

    - Input data field: `video` — A link to a video.

    - Output data field: `result` — string for saving the Toloker's response.

    #### HTML/CSS/JS editor

    1. The task interface describes how the elements should be arranged in the task.

    In the HTML interface, use the standard HTML tags and [special expressions](t-components.md) in double curly brackets for input and output data fields.

    For this project, leave the **HTML**, **JS**, and **CSS** blocks unchanged.

    #### If you use a video from YouTube
    Add the **Iframe** element to the interface:
    ```html
    <iframe src={{video}} width="560" height="315" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    ```

    1. In the **Data specification** section, you can configure the input and output data fields.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

    Learn more about the **Specification** parameters in [Input and output data](incoming.md).

    In this project:

    - Input data field: `video` — A link to a video.

    {% note warning %}

    If you use a video from **YouTube**, set the string data type for the `video` input field.

    {% endnote %}

    - Output data field: `result` — string for saving the Toloker's response.

    1. Click ![](../_images/tutorials/image-segmentation/preview-button.png) to see the Toloker's view of the task.

    {% note info %}

    The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

    {% endnote %}

    1. In the window that opens, check if the task options work correctly. In the lower-right corner, click **Submit**.

    1. To exit preview mode, click **Exit** in the lower-left corner.

    1. Save the changes.

1. 1. Write short and clear instructions. Describe what needs to be done and give examples in them.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

    1. Click **Finish**.

Learn more about working with the project in the [Project](project.md) section.

## Create a pool {#create-pool}

A pool is a set of paid tasks sent out for completion at the same time.

1. Open the page of the project that evaluates the video quality.

1. Click the {% if locale == "en-com" %}**Add a pool**{% endif %} button.

1. Specify the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. (optional) Enter a private description.

    1. Turn on the {% if locale == "en-com" %}**Add a private description**{% endif %} option.

    1. In the {% if locale == "en-com" %}**Private description**{% endif %} field, enter the pool description. This information is available only to you.

1. In the **Audience** block, add **Filters** to select Tolokers.

    - To make the task available only to Tolokers who speak Russian:

    1. Click {% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Add the {% if locale == "en-com" %}**Region by phone number**{% endif %} and {% if locale == "en-com" %}**Languages**{% endif %} filters and select Tolokers from Russia, Ukraine, Kazakhstan, and Belarus who indicated in their profiles that they know Russian.

    - Tasks in pools will be automatically available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

1. (optional) In the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} section, specify the desired quality level. Improving quality may reduce the speed of task completion because the pool will be available to fewer Tolokers. Learn more in the [Speed/quality balance](adjust.md) section.

1. In the **Price** block, set the price per task suite (for instance, $0.02).

    #### What is a task suite?

    A task suite can contain one or several tasks that are shown on the same page. If the tasks are simple, you can add 10-20 tasks per suite. Don't make task suites too long because it slows down loading speed for Tolokers.

    Tolokers get paid for completing the entire task suite.

    The number of tasks per suite is set when [uploading tasks](#tasks_upload).

    #### What is a fair price for a task suite?

    The general rule of pricing is the more time the Toloker spends to complete the task, the higher the price is.

    You can register in Toloka as a Toloker and find out how much other requesters pay for tasks.

1. [Quality control rules](control.md) allow you to filter out careless Tolokers. In the {% if locale == "en-com" %}**Quality control**{% endif %} block, add:

    - {% if locale == "en-com" %}**Control tasks**{% endif %} — filters out Tolokers who often make mistakes in the control tasks.

    1. Click {% if locale == "en-com" %}**Add Quality Control Rule**{% endif %}.

    1. Find the {% if locale == "en-com" %}**Rules**{% endif %} block in the list and choose {% if locale == "en-com" %}**Control tasks**{% endif %}.

    1. Set a rule for the control task: if the {% if locale == "en-com" %}**number of responses**{% endif %} to the control questions is **≥ 3** and {% if locale == "en-com" %}**correct responses (%)**{% endif %} to the control questions is **< 60**, then {% if locale == "en-com" %}**ban**{% endif %} the Toloker {% if locale == "en-com" %}**from the project**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. Specify **Control task** as a reason.

    This means that if a Toloker completed more than three control tasks and gave incorrect answers in more than 60% of them, they will be blocked and won't be able to complete tasks on this project for 10 days.

    - {% if locale == "en-com" %}**Fast responses**{% endif %} —Filters out Tolokers who respond too quickly.

    1. In the {% if locale == "en-com" %}**Recent values to use**{% endif %} field, enter the number of the Toloker's recently completed assignments. For example, `5`.
    1. In the {% if locale == "en-com" %}**Minimum time per task suite**{% endif %} field, enter the time in seconds. For example, `20`.
    1. Set a rule for a fast response: if the {% if locale == "en-com" %}**number of fast responses**{% endif %}** ≥ 1**, then {% if locale == "en-com" %}**ban**{% endif %} {% if locale == "en-com" %}**on requester**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. In the {% if locale == "en-com" %}**Reason**{% endif %} field, enter **Fast responses**.

    This means that a user who completes at least one assignment in less than 20 seconds won't be able to access your tasks for 10 days.

    - {% if locale == "en-com" %}**Majority vote**{% endif %} — a check based on matching responses from the majority of Tolokers.

    1. Set {% if locale == "en-com" %}**Accept as majority**{% endif %} to `2`.

    1. Set the rule: if {% if locale == "en-com" %}**number of responses**{% endif %} **≥ 5** and {% if locale == "en-com" %}**correct responses (%)**{% endif %} **< 50**, then {% if locale == "en-com" %}**ban**{% endif %} the Toloker {% if locale == "en-com" %}**on project**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. Specify the reason **Doesn't match the majority**.

    This means that if a Toloker completed more than ten tasks and most of their responses don't match the opinion of the majority of Tolokers, they won't be able to complete project tasks for 10 days.

    {% note info %}

    The rule takes effect when the number of responses for the task is equal to the overlap. To reach the required number of responses faster, enable the {% if locale == "en-com" %}**Keep task order**{% endif %} option in the [pool settings](#pool-parameters).

    {% endnote %}

    - {% if locale == "en-com" %}**Captcha**{% endif %} — prevents the task completion by robots.

    1. In the {% if locale == "en-com" %}**Recent values to use**{% endif %} field, enter the number of the Toloker's recently completed assignments. For example, `10`.
    1. Set a captcha rule: if the {% if locale == "en-com" %}**number of responses**{% endif %}** ≥ 5** and {% if locale == "en-com" %}**correct responses (%) **{% endif %}**< 65**, then {% if locale == "en-com" %}**ban**{% endif %} {% if locale == "en-com" %}**on project**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. In the {% if locale == "en-com" %}**Reason**{% endif %} field, enter **Captcha**.

    This means that if a Toloker enters captchas correctly in less than 65% of cases, they won't be able to access tasks in the project for 10 days.

    {% note info %}

    You can copy quality control settings from another pool. To do this, click {% if locale == "en-com" %}**Copy audience filters and quality control settings**{% endif %} in the {% if locale == "en-com" %}**Audience**{% endif %} section.

    {% endnote %}

1. Set overlap, which is the number of Tolokers to complete the same task. In the {% if locale == "en-com" %}**Overlap**{% endif %} section, specify the {% if locale == "en-com" %}**Overlap**{% endif %} field value. For tasks of this type it is usually `3-5`.

1. Set the {% if locale == "en-com" %}**Additional settings**{% endif %} for the pool:

    1. Specify the {% if locale == "en-com" %}**Time for completing a task suite in seconds**{% endif %} field value. There should be enough time to read the instructions, load the task, watch the video, and respond. For example, `1200` seconds.
    1. Turn on the {% if locale == "en-com" %}**Keep task order**{% endif %} option.

1. Click {% if locale == "en-com" %}**Save**{% endif %}.


## Upload tasks {#upload-file}
 {% if locale == "en-com" %}
Download the sample upload file. You can find it on the pool page. There are links to **files** with regular, control, and training tasks. Use it to prepare your own [file](../../glossary.md#tsv-file-definition-ru) with tasks.
{% endif %}
1. On the pool page, click {% if locale == "en-com" %}**Upload**{% endif %}. In the window that opens, you can also download a sample file.

1. In the window that opens, configure the file upload settings:

    1. Choose {% if locale == "en-com" %}**Smart mixing**{% endif %}.

    1. In the {% if locale == "en-com" %}**General tasks**{% endif %} field, specify `9`.

    1. In the {% if locale == "en-com" %}**Training tasks**{% endif %} field, specify `0`.

    1. In the {% if locale == "en-com" %}**Control tasks**{% endif %} field, specify `1`.

    1. Click {% if locale == "en-com" %}**Upload**{% endif %}.

    1. In the window that opens, choose the file with tasks to upload and click {% if locale == "en-com" %}**Open**{% endif %}.

    1. In the window that opens, check the number of tasks and click {% if locale == "en-com" %}**Add**{% endif %}.

1. Create a [control task](goldenset.md).

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.

    {% note info %}

    If you selected something else instead of **smart mixing**, click **Edit**. If this button is missing, delete the file and upload it again.

    {% endnote %}

    1. In the window that opens, click {% if locale == "en-com" %}**Create control tasks**{% endif %}.

    1. In the window that opens, in the {% if locale == "en-com" %}**Create control task**{% endif %} section, mark the **result** item on the left.

    1. Choose the correct answer to the question.

    1. Click {% if locale == "en-com" %}**Save and go to next**{% endif %}.

    1. Click **Rate the video quality** to exit task markup mode.

    {% note info %}

    In small pools, control tasks should be 10% of all tasks. Include different versions of correct responses in equal amounts. View the distribution of responses on the {% if locale == "en-com" %}**Edit tasks**{% endif %} page, {% if locale == "en-com" %}**Control tasks**{% endif %} tab.

    {% endnote %}

1. Click ![](../_images/other/b-start-pool.png) to start the pool.


## Get the results {#get-results}

1. Next to the {% if locale == "en-com" %}**Download results**{% endif %} button, click ![](../_images/other/drop-down.png).

1. Choose {% if locale == "en-com" %}**Dawid-Skene aggregation model**{% endif %} from the list. Learn more about [Result aggregation based on the Dawid-Skene model](result-aggregation.md#dawid-skene).

1. In the window that opens, click {% if locale == "en-com" %}**Yes**{% endif %}.

1. At the top of the page, click {% if locale == "en-com" %}**View the list of operations**{% endif %}.

1. When the operation is complete, download the file with the results. To do this, click {% if locale == "en-com" %}**Download**{% endif %} in the {% if locale == "en-com" %}**Files**{% endif %} column.


{% note info %}

To avoid unwanted errors, we recommend that you first run your project in the [Sandbox]({{ sandbox }}).

{% endnote %}



## Troubleshooting {#troubleshooting}

{% include [contact-support](../_includes/contact-support-help.md) %}
