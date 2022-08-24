# Tutorials for popular tasks

The tutorials will show you how to post tasks in Toloka. Choose the tutorial that is most similar to your task.

## Before you start {#section_ndt_5b3_smb}

Make sure you're [registered](access.md) as a requester. We recommend that you go through tutorials in the [sandbox](sandbox.md).

## List of examples {#section_qmm_vwz_mlb}

#### By task type

- **Images**
    - [Object classification](../tutorials/image-classification.md) — A multiple choice task. Examples are moderating content or grouping images by category.
    - [Side-by-side image comparison](../tutorials/side-by-side.md) — The Toloker compares pairs of images, illustrations, or interfaces.
    - [Object recognition and area selection](../tutorials/selection.md) — The Toloker labels the areas on an image that contain the specified object. These tasks are easier to run in the web version.
    - [Object recognition and area selection (example with decomposition)](image-segmentation-overview.md) — An example of dividing a task for selecting objects into three projects: filtering out inappropriate images, selecting objects, and reviewing assignments.

- **Video**
    - [Video classification](video-moderation.md) — A multiple choice task. For example, moderation of content, evaluation of video for noise and defects, or video classification by specified categories.

- **Audio**
    - [Audio transcription](../tutorials/transcript-audio.md) — The Toloker receives an audio recording and types the text they hear. Checking such tasks can be assigned to other Tolokers as a classification task.
    - [Voice recording](record-audio.md) — The Toloker receives a phrase or text fragment to record and has to attach the audio file as the response. These tasks are easier to run in the mobile app for [Android]({{ android-app }}) and [iOS]({{ ios-app }}).

- **Texts**
    - [Sentiment analysis and content moderation](content-moderation.md) — The Toloker checks the text for compliance with the rules.

- **Data enrichment**
    - [Survey](questionnaire.md) — Set requirements for respondents and take a poll.
    - [Business information](internet-search.md) — A task in which Tolokers search for data about businesses online.
    - [Business information (example with decomposition)](data-collection.md) — Type of task for searching and processing relevant data. For example, find similar shoes in an online store or determine which of the found objects is more similar to the original one.

- **Field tasks**
    Field tasks are completed in the Toloka mobile app for [Android]({{ android-app }}) and [iOS]({{ ios-app }}).

    - [Collect offline data](walk.md) — The Toloker goes to a specified point on the map, checks something, and takes photos.
    - [Monitor prices](price-tag.md) — The Toloker goes to the location and takes photos of the store's front, a particular product on the shelf, and the price tag.
    - [Monitor products](audit-of-planogram-of-product-placement-in-store.md) — The Toloker goes to the store, takes a photo of the front, finds the relevant section inside, and takes a photo of the rack with a certain brand of products.
    - [Collect data on businesses](monitoring-objects-in-organizations.md) — The Toloker goes to the point, takes a picture of the outside of the organization, and photographs a particular object inside from different angles.
    - [Monitor outdoor objects of interest](monitoring.md) — The Toloker goes to the point, finds an object on the street, photographs it from different angles, and takes a picture of the address sign.


#### By complexity

- **Level 1. Tutorials using a single project** are suitable for beginners. Go through **at least one** tutorial that is most similar to your task.
    - [Object classification](../tutorials/image-classification.md) — A multiple choice task. Examples are moderating content or grouping images by category.
    - [Side-by-side image comparison](../tutorials/side-by-side.md) — The Toloker compares pairs of images, illustrations, or interfaces.
    - [Object recognition and area selection](../tutorials/selection.md) — The Toloker labels the areas on an image that contain the specified object. These tasks are easier to run in the web version.
    - [Audio transcription](../tutorials/transcript-audio.md) — The Toloker receives an audio recording and types the text they hear. Checking such tasks can be assigned to other Tolokers as a classification task.
    - [Voice recording](record-audio.md) — The Toloker receives a phrase or text fragment to record and has to attach the audio file as the response. These tasks are easier to run in the mobile app for [Android]({{ android-app }}) and [iOS]({{ ios-app }}).
    - [Video classification](video-moderation.md) — A multiple choice task. For example, moderation of content, evaluation of video for noise and defects, or video classification by specified categories.
    - [Sentiment analysis and content moderation](content-moderation.md) — The Toloker checks the text for compliance with the rules.
    - [Survey](questionnaire.md) — Set requirements for respondents and take a poll.
    - [Business information](internet-search.md) — A task in which Tolokers search for data about businesses online.

- **Level 2. Field tutorials** — If you need to post field tasks, go through a tutorial at this level. If not, you can skip it.
    Field tasks are completed in the Toloka mobile app for [Android]({{ android-app }}) and [iOS]({{ ios-app }}).

    - [Collect offline data](walk.md) — The Toloker goes to a specified point on the map, checks something, and takes photos.
    - [Monitor prices](price-tag.md) — The Toloker goes to the location and takes photos of the store's front, a particular product on the shelf, and the price tag.
    - [Monitor products](audit-of-planogram-of-product-placement-in-store.md) — The Toloker goes to the store, takes a photo of the front, finds the relevant section inside, and takes a photo of the rack with a certain brand of products.
    - [Collect data on businesses](monitoring-objects-in-organizations.md) — The Toloker goes to the point, takes a picture of the outside of the organization, and photographs a particular object inside from different angles.
    - [Monitor outdoor objects of interest](monitoring.md) — The Toloker goes to the point, finds an object on the street, photographs it from different angles, and takes a picture of the address sign.

- **Level 3. Tutorials using several projects** — Learn how to decompose a task.
    - [Object recognition and area selection (example with decomposition)](image-segmentation-overview.md) — An example of dividing a task for selecting objects into three projects: filtering out inappropriate images, selecting objects, and reviewing assignments.
    - [Business information (example with decomposition)](data-collection.md) — Type of task for searching and processing relevant data. For example, find similar shoes in an online store or determine which of the found objects is more similar to the original one.

If you didn't find a suitable example, use general [instructions](main-steps.md) for launching and setting up projects.

You can [contact us or our partners](get-help.md) if you need help with your project overall or with individual steps like [editing tasks](../../glossary.md#task-markup-ru).

Learn more about how to [set up pricing](dynamic-pricing.md#section_wb1_lhl_vlb).


## Troubleshooting {#troubleshooting}

#### Setting up tasks with images

#### What template do I select so that Tolokers label only irrelevant products in the output?

You can create such an assignment based on the classification template. Show a product image and ask the question: "Does the product match the query?" Add two radio buttons for responses: <q>Yes</q> and <q>No</q>.

#### How do I label elements on web pages?
Generate the screenshots of pages and manually mark up areas using the <q>Object selection in an image</q> template.

#### How do I create a shortcut for adding a polygon in "image-annotation"?
To create a shortcut, add the following action to the "onKey" method:
```
onKey: function(key) {
    var el = this.getDOMElement().querySelector(".image-annotation-editor__shape-polygon");

    if (key === 'D') {
      el.click();
      el.classList.add('image-annotation-editor__shape_active')
    }
```

#### How do I mark up triangles so that they close automatically when the third point is selected?

Use the **C** shortcut for closing areas.

You can also use the [library](https://github.com/vmit/image-annotation) to customize the keyboard shortcuts for your tasks.

#### How do I create a task for selecting objects in images?

We recommend that you break down your object selection project into three projects in Toloka:
1. Sorting images containing an object.
    1. [Create a task](../tutorials/image-classification.md) using the <q>Image classification</q> template.
    1. Sort the images containing the object you are looking for.
    1. Show the image to the Toloker and ask if the object is in the image. Response options: Yes/No.

1. Selecting objects in images.
    1. Select the object in the images you obtained after the previous project. You already have such a project. Run the task with non-automatic acceptance.
    1. Use the quality control rules: fast responses, non-automatic acceptance, and post-review re-assessment. [Description of rules with examples](control.md).

1. Reviewing object selection assignments.
    1. Create a task using the object selection template.
    1. Hide the editor and ask whether the object is selected correctly. Response options: Yes/No.
    1. In the input data, pass the images and coordinates of the labeled objects from the previous task.
    Now you can run the resulting pool with an overlap of 3-5 or with dynamic overlap. After that, you can aggregate the results and then upload the data for review to Project 2.
    To prevent the Tolokers who worked on the second project from doing the review, assign a skill to them. Use this skill as a filter in the pools of the third project.

#### I have a task for area selection in an image. What should the Toloker do if there is no selectable object in the image?
Main options:
- Select an arbitrary area in the image (for example, put a square in the upper-right corner). In this case, the project instructions for reviewers should also reflect this.
- Ask the Toloker to skip the task and report it in a personal message. Messages are reviewed by the requester. If the object is truly missing, the task is deleted from the pool by resetting the overlap.
- Add an additional <q>No object</q> checkbox to the interface. Make sure that your JS checks that either the object is selected or the checkbox is enabled. In this case, add information about the checkbox value in the review task interface.

#### How much would 2000 images with a large number of different types of selectable objects cost? How do I create a task for this amount of work?

In the case of crowdsourcing, it's better to break down this task. The simpler the task, the cheaper it is and the better the quality of the final result. The cost of labeling a single class of objects in photos might be about $0.01.

​Base your task on the <q>Object selection in an image</q> template. See the step-by-step guide for creating this type of project on [this page](../tutorials/selection.md).

The editor used in the template lets you add a drop-down list for labeling the selected object. See how to do this in the editor description ([Dropdown list](t-components/image-annotation.md) tab).

#### How do I implement selection of 3 different areas in an image? Select the name, image, and price in the product page screenshot.

You can create a selection + drop-down list with category selection. See how to do this in the editor description ([Dropdown list](t-components/image-annotation.md) tab).

#### What are the input data in the case of object labeling in an image: the coordinates of the object relative to the image, or the coordinates of the object in the Toloka user window?

The coordinates are relative to the image.

#### How do I use the control tasks in the standard template with an area selection editor?

In the standard template with an area selection editor, you can't use the control tasks, because in order for the assignment to be accepted by the system as correct, the object selected by the Toloker must exactly match the control object. This is almost impossible. Therefore, you can leave the GOLDEN field empty in the task file or simply delete all the columns except INPUT.

#### How do I use control and training tasks in the standard template with an area selection editor?

In the standard template with an area selection editor, you can't use the control tasks, because in order for the assignment to be accepted by the system as correct, the object selected by the Toloker must exactly match the control object. This is almost impossible. Therefore, you can leave the GOLDEN field empty in the task file or simply delete all the columns except INPUT.

You can't use [training](../../glossary.md#training-pool-ru) and the main pool with the **Training** type in an area selection project because for the response to be correct, the object selected by the Toloker must exactly match the control object. This is almost impossible.

Such tasks are usually run with non-automatic acceptance: the Toloker submits an assignment, and then the assignment is rejected or accepted after the review.

For pre-selection of users, you can use <q>examination tasks</q>. Review the assignments and assign skills based on the percentage of accepted assignments. For this purpose, add the <q>Results of assignment review</q> rule to the pool. To make sure that only the good Tolokers are admitted to the main pool, put a skill-based filter to the pool.

#### How do I create a task with a selection out of three image options with the paired image comparison?

1. Use the <q>Side-by-side image comparison</q> template.
1. In the TSV file, specify the links to the compared images.
1. In the file, create the tasks where all the images will be compared in pairs:
    - Image 1 and Image 2

    - Image 1 and Image 3

    - Image 2 and Image 3

1. Process the results.

You can also edit the project so that the Toloker sees 3 images at once and selects one of them.

#### Setting up <q>Semantic analysis and content moderation</q> tasks

#### How do I classify texts according to their meanings?

You can structure your text classification task using the source text and radio buttons. It can also be text and checkboxes if you use multiple subjects.

We recommend that you base it on the <q>Text classification</q> template.

You can also create your own interface. All the available tools are described in the [Requester's guide](spec.md).

#### How do I create a task using both input and output text fields?

You can see how it's implemented in the  template where a string-type output field is used. In the <q>Text recognition from an image</q> template, you can view how to describe text input fields. Please note that if you later want to use the Dawid-Skene aggregation method, you must specify allowed values.

#### Setting up tasks with audio and video

#### Can I add a video player or audio player to my instructions?
No, but you can add links to them.

#### How do I make a voice recording of a text in a single audio file, but use about 1000 people to record it?

You need to break down your task for Toloka. If you have a 30-minute task intended for one person and containing all the phrases, the best approach is to divide it into individual phrases, which you can give to different Tolokers. The template for voice recording tasks doesn't require that the Toloker installs a separate voice recorder app.

Refer to our step-by-step guide for creating a [voice recording task](record-audio.md).

In the input data, you can pass the phrase for the Toloker to record ("enable navigation"), and the speech speed (normal speed). This is the data you need to save in the TSV file. See the [Guide](pool_csv.md) to learn about creating a TSV file and its structure.

The preview contains 4 tasks per suite by default. You can specify the number of tasks for your project when you upload the task file. [Learn more about the preview](spec.md).

For example, if you want one person to say the same phrase 10 times, create 10 tasks in a suite. The cost is specified per task suite. To define how many people should say a particular phrase, use the overlap in the pool. By the way, don't forget to set up filters in your pool. This way you can select only the Tolokers who speak a certain language and use mobile devices: client = mobile Toloka.

You can delegate review of the voice recordings to other Tolokers by creating a separate project. Find brief instructions on how to do this [here](record-audio.md).

#### How do I make an image expand to its maximum size on click?

To the component that inserts the image, add the parameters: `real-size=true` and `screenshot=true`.

#### Setting up <q>Data Collection</q> tasks

#### How do I create a simple survey with no options, where the Toloker answers an open-ended question?

1. Create a project from an empty template.
1. Write your question in the HTML block.
1. If you need an [extensive](t-components/text.md) response, add the required number of text entry components.
1. If you need a [short](t-components/string.md) response, add the required number of string entry components.
1. Come up with a name for each of the components and create a matching number of string-type output fields with the same names. They will be used to save responses.
1. Make all the output fields mandatory.
1. Make the input field auxiliary. It will only be used to create a TSV file with tasks.
1. Come up with a name for the input field and set the string type for it (see the step-by-step [guide on creating a survey](questionnaire.md)).

#### How do I create a survey with a single question based on the preset survey template?

The survey includes an auxiliary input field. You can use it to pass any information, and it won't be visible to Tolokers.

Upload one task and use the overlap parameter to enter the number of people you want to survey.

#### I have a complex task. How do I break it down to get high-quality results?

If your task contains many objects of different types, you should break it down. For example, you can ask users to select numbers in the first project, doorways and windows in the second project, walls in the third project, and plumbing in the fourth project.

The simpler the task, the cheaper it is and the better the quality of the final result. Set the cost of labeling a single class of objects in photos at about $0.01.

[Use](../tutorials/selection.md) the **Object selection in an image** template. You can open this template in the editor and add a drop-down list for labeling the selected object. See how to do this in the editor [description](t-components/image-annotation.md#annotation) (**Dropdown list** tab).

#### How do I add response validation depending on a checkbox?

You can use JavaScript to add assignment validation depending on a checkbox. An example is provided in the <q>Search for information online</q> template.

#### Can I limit the source of the photo to camera-only in a field task so that the Toloker can't upload a photo from anywhere else?

To open the camera instead of the gallery when the Toloker taps the image upload button, in the **Image upload button **component specify `camera=true`.

In the mobile apps, Tolokers can add photos from the default gallery (iOS) or Google photo (Android). To limit the capacity of adding online images, specify in the component `requiredCoordinates=true`. In this case, the system won't let the Toloker add images without geotags.

[Learn more about setting up the image upload component](t-components/upload-picture.md) .


{% include [contact-support](../_includes/contact-support-help.md) %}
