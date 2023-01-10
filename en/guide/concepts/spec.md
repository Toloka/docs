# Task interface

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in the [Template Builder](../../template-builder/index.md).

{% endnote %}

The {% if locale == "en-com" %}**task interface**{% endif %} defines the visual appearance of the task for the Toloker and the logic for processing responses.

A user-friendly interface improves the quality of results, helps Tolokers complete tasks faster, and lets you set a lower price per task.
{% if locale == "en-com" %}

To learn how to create a user-friendly interface, read the article in our [knowledge base]({{ toloka-knowledge-base }}).
{% endif %}

## Interface configuration block {#interface-section}

Hover over an item in the image to see a hint:

![](../_images/location-job/spec.png)

{% note tip %}

To open the **HTML**, **CSS**, and **JS** blocks in the interface, click the block name on the right.

{% endnote %}

## HTML block {#html}

Add elements for the [input and output data](incoming.md) to display in the task interface in this block. You can use special components or HTML tags inside the `<body>` tag.

[Handlebars](t-components/handlebars.md) is used as a template engine for HTML.

{% cut "How do I add a component?" %}

1. Open the task interface editor. To do this, find the {% if locale == "en-com" %}**Task interface**{% endif %} section, click ![](../_images/location-job/helper-icon.svg), and select the component.

    Click {% if locale == "en-com" %}**More**{% endif %} to see an example and a full list of parameters.

1. Copy the expression using the ![](../_images/copy.svg) button and paste it into the HTML block.

1. Enter the field name from the input or output data.

{% endcut %}

{% cut "Examples of using input data" %}

- **Display the text in the task.** Add the `text` field with the **string** type in the input data. Then in the task interface (in the HTML block), you can add this text as a variable, for example:

    {% if locale == "en-com" %}

    ```html
    <p>Read the text: not_var{{text}}</p>
    ```

    {% endif %}
- **Upload a file to the task, for example, an image.** Add the `url` field with the **URL** type in the input data. Then add the [Picture](t-components/img.md) component in the task interface (in the HTML block) and specify the field name in the `src` attribute:

    ```html
    {{img src=url width="400px" height="300px"}}
    ```

{% endcut %}

{% cut "Examples of using output data" %}

- **Ask Tolokers to enter the text.** Add the `input` field with the **string** type in the output data. Make the field mandatory. Then add the [Text input field](t-components/text.md) field in the task interface (in the HTML block) and specify the field name in the `name` attribute:

    ```html
    {{field type="textarea" name="input" width="270px" rows=5}}
    ```

- **Ask Tolokers to select one of the values.** Add the `result` field with the **string** type in the output data. Make this field mandatory and specify `Yes` and `No` as acceptable values. Then add a component [Radio button](t-components/radiobuttons.md) component in the task interface (in the HTML block) and specify the field name in the `name` attribute:

    {% if locale == "en-com" %}

    ```html
    {{field type="radio" name="result" label="Yes" value="Yes" hotkey="1"}}
    {{field type="radio" name="result" label="No" value="No" hotkey="2"}}
    ```

    {% endif %}

{% endcut %}

## JavaScript block {#js}

In the **JS** block, you can add rules for response processing in JavaScript. [Special extensions for task classes](spec-advanced.md) are available for this purpose.

You can also connect JavaScript libraries to create the interface. For example, if you have several [projects](../../glossary.md#project) with similar tasks, save the method descriptions in a separate file and add it as a library.

To connect the JavaScript library, click the ![](../_images/settings.svg) button in the {% if locale == "en-com" %}**Task interface**{% endif %} block and add links to libraries in the **JS** field.

## CSS block {#css}

In the **CSS** block, you can declare the design for tags and classes. For example, the indent at the bottom after a text field with the `task-text` class:

```css
.task-text{
  margin-bottom: 15px;
};
```

In addition, you can connect a CSS library. To do this, click the ![](../_images/settings.svg) button in the {% if locale == "en-com" %}**Task interface**{% endif %} block and add links to libraries in the **CSS** filed.

## Preview features {#preview}

{% note alert %}

Changes to the input and output data, as well as the number of tasks per suite aren't saved after you exit {% if locale == "en-com" %}**Preview**{% endif %}.

{% endnote %}

To view the resulting task, click {% if locale == "en-com" %}**Preview**{% endif %}. The preview shows a page with a task that contains standard data. Change the input data and make sure that images, links, or text are displayed correctly on the [task suite](../../glossary.md#task-suite). You can also complete one or more tasks and get responses.

{% cut "How do I change the number of standard tasks?" %}

You can change the number of tasks with standard data on the Preview page:

1. Click {% if locale == "en-com" %}**Change input data**{% endif %}.

1. To add a task, click {% if locale == "en-com" %}**Add task**{% endif %}.

    To delete a task, click its number, then click ![](../_images/bin.svg).

1. Click {% if locale == "en-com" %}**Apply**{% endif %}.

{% endcut %}

{% cut "How to check the input data display" %}

Add input data to check if files or text hints are displayed on the task suite. To do this, click {% if locale == "en-com" %}**Change input data**{% endif %} and choose one of the methods:

{% list tabs %}

- Filling in the table

  1. Change the input data fields.

      To change the task type to [control](../../glossary.md#control-task) or [training](../../glossary.md#training-task), add correct responses and a hint (the {% if locale == "en-com" %}**Add correct answers**{% endif %} button).

      To go to the next task, click the task number at the bottom of the table. To delete a task, click ![](../_images/bin.svg).

  1. Click {% if locale == "en-com" %}**Apply**{% endif %}.

- File upload

  1. Get the sample upload file here: {% if locale == "en-com" %}**Download example file**{% endif %}.

  1. [Add the task data](pool_csv.md) to the file.

  1. Save the file in UTF-8 encoding with the [tsv](pool_csv.md) extension.

  1. Click the {% if locale == "en-com" %}**Upload file**{% endif %} button and choose the file.

  1. Check whether the fields are filled in correctly in the {% if locale == "en-com" %}**Table**{% endif %}.

      If the column headers are invalid, you will get the message "Error loading the file".

      If the value of the required input field is not specified, or the number of fields in the header and row do not match, the task won't load. Refresh the page to return to viewing, correct the errors in the file, and load it again.

  1. Click {% if locale == "en-com" %}**Apply**{% endif %}.

- Data in JSON format

  1. Choose **JSON**.

  1. Fill in the data for verification in [JSON format]({{ json-format }}).

      If the box is bordered in red, the JSON is not valid and the data won't be saved.

  1. Click {% if locale == "en-com" %}**Apply**{% endif %}.

  Complete the task and click {% if locale == "en-com" %}**Submit**{% endif %}.

{% endlist %}

{% endcut %}

{% cut "How do I check if output data is received correctly?" %}

You can check some of the received data on the task suite.

To check if the data from text comments or checkboxes is received correctly, fill in these task fields and click **Submit**. Then click **View responses**.

{% note tip %}

Use the [Sandbox](../../glossary.md#sandbox) to check if files, images, audio, or videos submitted from the task suite are received correctly. To do this, complete the project creation, create the same project in the Sandbox, and [complete](sandbox.md) it from a trusted user account.

{% endnote %}

{% endcut %}

## Controls in a task {#controls}

To change the set of controls, click **Show common interface elements** at the bottom of the {% if locale == "en-com" %}**Task Interface**{% endif %} section.

By default, the task suite displays:

- **Time remaining** (counts down the time for completing the task).

- **Price per task suite**.
- **Task name** (project name).

- The following buttons: {% if locale == "en-com" %}**Message to requester**{% endif %}, {% if locale == "en-com" %}**Guidelines**{% endif %}, {% if locale == "en-com" %}**Fullscreen**{% endif %}, {% if locale == "en-com" %}**Submit**{% endif %}, {% if locale == "en-com" %}**Skip**{% endif %}, {% if locale == "en-com" %}**Exit**{% endif %}.

{% note tip %}

{% if locale == "en-com" %}
Read the [article]({{ toloka-knowledge-base }}) on how to make the task interface intuitive and user-friendly.
{% endif %}

{% endnote %}

## What's next {#what-next}

- [Adapt the task interface for mobile devices](mobile.md).
- [Create a task pool in the project](pool-main.md).
- Learn more about how to set up a project:

    - [Writing instructions](instruction.md).
    - [Input and output data](incoming.md).
    - [Setting up quality control](project-qa.md).

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Interfaces](https://toloka.ai/knowledgebase/interface/)
- [{#T}](edit-project.md)

## Troubleshooting {#troubleshooting}

{% cut "Setting up tasks, preview" %}

{% include [troubleshooting-cant-upoad-file](../_includes/troubleshooting/project-settings/cant-upoad-file.md) %}

{% include [faq-mobile-task-display](../_includes/faq/project-settings/mobile-task-display.md) %}

{% include [faq-hide-expandable](../_includes/faq/project-settings/hide-expandable.md) %}

{% include [faq-calendar](../_includes/faq/project-settings/calendar.md) %}

{% cut "How do I enable loading audio files in preview mode?" %}

You can't check loading of audio files in the preview mode, but you can do it in the sandbox if you do your task. To do this, register in the sandbox as a Toloker and add the Toloker username to your trusted list on the **Tolokers** page. For more information, see [this post](sandbox.md).

{% endcut %}

{% endcut %}

{% cut "Setting up controls" %}

{% cut "How do I add the text from an input variable to a checkbox label?" %}

To pass a `label` in the input data, enter the input field name into the label.

For example, if you have the `asd` input field with the string type, the component would look like: `{{field type="checkbox" name="like" label=asd hotkey="q"}}`.

If you want to pass different label values in different tasks or the number of checkboxes may differ, use [concatenation](t-components/helpers.md#concat).

{% endcut %}

{% cut "I selected one checkbox, but all the checkboxes are selected." %}

The names of the output fields must differ: each checkbox must have its own unique name. For more information about this component, see [here](t-components/checkboxes.md).

{% endcut %}

{% cut "How can I do it in JS so that if the checkbox is selected, the link is not required, but if the link is inserted, the checkbox is cleared?" %}

1. See how this is implemented in the “[Mining business contacts](../tutorials/internet-search.md)” template.

1. To solve the second problem, you can add another validation like this:

    {% if locale == "en-com" %}

    ```javascript0
    if (solution.output_values.url && solution.output_values.check) {return {task_id:
    this.getTask().id,errors: {'url': {code: ''Insert a link or check the box if the site doesn't exist'}}}}
    ```

    {% endif %}

{% endcut %}

{% cut "How do I make tasks that have a varying number of response options and different options available?" %}

You can do this using [concatenation](t-components/helpers.md#concat).

See the sample projects that can help you build an interface:

- [with checkboxes]({{ project-with-checkboxes }})

- [with a dropdown list]({{ project-with-drop-down-list }})

- [with radio buttons]({{ project-with-radiobutton }})

If you pass an array of values to the input field, use commas to separate the array elements. A response option will be generated for each of them in the interface. Input/output data for the sample projects are provided in the comments at codepen.io.

{% endcut %}

{% include [troubleshooting-submit-doesnt-work](../_includes/troubleshooting/project-settings/submit-doesnt-work.md) %}

{% include [faq-checkbox-selected](../_includes/faq/project-settings/checkbox-selected.md) %}

{% cut "How do I use different numbers of response options for different questions?" %}

Use [concatenation](t-components/helpers.md#concat), for example:

```html
{{field type="checkbox" name=(concat "result." @index ) label=(concat "checkbox –
                " @index) size="L"}}
```

{% endcut %}

{% include [faq-deselect-radio](../_includes/faq/project-settings/deselect-radio.md) %}

{% include [faq-assigment-validation](../_includes/faq/project-settings/assigment-validation.md) %}

{% cut "How do I change the task background from the standard white color to a different color?" %}

Use CSS to specify the color for the `.task` or `.task-suite` element. For example, to use a black background:

```css
.task-suite {
    background-color: #000000;
    }
    .task {
    background-color: #000000;
    }
```

You can also assign a class to the interface block with the image and set the background for this block only.

{% endcut %}

{% cut "How do I use sliders as interface elements for selecting parameter values?" %}

In the HTML code of the template, enter the following:

{% if locale == "en-com" %}

```html
<input type=""range"" list=""rng"" class=""res"">
```

and include the following in onRender in your JS:

```javascript
onRender: function() {
// Generated DOM element for the task (available via #getDOMElement())
//Adding auxiliary variables
var $root = $(this.getDOMElement());
var _this = this;
var solution = TolokaHandlebarsTask.prototype.getSolution.apply(this, arguments);

$root.on('change', '.res', function(){
var range_result = $(this).val()
_this.setSolutionOutputValue('result', range_result);

return solution;
})
}
```

{% endif %}

{% endcut %}

{% include [faq-expand-window](../_includes/faq/project-settings/expand-window.md) %}

{% cut "Can I use my own JS to build an interface in Toloka?" %}

You don't have to use our components for task interfaces. Feel free to create a custom design for your tasks. To do this, delete the library from the project template:

- Click the “gear button” to open the settings.

- Delete `$TOLOKA_ASSETS/js/toloka-handlebars-templates.js`.

See the [documentation](spec-advanced.md) for descriptions of the structure of classes and how they work.

{% endcut %}

{% cut "What do I do if the radio button attributes are displayed correctly in the preview, but disappear after saving?" %}

If the tags or attributes disappear after you save the instructions (for example, `checked="true"`), it means that they are not supported. For the full list of tags that can be used in the instructions, see the [Guide](instruction.md#html-yes).

{% endcut %}

{% include [faq-implement-prettifier](../_includes/faq/project-settings/implement-prettifier.md) %}

{% endcut %}

{% cut "Input and output data" %}

{% include [troubleshooting-iframe-content](../_includes/troubleshooting/project-settings/iframe-content.md) %}

{% include [faq-pass-value](../_includes/faq/project-settings/pass-value.md) %}

{% include [faq-line-by-line](../_includes/faq/project-settings/line-by-line.md) %}

{% include [faq-use-input-data](../_includes/faq/project-settings/use-input-data.md) %}

{% cut "How do I display formatted text from input data in the task?" %}

Enclose the input field in triple curly brackets `{not_var{{input_field}}}`.

More information about [using the component](t-components/html.md).

{% endcut %}

{% cut "How do I use a variable number of inputs in HTML to be determined by the Toloker?" %}

To change the number of output fields dynamically, use the recommendations from [this page](t-components/helpers.md).

{% endcut %}

{% include [faq-display-text](../_includes/faq/project-settings/display-text.md) %}

{% endcut %}

{% cut "Validation" %}

{% cut "How do I use the Vue markup without the basic TolokaHadlebarsTask object?" %}

Learn more about the template's JS extension [here](spec-advanced.md).

To avoid conflict between the Vue markup and the Handlebars syntax, disable the "toloka-handlebars-templates" library and inherit from the Task/TaskSuite classes.

{% endcut %}

{% include [faq-setsolution](../_includes/faq/project-settings/setsolution.md) %}

{% include [faq-validate-data](../_includes/faq/project-settings/validate-data.md) %}

{% endcut %}

{% cut "Tasks with images" %}

{% include [faq-image-expand](../_includes/faq/project-settings/image-expand.md) %}

{% include [faq-shortcut](../_includes/faq/project-settings/shortcut.md) %}

{% include [faq-show-photo](../_includes/faq/project-settings/show-photo.md) %}

{% include [faq-prevent-adding-photos](../_includes/faq/project-settings/prevent-adding-photos.md) %}

{% cut "How do I implement selection of 3 different areas in an image?" %}

You can create a selection and drop-down list with category selection. See how it is implemented on [this page](t-components/image-annotation.md) (**Dropdown list** tab).

{% endcut %}

{% cut "In the “Side-by-side image comparison” template, where do I specify a proxy for the task interface to create a task with three image options?" %}

The “Side-by-side image comparison” template uses a component rather than an HTML tag. This means that you should enclose your proxy in curly brackets like this [example](t-components/img.md): `{{img src=(proxy image)}}`.

{% endcut %}

{% cut "What should the Toloker do if there is no selectable object in the image in an area selection task?" %}

There are four options:

- [ Decompose the task](solution-architecture.md): First select images with the items you need, then select areas in them.

- Select an arbitrary area in the image. For example, put a square in the upper-right corner.

    Mention this in your instructions for reviewers.

- Ask the Toloker to skip the task and report it in a personal message. Messages are reviewed by the requester. If the selectable object is missing, the task is deleted from the pool (by resetting the overlap).

- Add the “No object” checkbox to the interface and make sure that your JS checks that either the object is selected or the checkbox is selected.

    For control purposes, add information about the value of this checkbox to the task interface.

{% endcut %}

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}