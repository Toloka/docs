# Setting up a project

{% note info %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}


## Instructions {#concept_llj_dkp_smb}

#### How do I show my instructions to the Toloker inside the task so that they don't need to open or close it?

There are three options:
- Put your instructions inside the task, but make sure that it doesn't clutter the interface.
- Use [a side window]({{ instr-in-form-of-side-window }}) for your instructions so that the Toloker can quickly expand or collapse them.
- [Hide the instructions in an expandable section]({{ hints-questions }}) or add hints for the individual interface elements.
For best results, we recommend that you pre-select the Tolokers that meet your requirements and set up the quality control rules.
#### Can I add a video player or audio player to my instructions?
No, but you can add links to them.
#### Some tags disappear after I save the instructions.
You can't use unsupported tags because they are deleted when you save the project. [List of supported tags](../concepts/instruction.md#html).
#### How do I create different instructions for the training pool and main pools?
By default, the project instructions are displayed in the training pool. To use separate instructions for the training pool, deselect **Use project instructions**. Don't forget to update the training instructions if you change something in the general task instructions.
#### What do I do if the radio button attributes are displayed correctly in the preview, but disappear after saving?

If the tags or attributes disappear after you save the instructions (for example, `checked="true"`), it means that they are not supported. For the full list of tags that can be used in the instructions, see the [Guide](../concepts/instruction.md#html-yes).

[Other questions](support.md#help)


## Configuring the task interface {#concept_gss_fkp_smb}

#### How do I make an image expand to its maximum size on click?

To the component that inserts the image, add the parameters: `real-size=true` and `screenshot=true`.

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

If you need to further modify the area-selection editor, use [this library](https://github.com/vmit/image-annotation).

#### How do I enable loading audio files in preview mode?

You can't check loading of audio files in the preview mode, but you can do it in the sandbox if you do your task. To do this, register in the sandbox as a Toloker and add the Toloker username to your trusted list on the **Tolokers** page. For more information, see [this post](../concepts/sandbox.md).

#### My Tolokers can't upload a file with the assignment

If none of the Tolokers can submit the assignment, the most likely reason is JS validation. Run JS validation again.

Export your project to the sandbox and try to complete the task in the sandbox yourself.

#### How do I check the task display in the mobile Toloka app?

To check the task's look-and-feel on the mobile phone screen, enable the emulation mode in Chrome or Safari and edit the CSS block.

You can also use the mobile version of the sandbox. Write to support to get access to it.

#### How do I use different numbers of response options for different questions?

Use [concatenation](../concepts/t-components/helpers.md#concat), for example:
```
{{field type="checkbox" name=(concat "result." @index ) label=(concat "checkbox –
          " @index) size="L"}}
```

#### Why is the iframe content not displayed when I add the input and output data to the HTML interface in the preview mode?

Try to disable extensions in your browser. They might block iframe loading.

#### How do I add the text from an input variable to a checkbox label?

To pass a `label` in the input data, enter the input field name into the label.

For example, if you have the `asd` input field with the string type, the component would look like: `{{field type="checkbox" name="like" label=asd hotkey="q"}}`.

If you want to pass different label values in different tasks or the number of checkboxes may differ, use [concatenation](../concepts/t-components/helpers.md#concat).

#### How do I hide expandable text?

You can hide text in an expandable section by using CSS styles, both in the task itself and in the instructions. You can see the sample code [here]({{ text-under-the-cut }}).

#### How do I pass the value of the input variable to the <q>Button with click validation</q>?

Specify the name of the input field where you pass the link, without the brackets:{% if locale == "en-com" %}
```
{{field type="button-clicked" name="ads" label="Click me" href=name_escape
          action=true}}
```
{% endif %}

#### How can I do it in JS so that if the checkbox is selected, the link is not required, but if the link is inserted, the checkbox is cleared?

1. See how this is implemented in the  template.
1. To solve the second problem, you can add another validation like this:{% if locale == "en-com" %}
    ```
    if (solution.output_values.url && solution.output_values.check) {return {task_id:
    this.getTask().id,errors: {'url': {code: ''Insert a link or check the box if the site doesn't exist'}}}}
    ```
    {% endif %}

#### I selected one checkbox, but all the checkboxes are selected.

The names of the output fields must differ: each checkbox must have its own unique name. For more information about this component, see [here](../concepts/t-components/checkboxes.md).

#### How do I add assignment validation depending on a checkbox, so that if an object is in the image, it must be selected, otherwise, a checkbox must be selected?

You can use JavaScript to add assignment validation depending on the checkbox. An example is provided in the <q>Search for information online</q> template.

#### How do I insert a calendar?

You can see an example in the comments for this [project]({{ how-to-insert-a-calendar }}). The example includes the output data format and libraries to be added.

To add libraries:
1. Click the <q>gear button</q> in project editing mode.
1. In the field that opens on the left, enter the links and press **Enter**.

#### Why doesn't the <q>Submit</q> button work in the task?

The issue is probably in the JS block. Try deleting its content, then test the **Submit** button in the preview mode.

#### How do I make tasks that have a varying number of response options and different options available?
You can do this using [concatenation](../concepts/t-components/helpers.md#concat).
See the sample projects that can help you build an interface:
- [with checkboxes]({{ project-with-checkboxes }})
- [with a dropdown list]({{ project-with-drop-down-list }})
- [with radio buttons]({{ project-with-radiobutton }})
If you pass an array of values to the input field, use commas to separate the array elements. A response option will be generated for each of them in the interface. Input/output data for the sample projects are provided in the comments at codepen.io.

#### How do I deselect a radio button?

You can't deselect a radio button. You can only select another radio button as a different response option.

#### How do I, depending on the option selected, show a photo and make it mandatory or hide it and make it optional?

In this case, you need to leave the field optional in the output data and set up validation depending on the Toloker response. You can see how this is implemented in the <q>Text classification</q> template.

#### How do I prevent adding photos from the gallery so that when the Toloker clicks the add photo button the camera opens, rather than the gallery/camera choice?

Add `sources="CAMERA"` to the attributes of the image loading component. This disables adding photos from the gallery.

#### How do I run setSolution validation in "OnRender"?

Try to add a condition to check for the second progress bar:
```
setSolution: function(solution) {
var secondScale = this.getDOMElement().querySelector('.second-scale');

if(secondScale) {
secondScale.style.display = solution.output_values.grammar === 'no' ? 'block' : 'none';
}

TolokaHandlebarsTask.prototype.setSolution.call(this, solution);
},
```

#### How do I implement selection of 3 different areas in an image?

You can create a selection and drop-down list with category selection. See how it is implemented on [this page](../concepts/t-components/image-annotation.md) (**Dropdown list** tab).

#### How do I use the Vue markup without the basic TolokaHadlebarsTask object?

Learn more about the template's JS extension [here](../concepts/spec-advanced.md).

To avoid conflict between the Vue markup and the Handlebars syntax, disable the "toloka-handlebars-templates" library and inherit from the Task/TaskSuite classes.

#### In the <q>Side-by-side image comparison</q> template, where do I specify a proxy for the task interface to create a task with three image options?

The <q>Side-by-side image comparison</q> template uses a component rather than an HTML tag. This means that you should enclose your proxy in curly brackets like this [example](../concepts/t-components/img.md): `{{img src=(proxy image)}}`.

#### How do I change the task background from the standard white color to a different color?

Use CSS to specify the color for the `.task` or `.task-suite` element. For example, to use a black background:
```
.task-suite {
background-color: #000000;
}
.task {
background-color: #000000;
}
```
You can also assign a class to the interface block with the image and set the background for this block only.

#### How do I validate the data entered by the Toloker in the Toloka interface?

You can check the link format using regular expressions. To do this, add the link validation JavaScript code with `regexp` to the task template.

For example: `var regexp = /^(https://www.myurl.com/).{4,200}$/`.

You can also add a regular expression to the `input` field with the **string** type in the output data. Make the field mandatory. Then add the **Text input field** field in the task interface (in the HTML block) and specify the field name in the `name` attribute:
```
{{field type="textarea" name="input" width="270px" rows=5}}
```

#### How do I add assignment validation depending on a checkbox?

You can use JavaScript to add assignment validation depending on a checkbox. An example is provided in the <q>Search for information online</q> template.

#### How do I enter a list of words line-by-line, display an element for each of them, and save the result to the output array?

Pass an array of strings as the input field. For example, as shown in the screenshot: ![](../_images/troubleshooting/array-each-words.png)
In HTML, use a special handlebar to iterate over this field. The code structure will look like this:
```
{{#each words}}
{{field type="radio" name="result" value=this label=this}}
{{/each}}
```

#### How do I use sliders as interface elements for selecting parameter values?
In the HTML code of the template, enter the following:{% if locale == "en-com" %}
```
<input type=""range"" list=""rng"" class=""res""> and include the following in onRender in your JS:
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
#### How can I expand the window with HTML/CSS/JS code in the online task editor?

You can't expand the HTML window. To expand the JS and CSS fields, click any area within the field.

#### How do I use the input data as a variable in the HTML block?

Enclose the input field in double curly brackets `{{text}}`.

#### How do I display formatted text from input data in the task?

Enclose the input field in triple curly brackets `{{{input_field}}}`.

For more information about using the component, see the [Requester's guide](../concepts/t-components/html.md).

#### Can I use my own JS to build an interface in Toloka?

You don't have to use our components for task interfaces. Feel free to create a custom design for your tasks. To do this, delete the library from the project template:
- Click the <q>gear button</q> to open the settings.
- Delete `$TOLOKA_ASSETS/js/toloka-handlebars-templates.js`.
See the [Requester's guide](../concepts/spec-advanced.md) for descriptions of the structure of classes and how they work.

#### How do I use a variable number of inputs in HTML to be determined by the Toloker?

To change the number of output fields dynamically, use the recommendations from [this page](../concepts/t-components/helpers.md).

#### Are you going to implement an HTML/JS prettifier in the project design?

We didn't intend this window for any sophisticated development. Usually, the content is prepared in a third-party prettified editor, and the resulting code is pasted to the window prior to the update.

However, in the context of TolokaHandlebars editability, there are no differences between our window and a third-party editor.

#### How do I display the text in the input field as in the source (with the HTML tags)?

To display the text in the input field with HTML tags, use the `<pre>` tag. For example:`<pre>{{text}}</pre>`.

In this case, the text is rendered as is, in one scrollable line. To remove the scroll and avoid stretching the task card, add the following CSS to the block:
```
.task {
  max-width: 800px;
}

pre {
  white-space: pre-wrap;
}
```

#### What should the Toloker do if there is no selectable object in the image in an area selection task?

There are four options:
- [ Decompose the task](../concepts/solution-architecture.md): First select images with the items you need, then select areas in them.
- Select an arbitrary area in the image. For example, put a square in the upper-right corner.
    Mention this in your instructions for reviewers.

- Ask the Toloker to skip the task and report it in a personal message. Messages are reviewed by the requester. If the selectable object is missing, the task is deleted from the pool (by resetting the overlap).
- Add the <q>No object</q> checkbox to the interface and make sure that your JS checks that either the object is selected or the checkbox is selected.
    For control purposes, add information about the value of this checkbox to the task interface.

#### How do I make a voice recording of a text in a single audio file, but use about 1000 people to record it?

You need to break down your task for Toloka. If you have a 30-minute task intended for one person and containing all the phrases, the best approach is to divide it into individual phrases, which you can give to different Tolokers. The template for voice recording tasks doesn't require that the Toloker installs a separate voice recorder app.

Refer to our step-by-step guide for creating a [voice recording task](../concepts/record-audio.md).

In the input data, you can pass the phrase for the Toloker to record ("enable navigation"), and the speech speed (normal speed). This is the data you need to save in the file. See the [Guide](../concepts/pool_csv.md) to learn about creating a file and its structure.

The preview contains 4 tasks per suite by default. You can specify the number of tasks for your project when you upload the task file. [Learn more about the preview](../concepts/spec.md).

For example, if you want one person to say the same phrase 10 times, create 10 tasks in a suite. The cost is specified per task suite. To define how many people should say a particular phrase, use the overlap in the pool. By the way, don't forget to set up filters in your pool. This way you can select only the Tolokers who speak a certain language and use mobile devices: client = mobile Toloka.

You can delegate review of the voice recordings to other Tolokers by creating a separate project. Find brief instructions on how to do this [here](../concepts/record-audio.md).

[Other questions](support.md#help)


## Input and output data {#concept_cjj_gkp_smb}

#### How do I insert a function that is called by an image click in my task?

You can find an example of the task template for selecting image groups at this [link]({{ selection-of-images-groups }}). The input and output data, as well as a fragment of the instructions, are in the comments to the project.

#### How do I add a mask for the input field, like dd.mm.yyyy for the date field or numbers only (10 or 12) for INN (Taxpayer Identification Number)?

To validate the input data format, you can use the output field type, specifying the acceptable or minimum/maximum values. For example, create an output field for the taxpayer number with the <q>string</q> type and enter its minimum and maximum length (like 10 and 12). To use a more sophisticated validation in the template, use RegExp.

To enter a date, you can add a calendar to the task interface. See an [example of a calendar]({{ how-to-insert-a-calendar }}).

#### Do I need to convert all the images in the task to the same size or can they be different?
You can use different image sizes.
#### If a project's output data may include any number from 1 to 999999, can I specify a range?

You can't use a range as a fixed value.

[Other questions](support.md#help)

{% include [contact-support](../_includes/contact-support-help.md) %}