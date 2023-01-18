# Create a project

If you already have a project and you want to create an identical one, [clone](#clone) the existing project. If not, create a new project.

## New project {#new-project}

The project defines what the task will look like for a Toloker.

To get better results, make tasks as simple as possible and divide complex tasks into several projects.

{% note info %}

You can first create and test your project for free in the [sandbox](sandbox.md) and then [move](sandbox.md#export) it to the Toloka production version.

{% endnote %}

To create a project, follow the instructions:

#### In the interface:

1. Choose a preset:

    1. Click the {% if locale == "en-com" %}**Create project**{% endif %} button on the {% if locale == "en-com" %}**Projects**{% endif %} page.

    1. Choose a preset. The preset contains pre-configured [input and output data fields](incoming.md) and [the task interface](spec.md), which you can edit.

        If there is no suitable preset, choose an empty preset.

        {% note tip %}

        If you unsure which preset to choose, you can ask Toloka experts to create a project for you. To do that,

        - click **Get expert help**,
        - select the way Toloka can contact you (WhatsApp, Telegram, Viber, email, or phone),
        - enter your phone number or email address,
        - briefly describe the project and the results you want to get.

        Toloka engineering team will contact you for more details and explain your further steps.

        {% endnote %}

1. Provide general information:

    1. Enter the **Name** and **Description**. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

1. Edit the task interface:

    {% list tabs %}

    - Template Builder

      1. [Create the task interface](../../template-builder/index.md).

      1. Click **Show specifications** to see the input and output data fields.

          Input data fields are created from the code on the **Example of input data** tab.

          The output data fields depend on the components that use `data.output` and values supported by it.

          Learn more about [input and output data fields](../../template-builder/operations/create-specs.md) in the Template Builder Help.

      1. Specify the settings for field task display if you use one of the field task templates.

    - HTML/JS/CSS editor

      1. [Describe the task interface](spec.md).

      1. Add fields for [input and output data](incoming.md) in the **Data specification** block.

      1. Specify the settings for field task display if you use one of the field task templates.

    {% endlist %}

1. [Write {% if locale == "en-com" %}guidelines{% endif %}](instruction.md) for Tolokers.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

1. Optionally, add translations to other languages.

    1. Select the source language and the target languages.

    1. Fill in the fields in the table.

    1. Click **Finish**.

After creating the project, add a [task pool](pool-main.md) to it. You can also set up [quality control](control.md) in the project.

{% include [project-moderation](../_includes/toloka-requester-source/id-toloka-requester-source/project-moderation.md) %}

## Cloning a project {#clone}

You can view the list of created projects on the **Projects** page. Open the project page to view the list of pools, [project rating](project_rating_stat.md), and [project statistics](project-statistic.md).

To clone a project, click ![](../_images/location-job/project/clone-project.svg) in the list of projects or select {% if locale == "en-com" %}**Project actions → Clone**{% endif %} on the project page.

{% note warning %}

Quality control in the project is not cloned.

{% endnote %}

If you need to change the project settings, [open edit mode](edit-project.md).

## What's next {#what_next}

- [Create a task pool](pool-main.md) in the project.
- Learn more about how to set up a project:

    - [Writing instructions](instruction.md).
    - [Input and output data](incoming.md).
    - [Task interface](spec.md).
    - [Adapt a task for mobile devices](mobile.md).
    - [Setting up quality control](project-qa.md).

## See also {#see-also}

- [Efficiency indicators: Quality of interface](./efficiency-metrics/interface-quality.md)

## For developers {#for-developers}

- [Toloka API: Creating project](../../api/concepts/create-prj.md)
- [Toloka-Kit: Creating project](../../toloka-kit/reference/toloka.client.TolokaClient.create_project.md)

## Troubleshooting {#troubleshooting}

{% cut "General task settings" %}

{% cut "I have a complex task. How do I break it down to get high-quality results?" %}

If your task contains many objects of different types, you should break it down. For example, you can ask users to select numbers in the first project, doorways and windows in the second project, walls in the third project, and plumbing in the fourth project.

The simpler the task, the cheaper it is and the better the quality of the final result. Set the cost of labeling a single class of objects in photos at about $0.01.

[Use](../tutorials/selection.md) the **Object selection in an image** preset. You can open this preset in the editor and add a drop-down list for labeling the selected object. See how to do this in the editor [description](t-components/image-annotation.md#annotation) (**Dropdown list** tab).

{% endcut %}

{% cut "How do I add response validation depending on a checkbox?" %}

You can use JavaScript to add assignment validation depending on a checkbox. An example is provided in the “Search for information online” preset.

{% endcut %}

{% cut "How many tasks should be in a suite?" %}

The number of tasks depends on how difficult and time-consuming the tasks are. Keep the size reasonably small. Large task suites are unpopular, partly because they are inconvenient for Tolokers (for example, if the internet connection is unstable).

{% endcut %}

{% endcut %}

{% cut "Setting up tasks with images" %}

{% cut "What preset do I select so that Tolokers label only irrelevant products in the output?" %}

You can create such an assignment based on the classification preset. Show a product image and ask the question: "Does the product match the query?" Add two radio buttons for responses: “Yes” and “No”.

{% endcut %}

{% cut "How do I label elements on web pages?" %}

Generate the screenshots of pages and manually label areas using the "Object selection in an image" preset.

{% endcut %}

{% cut "How do I create a task for selecting objects in images?" %}

We recommend that you break down your object selection project into three projects in Toloka:

1. Sorting images containing an object.

    1. [Create a task](../tutorials/image-classification.md) using the “Image classification” preset.

    1. Sort the images containing the object you are looking for.

    1. Show the image to the Toloker and ask if the object is in the image. Response options: Yes/No.

1. Selecting objects in images.

    1. Select the object in the images you obtained after the previous project. You already have such a project. Run the task with non-automatic acceptance.

    1. Use the quality control rules: fast responses, non-automatic acceptance, and post-review re-assessment. [Description of rules with examples](control.md).

1. Reviewing object selection assignments.

    1. Create a task using the object selection preset.

    1. Hide the editor and ask whether the object is selected correctly. Response options: Yes/No.

    1. In the input data, pass the images and coordinates of the labeled objects from the previous task.

       Now you can run the resulting pool with an overlap of 3–5 or with dynamic overlap. After that, you can aggregate the results and then upload the data for review to Project 2.

       To prevent the Tolokers who worked on the second project from doing the review, assign a skill to them. Use this skill as a filter in the pools of the third project.

{% endcut %}

{% cut "I have a task for area selection in an image. What should the Toloker do if there is no selectable object in the image?" %}

Main options:

- Select an arbitrary area in the image (for example, put a square in the upper-right corner). In this case, the project instructions for reviewers should also reflect this.

- Ask the Toloker to skip the task and report it in a personal message. Messages are reviewed by the requester. If the object is truly missing, the task is deleted from the pool by resetting the overlap.

- Add an additional “No object” checkbox to the interface. Make sure that your JS checks that either the object is selected or the checkbox is enabled. In this case, add information about the checkbox value in the review task interface.

{% endcut %}

{% cut "How do I implement selection of 3 different areas in an image? Select the name, image, and price in the product page screenshot." %}

You can create a selection + drop-down list with category selection. See how to do this in the editor description ([Dropdown list](t-components/image-annotation.md) tab).

{% endcut %}

{% cut "What are the input data in the case of object labeling in an image: the coordinates of the object relative to the image, or the coordinates of the object in the Toloka user window?" %}

The coordinates are relative to the image.

{% endcut %}

{% cut "How do I mark up triangles so that they close automatically when the third point is selected?" %}

Use the **C** shortcut for closing areas.

You can also use the [library](https://github.com/vmit/image-annotation) to customize the keyboard shortcuts for your tasks.

{% endcut %}

{% cut "How do I create a shortcut for adding a polygon in ’image-annotation’?" %}

To create a shortcut, add the following action to the "onKey" method:

```javascript
onKey: function(key) {
    var el = this.getDOMElement().querySelector(".image-annotation-editor__shape-polygon");

    if (key === 'D') {
      el.click();
      el.classList.add('image-annotation-editor__shape_active')
    }
```

{% endcut %}

{% cut "How much would 2000 images with a large number of different types of selectable objects cost? How do I create a task for this amount of work?" %}

In the case of crowdsourcing, it's better to break down this task. The simpler the task, the cheaper it is and the better the quality of the final result. The cost of labeling a single class of objects in photos might be about $0.01.

​Base your task on the “Object selection in an image” preset. See the step-by-step guide for creating this type of project on [this page](../tutorials/selection.md).

The editor used in the preset lets you add a drop-down list for labeling the selected object. See how to do this in the editor description ([Dropdown list](t-components/image-annotation.md) tab).

{% endcut %}

{% cut "How do I use control and training tasks in the standard preset with an area selection editor?" %}

In the standard preset with an area selection editor, you can't use the control tasks, because in order for the assignment to be accepted by the system as correct, the object selected by the Toloker must exactly match the control object. This is almost impossible. Therefore, you can leave the GOLDEN field empty in the task file or simply delete all the columns except INPUT.

You can't use [training](../../glossary.md#training-pool) and the main pool with the **Training** type in an area selection project because for the response to be correct, the object selected by the Toloker must exactly match the control object. This is almost impossible.

Such tasks are usually run with non-automatic acceptance: the Toloker submits an assignment, and then the assignment is rejected or accepted after the review.

For pre-selection of users, you can use “examination tasks”. Review the assignments and assign skills based on the percentage of accepted assignments. For this purpose, add the “Results of assignment review” rule to the pool. To make sure that only the good Tolokers are admitted to the main pool, put a skill-based filter to the pool.

{% endcut %}

{% cut "How do I create a task with a selection out of three image options with the paired image comparison?" %}

1. Use the **Image comparison (Side-by-side)** preset.

1. In the TSV file, specify the links to the compared images.

1. In the file, create the tasks where all the images will be compared in pairs:

    - Image 1 and Image 2

    - Image 1 and Image 3

    - Image 2 and Image 3

1. Process the results.

You can also edit the project so that the Toloker sees 3 images at once and selects one of them.

{% endcut %}

{% endcut %}

{% cut "Setting up tasks with texts" %}

{% cut "How do I classify texts according to their meanings?" %}

You can structure your text classification task using the source text and radio buttons. It can also be text and checkboxes if you use multiple subjects.

We recommend that you base it on the "Text classification" preset.

You can also create your own interface. All the available tools are described in the [documentation](spec.md).

{% endcut %}

{% cut "How do I create a task using both input and output text fields?" %}

You can see how it's implemented in the “[Transcript of audio recordings](../tutorials/transcript-audio.md)” preset where a string-type output field is used. In the “Text recognition from an image” preset, you can view how to describe text input fields. Please note that if you later want to use the Dawid-Skene aggregation method, you must specify allowed values.

{% endcut %}

{% cut "How do I create a simple survey with no options, where the Toloker answers an open-ended question?" %}

1. Create a project from an empty preset.

1. Write your question in the HTML block.

1. If you need an [extensive](t-components/text.md) response, add the required number of text entry components.

1. If you need a [short](t-components/string.md) response, add the required number of string entry components.

1. Come up with a name for each of the components and create a matching number of string-type output fields with the same names. They will be used to save responses.

1. Make all the output fields mandatory.

1. Make the input field auxiliary. It will only be used to create a file with tasks.

1. Come up with a name for the input field and set the string type for it (see the step-by-step [guide on creating a survey](../tutorials/questionnaire-toloka.md)).

{% endcut %}

{% cut "How do I create a survey with a single question based on the survey preset?" %}

The survey includes an auxiliary input field. You can use it to pass any information, and it won't be visible to Tolokers.

Upload one task and use the overlap parameter to enter the number of people you want to survey.

{% endcut %}

{% endcut %}

{% cut "Can I limit the source of the photo to camera-only in a field task so that the Toloker can't upload a photo from anywhere else?" %}

To open the camera instead of the gallery when the Toloker taps the image upload button, in the **Image upload button** component specify `camera=true`.

In the mobile apps, Tolokers can add photos from the default gallery (iOS) or Google photo (Android). To limit the capacity of adding online images, specify in the component `requiredCoordinates=true`. In this case, the system won't let the Toloker add images without geotags.

[Learn more about setting up the image upload component](t-components/upload-picture.md).

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}