# Questions about presets

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Selecting a preset {#concept_tfh_pgd_rmb}

{% cut "How do I classify texts according to their meanings?" %}

You can structure your text classification task using the source text and radio buttons. It can also be text and checkboxes if you use multiple subjects.

We recommend that you base it on the **Sentiment analysis & content moderation** preset.

You can also create your own interface. All the available tools are described in the [Requester's guide](../concepts/spec.md).

{% endcut %}

{% cut "How do I create a task using both input and output text fields?" %}

You can see how it's implemented in the [Transcribing audio recordings](../tutorials/transcript-audio.md) preset where a string-type output field is used. In the **Text recognition from an image (OCR)** preset, you can view how to describe text input fields. Please note that if you later want to use the Dawid-Skene aggregation method, you must specify allowed values.

{% endcut %}

{% cut "What preset do I select so that Tolokers label only irrelevant products in the output?" %}

You can create such an assignment based on the classification preset. Show a product image and ask the question: "Does the product match the query?" Add two radio buttons for responses: “Yes” and “No”.

{% endcut %}

{% cut "How do I label elements on web pages?" %}

Generate the screenshots of pages and manually label areas using the “Object selection in an image” preset.

{% endcut %}

{% cut "I have a complex task. How do I break it down to get high-quality results?" %}

If your task contains many objects of different types, you should break it down. For example, you can ask users to select numbers in the first project, doorways and windows in the second project, walls in the third project, and plumbing in the fourth project.

The simpler the task, the cheaper it is and the better the quality of the final result. Set the cost of labeling a single class of objects in photos at about $0.01.

[Use](../tutorials/selection.md) the **Object selection in an image** preset. You can open this preset in the editor and add a drop-down list for labeling the selected object. See how to do this in the editor [description](../concepts/t-components/image-annotation.md#annotation) (**Dropdown list** tab).

{% endcut %}

{% cut "How do I add response validation depending on a checkbox?" %}

You can use JavaScript to add assignment validation depending on a checkbox. An example is provided in the “Search for information online” preset.

{% endcut %}

[Other questions](support.md#help)

## Area selection {#concept_bdk_qgd_rmb}

{% cut "How do I create a shortcut for adding a polygon in "image-annotation"?" %}

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

{% cut "How do I mark up triangles so that they close automatically when the third point is selected?" %}

Use the **C** shortcut for closing areas.

You can also use the [library](https://github.com/vmit/image-annotation) to customize the keyboard shortcuts for your tasks.

{% endcut %}

{% cut "How do I create a task for selecting objects in images?" %}

We recommend that you break down your object selection project into three projects in Toloka:

1. Sorting images containing an object.

    1. [Create a task](../tutorials/image-classification.md) using the “Image classification” preset.

    1. Sort the images containing the object you are looking for.

    1. Show the image to the Toloker and ask if the object is in the image. Response options: Yes/No.

1. Selecting objects in images.

    1. Select the object in the images you obtained after the previous project. You already have such a project. Run the task with non-automatic acceptance.

    1. Use the quality control rules: fast responses, non-automatic acceptance, and post-review re-assessment. [Description of rules with examples](../concepts/control.md).

1. Reviewing object selection assignments.

    1. Create a task using the object selection template.

    1. Hide the editor and ask whether the object is selected correctly. Response options: Yes/No.

    1. In the input data, pass the images and coordinates of the labeled objects from the previous task.

    Now you can run the resulting pool with an overlap of 3–5 or with dynamic overlap. After that, you can aggregate the results and then upload the data for review to Project 2.

    To prevent the Tolokers who worked on the second project from doing the review, assign a skill to them. Use this skill as a filter in the pools of the third project.

{% endcut %}

{% cut "How do I add assignment validation depending on a checkbox?" %}

You can use JavaScript to add assignment validation depending on a checkbox. An example is provided in the “Search for information online” preset.

{% endcut %}

{% cut "How much would 2000 images with a large number of different types of selectable objects cost? How do I create a task for this amount of work?" %}

In the case of crowdsourcing, it's better to break down this task. The simpler the task, the cheaper it is and the better the quality of the final result. The cost of labeling a single class of objects in photos might be about $0.01.

​Base your task on the “Object selection in an image” preset. See the step-by-step guide for creating this type of project on [this page](../tutorials/selection.md).

The editor used in the preset lets you add a drop-down list for labeling the selected object. See how to do this in the editor description ([Dropdown list](../concepts/t-components/image-annotation.md) tab).

{% endcut %}

{% cut "How do I implement selection of 3 different areas in an image? Select the name, image, and price in the product page screenshot." %}

You can create a selection + drop-down list with category selection. See how to do this in the editor description ([Dropdown list](../concepts/t-components/image-annotation.md) tab).

{% endcut %}

{% cut "What are the input data in the case of object labeling in an image: the coordinates of the object relative to the image, or the coordinates of the object in the Toloka user window?" %}

The coordinates are relative to the image.

{% endcut %}

{% cut "How do I use control and training tasks in the standard preset with an area selection editor?" %}

In the standard preset with an area selection editor, you can't use the control tasks. In order for the assignment to be accepted by the system as correct, the object selected by the Toloker must exactly match the control object. This is almost impossible. Therefore, you can leave the `GOLDEN` field empty in the task file or simply delete all the columns except `INPUT`.

You can't use [training](../../glossary.md#training-pool) and the main pool with the **Training** type in an area selection project because for the response to be correct, the object selected by the Toloker must exactly match the control object. This is almost impossible.

Such tasks are usually run with non-automatic acceptance: the Toloker submits an assignment, and then the assignment is rejected or accepted after the review.

For pre-selection of users, you can use “examination tasks”. Review the assignments and assign skills based on the percentage of accepted assignments. For this purpose, add the “Results of assignment review” rule to the pool. To make sure that only the good Tolokers are admitted to the main pool, put a skill-based filter to the pool.

{% endcut %}

[Other questions](support.md#help)

## Field task {#concept_k1m_rgd_rmb}

{% cut "Can I limit the source of the photo to camera-only in a field task so that the Toloker can't upload a photo from anywhere else?" %}

To open the camera instead of the gallery when the Toloker taps the image upload button, in the **Image upload button **component specify `camera=true`.

In the mobile apps, Tolokers can add photos from the default gallery (iOS) or Google photo (Android). To limit the capacity of adding online images, specify in the component `requiredCoordinates=true`. In this case, the system won't let the Toloker add images without geotags.

[Learn more about setting up the image upload component](../concepts/t-components/upload-picture.md).

{% endcut %}

[Other questions](support.md#help)

## Side-by-side image comparison {#side-by-side}

{% cut "How do I create a task with a selection out of three image options with the paired image comparison?" %}

1. Use the “Side-by-side image comparison” preset.

1. In the file, specify the links to the compared images.

1. In the file, create the tasks where all the images will be compared in pairs:

    - Image 1 and Image 2

    - Image 1 and Image 3

    - Image 2 and Image 3

1. Process the results.

You can also edit the project so that the Toloker sees 3 images at once and selects one of them.

{% endcut %}

[Other questions](support.md#help)

## Survey {#interview}

{% cut "How do I create a simple survey with no options, where the Toloker answers an open-ended question?" %}

1. Create a project from an empty preset.

1. Write your question in the HTML block.

1. If you need an [extensive](../concepts/t-components/text.md) response, add the required number of text entry components.

1. If you need a [short](../concepts/t-components/string.md) response, add the required number of string entry components.

1. Come up with a name for each of the components and create a matching number of string-type output fields with the same names. They will be used to save responses.

1. Make all the output fields mandatory.

1. Make the input field auxiliary. It will only be used to create a file with tasks.

1. Come up with a name for the input field and set the string type for it (see the step-by-step [guide on creating a survey](../tutorials/questionnaire-toloka.md)).

{% endcut %}

{% cut "How do I create a survey with a single question based on the survey preset?" %}

The survey includes an auxiliary input field. You can use it to pass any information, and it won't be visible to Tolokers.

Upload one task and use the overlap parameter to enter the number of people you want to survey.

{% endcut %}

[Other questions](support.md#help)

{% include [contact-support](../_includes/contact-support-help.md) %}