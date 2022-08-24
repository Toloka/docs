# Voice recording

{% note info %}

Run the project in the [Sandbox]({{ sandbox }}) first. This helps you avoid making mistakes and spending money on a task that isn't working right.

{% endnote %}


Voice recording tasks are most convenient to open in the mobile app for [Android]({{ android-app }}) or [iOS]({{ ios-app }}). Mobile apps can record audio directly in a task using the device's built-in voice recorder.

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](solution-architecture.md).

Let's say you need to collect audio recordings in which users read your text outloud. To do this, create a task in which the Toloker is given a text phrase and should attach an audio recording as a response.

To run tasks and get responses:

1. [Create a project](#project)
1. [Add a task pool](#pool)
1. [Upload tasks](#tasks_upload)
1. [Start the pool and get the results](#launch)

## Create a project {#project}

The project defines what the task will look like for a Toloker.

#### In the interface:

1. Choose a template:

    1. Click {% if locale == "en-com" %}**Create project**{% endif %}.

    1. Select the {% if locale == "en-com" %}**Voice recording**{% endif %} template.

1. Provide general information:

    1. Enter a clear name and a short description for the project. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

    1. Click **Save**.

1. Edit the task interface in the editor you selected:

    #### Template Builder

    1. The task interface describes how the elements should be arranged in the task.

    Use the {% if locale == "en-com" %}[ready-made code](https://clck.ru/VC42P){% endif %} for this project with pre-configured validation and task layout. The Toloker won't be able to submit the response until they upload the audio recording.

    Learn more about [setting up conditions]({{ tb-conditions }}) in the Template Builder Help.

    1. To specify what data you will pass to the Toloker and receive in response, create input and output data fields.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

    Input data fields are created from the code on the **Example of input data** tab.

    The output data fields depend on the components that use `data.output` and values supported by it.

    Click **Show specifications** to see the input and output data fields.

    Learn more about [input and output data fields]({{ tb-create-specs }}) in the Template Builder Help.

    In this project:

    - Input data field: `text` — The text to be voiced by the Toloker.

    - Output data field: `audio_record` — An audio recording that the Toloker should upload.

    #### HTML/CSS/JS editor

    1. The task interface describes how the elements should be arranged in the task.

    In the HTML interface, use the standard HTML tags and [special expressions](t-components.md) in double curly brackets for input and output data fields.

    For this project, leave the **HTML**, **JS**, and **CSS** blocks unchanged.

    1. In the **Data specification** section, you can set the input and output data parameters.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

    Learn more about the **Specification** parameters in [Input and output data](incoming.md).

    In this project:

    - Input data field: `text` — The text to be voiced by the Toloker.

    - Output data field: `audio_record` — An audio recording that the Toloker should upload.

    1. Click ![](../_images/tutorials/image-segmentation/preview-button.png) to see the Toloker's view of the task.

    {% note info %}

    The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

    {% endnote %}

    1. To exit preview mode, click **Exit** in the lower-left corner.

1. Save the changes.

1. 1. Write short and clear instructions. Describe what needs to be done and give examples in them.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

    1. Click **Finish**.

Learn more about working with the project in the [Project](project.md) section.

## Add a task pool {#pool}

A pool is a set of paid tasks sent out for completion at the same time.

1. Open the project and click **Add pool**.
1. Give the pool any convenient name and description. The pool info is only available to you. Tolokers can view only the project name and description.
1. In the **Audience** block, add {% if locale == "en-com" %}**Filters**{% endif %} to select Tolokers.

    Tasks in pools will be automatically available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

1. If there is no adult content in the task in any form, turn off {% if locale == "en-com" %}**Adult content**{% endif %}.
1. In the **Price** block, set the price per task suite (for instance, $0.02).
    #### What is a task suite?

    A task suite can contain one or several tasks that are shown on the same page. If the tasks are simple, you can add 10-20 tasks per suite. Don't make task suites too long because it slows down loading speed for Tolokers.

    Tolokers get paid for completing the entire task suite.

    The number of tasks per suite is set when [uploading tasks](#smart-mixing).

    #### What is a fair price for a task suite?

    The general rule of pricing is the more time the Toloker spends to complete the task, the higher the price is.

    You can register in Toloka as a Toloker and find out how much other requesters pay for tasks.

1. In the **Quality control** block, set the {% if locale == "en-com" %}**Overlap**{% endif %}, which is the number of Tolokers to complete the same task. The value depends on how many recordings of the same phrase you want to collect. If one is enough, put 1.
1. Enable the {% if locale == "en-com" %}**Non-automatic acceptance**{% endif %} option and enter the number of days for checking in the {% if locale == "en-com" %}**Review period**{% endif %} field (for example, 7).
1. In the **Additional settings** block, specify the {% if locale == "en-com" %}**Time**{% endif %} allowed for completing a task suite. It should be long enough to read the instructions and wait for task data to download. (for example, 1200 seconds).
1. Save the pool.

## Upload tasks {#tasks_upload}
 {% if locale == "en-com" %}
Download the sample upload file. You can find it on the pool page. There are links to **files** with regular, control, and training tasks. Use it to prepare your own [file](../../glossary.md#tsv-file-definition-ru) with tasks.
{% endif %}
1. Click **Upload**. In the window that opens, you can also download a sample file.
1. Add input data in it. The header of the input data column contains the word `INPUT`. Put the text to read outloud in the `INPUT:phrase` column and remove the other columns.
1. Load the tasks. Choose {% if locale == "en-com" %}**Set manually**{% endif %} and set the number of tasks per suite (for example, 5). This means that there are 5 phrases per page and the Toloker has to attach 5 audio files.

## Start the pool and get the results {#launch}

1. Start the pool by clicking ![](../_images/other/b-start-pool.png).
1. Track the completion in the {% if locale == "en-com" %}**Pool statistics**{% endif %} block.
1. Start the review as soon as you get the first results. After the specified time period, all responses are automatically accepted, regardless of their quality.

    To check the tasks and download the attached files, open the pool and click {% if locale == "en-com" %}**Download results**{% endif %}, and then **Download attachments**.
    {% note info %}

    The files received from the Toloka app are in WAV 16KHz 16bit PCM format.

    {% endnote %}


## Troubleshooting {#troubleshooting}

#### How do I make a single voice-recorded file for my text by involving 1000 people for this purpose?

You need to break down your task for Toloka. If you have a 30-minute task intended for one person and containing all the phrases, the best approach is to divide it into individual phrases, which you can give to different Tolokers. The template for voice recording tasks doesn't require that the Toloker installs a separate voice recorder app.

Refer to our step-by-step guide for creating a [voice recording task](record-audio.md).

In the input data, you can pass the phrase for the Toloker to record ("enable navigation"), and the speech speed (normal speed). This is the data you need to save in the file. See the [Guide](pool_csv.md) to learn about creating a file and its structure.

The preview contains 4 tasks per suite by default. You can specify the number of tasks for your project when you upload the task file. [Learn more about the preview](spec.md).

For example, if you want one person to say the same phrase 10 times, create 10 tasks in a suite. The cost is specified per task suite. To define how many people should say a particular phrase, use the overlap in the pool. By the way, don't forget to set up filters in your pool. This way you can select only the Tolokers who speak a certain language and use mobile devices: client = mobile Toloka.

You can delegate review of the voice recordings to other Tolokers by creating a separate project. Find brief instructions on how to do this [here](record-audio.md).

#### How do I show two different versions of the text to Tolokers?

If you pass texts to the input data, you can upload 2 different tasks to the pool: pass Text 1 in the `INPUT: <input field name>` field of Task 1. In Task 2, use this field to pass Text 2.

If the text is in the HTML block of the task template, then clone the project. To limit a Toloker to doing only one task in your project, use the [Submitted responses](submitted-answers.md) rule. You can assign a skill or ban the Toloker after they submit one response.

#### My Tolokers can't upload a file with the assignment

If none of the Tolokers can submit the assignment, the most likely reason is JS validation. Run JS validation again.

Export your project to the sandbox and try to complete the task in the sandbox yourself.

#### How do I make an image expand to its maximum size on click?

To the component that inserts the image, add the parameters: `real-size=true` and `screenshot=true`.


{% include [contact-support](../_includes/contact-support-help.md) %}
