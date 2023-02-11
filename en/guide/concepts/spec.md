# Task interface

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in the [Template Builder](../../template-builder/index.md).

{% endnote %}

The task interface defines the visual appearance of the [task](../../glossary.md#task) for the Toloker and the logic for processing responses.

A user-friendly interface improves the quality of results, helps Tolokers complete tasks faster, and lets you set a lower price per task.

To learn how to create a user-friendly interface, read the article in our [knowledge base]({{ toloka-knowledge-base }}).

## Interface configuration block {#interface-section}

{% note tip %}

To open the **HTML**, **CSS**, and **JS** blocks in the interface, click the block name on the right.

{% endnote %}

### HTML block {#html}

Add elements for the [input and output data](incoming.md) to display in the task interface in this block. You can use special [components](t-components.md) or HTML tags inside the `<body>` tag.

[Handlebars](t-components/handlebars.md) is used as a template engine for HTML.

{% cut "How do I add a component?" %}

1. Open the task interface editor. To do this, find the **Task interface** section, click ![](../_images/location-job/helper-icon.svg), and select the component.

    Click **Learn more** to see an example and a full list of parameters.

1. Copy the expression using the ![](../_images/copy.svg) button and paste it into the HTML block.

1. Enter the field name from the input or output data.

{% endcut %}

{% cut "Examples of using input data" %}

{% cut "Display the text in the task" %}

Add the `text` field with the `string` type in the input data. Then in the task interface (in the HTML block), you can add this text as a variable, for example:

    ```html
    <p>Read the text: not_var{{text}}</p>
    ```

{% endcut %}

{% cut "Upload a file to the task (for example, an image)" %}

Add the `url` field with the `URL` type in the input data. Then add the [Picture](t-components/img.md) component in the task interface (in the HTML block) and specify the field name in the `src` attribute:

    ```html
    {{img src=url width="400px" height="300px"}}
    ```

{% endcut %}

{% endcut %}

{% cut "Examples of using output data" %}

{% cut "Ask Tolokers to enter the text" %}

Add the `input` field with the `string` type in the output data. Make the field required. Then add the [Text input field](t-components/text.md) field in the task interface (in the HTML block) and specify the field name in the `name` attribute:

    ```html
    {{field type="textarea" name="input" width="270px" rows=5}}
    ```

{% endcut %}

{% cut "Ask Tolokers to select one of the values" %}

Add the `result` field with the `string` type in the output data. Make this field required and specify `Yes` and `No` as acceptable values. Then add a component [Radio button](t-components/radiobuttons.md) component in the task interface (in the HTML block) and specify the field name in the `name` attribute:

    ```html
    {{field type="radio" name="result" label="Yes" value="Yes" hotkey="1"}}
    {{field type="radio" name="result" label="No" value="No" hotkey="2"}}
    ```

{% endcut %}

{% endcut %}

![](../_images/location-job/spec.png)

### JavaScript block {#js}

In the **JS** block, you can add rules for response processing in JavaScript. [Special extensions for task classes](spec-advanced.md) are available for this purpose.

You can also connect JavaScript libraries to create the interface. For example, if you have several [projects](../../glossary.md#project) with similar tasks, save the method descriptions in a separate file and add it as a library.

To connect the JavaScript library, click the ![](../_images/settings.svg) button in the **Task interface** block and add links to libraries in the **JS** field.

### CSS block {#css}

In the **CSS** block, you can declare the design for tags and classes. For example, the indent at the bottom after a text field with the `task-text` class:

```css
.task-text{
  margin-bottom: 15px;
};
```

In addition, you can connect a CSS library. To do this, click the ![](../_images/settings.svg) button in the **Task interface** block and add links to libraries in the **CSS** filed.

## Preview features {#preview}

{% note alert %}

Changes to the input and output data, as well as the number of tasks per suite aren't saved after you exit **Preview**.

{% endnote %}

To view the resulting task, click **Preview task**. The preview shows a page with a task that contains standard data. Change the input data and make sure that images, links, or text are displayed correctly on the [task suite](../../glossary.md#task-suite). You can also complete one or more tasks and get responses.

{% cut "How do I change the number of standard tasks?" %}

You can change the number of tasks with standard data on the preview page:

1. Click **Change input data**.

1. To add a task, click **Add task**.

    To delete a task, click its number, then click ![](../_images/bin.svg).

1. Click **Apply**.

{% endcut %}

{% cut "How to check the input data display" %}

Add input data to check if files or text hints are displayed on the task suite. To do this, click **Change input data** and choose one of the methods:

{% list tabs %}

- Filling in the table

  1. Change the input data fields.

      To change the task type to [control](../../glossary.md#control-task) or [training](../../glossary.md#training-task), add correct responses and a hint (the **Add correct answers** button).

      To go to the next task, click the task number at the bottom of the table. To delete a task, click ![](../_images/bin.svg).

  1. Click **Apply**.

- File upload

  1. Get the sample upload file here: **Download sample file**.

  1. [Add the task data](pool_csv.md) to the file.

  1. Save the file in UTF-8 encoding with the [tsv](pool_csv.md) extension.

  1. Click the **Upload file** button and choose the file.

  1. Check whether the fields are filled in correctly in the **Table**.

      If the column headers are invalid, you will get the message "Error loading the file".

      If the value of the required input field is not specified, or the number of fields in the header and row do not match, the task won't load. Refresh the page to return to viewing, correct the errors in the file, and load it again.

  1. Click **Apply**.

- Data in JSON format

  1. Choose **JSON**.

  1. Fill in the data for verification in the [JSON]({{ json-format }}) format.

      If the box is bordered in red, the JSON is not valid and the data won't be saved.

  1. Click **Apply**.

  Complete the task and click **Submit**.

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

To change the set of controls, click **Show common interface elements** at the bottom of the **Task Interface** section.

By default, the task suite displays:

- **Remaining time**: Counts down the time for completing the task.

- **Price per task suite**.

- **Task name**: Corresponds to the project name.

- The following buttons:

  - **Contact requester button**.

  - **Instructions**.

  - **Fullscreen**.

  - **Submit**.

  - **Skip**.

  - **Exit**.

{% note tip %}

Read the [article]({{ toloka-knowledge-base }}) on how to make the task interface intuitive and user-friendly.

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

{% include [faq-loading-audio-files](../_includes/faq/project-settings/loading-audio-files.md) %}

{% endcut %}

{% cut "Setting up controls" %}

{% include [faq-add-text](../_includes/faq/project-settings/add-text.md) %}

{% include [troubleshooting-all-checkboxes](../_includes/troubleshooting/project-settings/all-checkboxes.md) %}

{% include [faq-link-not-required](../_includes/faq/project-settings/link-not-required.md) %}

{% include [faq-make-tasks](../_includes/faq/project-settings/make-tasks.md) %}

{% include [troubleshooting-submit-doesnt-work](../_includes/troubleshooting/project-settings/submit-doesnt-work.md) %}

{% include [faq-checkbox-selected](../_includes/faq/project-settings/checkbox-selected.md) %}

{% include [faq-different-numbers](../_includes/faq/project-settings/different-numbers.md) %}

{% include [faq-deselect-radio](../_includes/faq/project-settings/deselect-radio.md) %}

{% include [faq-assigment-validation](../_includes/faq/project-settings/assigment-validation.md) %}

{% include [faq-change-background](../_includes/faq/project-settings/change-background.md) %}

{% include [faq-own-colors](../_includes/faq/project-settings/own-colors.md) %}

{% include [faq-sliders](../_includes/faq/project-settings/sliders.md) %}

{% include [faq-expand-window](../_includes/faq/project-settings/expand-window.md) %}

{% include [faq-use-own-js](../_includes/faq/project-settings/use-own-js.md) %}

{% include [troubleshooting-radio-attr-disappear](../_includes/troubleshooting/project-settings/radio-attr-disappear.md) %}

{% include [faq-implement-prettifier](../_includes/faq/project-settings/implement-prettifier.md) %}

{% endcut %}

{% cut "Input and output data" %}

{% include [troubleshooting-iframe-content](../_includes/troubleshooting/project-settings/iframe-content.md) %}

{% include [faq-pass-value](../_includes/faq/project-settings/pass-value.md) %}

{% include [faq-line-by-line](../_includes/faq/project-settings/line-by-line.md) %}

{% include [faq-use-input-data](../_includes/faq/project-settings/use-input-data.md) %}

{% include [faq-display-formatted-text](../_includes/faq/project-settings/display-formatted-text.md) %}

{% include [faq-variable-number](../_includes/faq/project-settings/variable-number.md) %}

{% include [faq-display-text](../_includes/faq/project-settings/display-text.md) %}

{% endcut %}

{% cut "Validation" %}

{% include [faq-vue-markup](../_includes/faq/project-settings/vue-markup.md) %}

{% include [faq-setsolution](../_includes/faq/project-settings/setsolution.md) %}

{% include [faq-validate-data](../_includes/faq/project-settings/validate-data.md) %}

{% endcut %}

{% cut "Tasks with images" %}

{% include [faq-image-expand](../_includes/faq/project-settings/image-expand.md) %}

{% include [faq-shortcut](../_includes/faq/project-settings/shortcut.md) %}

{% include [faq-show-photo](../_includes/faq/project-settings/show-photo.md) %}

{% include [faq-prevent-adding-photos](../_includes/faq/project-settings/prevent-adding-photos.md) %}

{% include [faq-different-areas](../_includes/faq/project-settings/different-areas.md) %}

{% include [faq-side-by-side](../_includes/faq/project-settings/side-by-side.md) %}

{% include [faq-no-selectable-object](../_includes/faq/project-settings/no-selectable-object.md) %}

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}