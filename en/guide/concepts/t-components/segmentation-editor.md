# Text segmentation editor

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a text segmentation editor in {% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.text-annotation){% endif %}.

{% endnote %}


Tolokers can mark up text using the editor in the Toloka web interface. You put the text in the editor, and the Toloker selects individual words and entire phrases, and then marks them with tags.

{% note info %}

The text segmentation editor doesn't work on mobile devices.

{% endnote %}


To make your task available only to Tolokers who log in via a browser, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select {% if locale == "en-com" %}**Toloka web version**{% endif %}. This way, Tolokers won't see the task in the mobile app but will be able to log in using a mobile browser. To prevent Tolokers from accessing the task through mobile browsers, add another filter: {% if locale == "en-com" %}**Device type**{% endif %} = {% if locale == "en-com" %}**Personal computer**{% endif %}.

## Text editor features {#what}

The editor supports 10 colors for [category tags](#adding_editor). You can add more than 10 tags, but then the colors will repeat. The first of the specified tags is active.

{% note info %}

Think about [decomposing the task](../solution-architecture.md). The more tags, the more complex the instruction and the response review process.

{% endnote %}


## How do I set it up? {#whats-inside}

To enable Tolokers to use the editor, import the necessary libraries and add the JS code and CSS styles.

#### Learn more

If you're using an empty template:

1. In the **Task interface** block on the project editing page, click ![](../../_images/settings.svg)
1. In the **Libraries ** block, add:
    - JS `toloka-handlebars-templates.js`
    - JS `https://yastat.net/s3/toloka/presets/TemplateVideoModeration/494c560d-0f4e-4e71-928f-5d9710522893.js`
    - CSS `https://yastat.net/s3/toloka/presets/TemplateVideoModeration/26a20e48-5dfb-4acc-abbf-a8ab7d91bf3f.css`

1. In the **Specification** block, add the fields that are used by the editor:
    - Add the `input` field with the **string** type in the input data.
    - Add the `result` field with the **json** type and the `text_review_mode` with the **JSON array** type in the output data.

1. In the HTML block, add the `not_var{{textAnnotationInterface input tagsData}}` component.
1. Add the following code in the JS block:

{% if locale == "en-com" %}
    ```javascript
    var tagsData = [
    {
    'tag_color': 'Blue',
    'tag_name': 'Name',
    'tag_hotkey': 'q'
    },
    {
    'tag_color': 'Yellow',
    'tag_name': 'Brand',
    'tag_hotkey': 'w'
    },
    {
    'tag_color': 'Green',
    'tag_name': 'Volume',
    'tag_hotkey': 'e'
    },
    {
    'tag_color': 'Red',
    'tag_name': 'Error',
    'tag_hotkey': 'r'
    },
    {
    'tag_color': 'Gray',
    'tag_name': 'Manufacturer',
    'tag_hotkey': 't'
    }
    ];

    function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function () {};
    prototypeHash = prototypeHash || {};
    if (ParentClass) {
    constructorFunction.prototype = Object.create(ParentClass.prototype);
    }
    for (var i in prototypeHash) {
    constructorFunction.prototype[i] = prototypeHash[i];
    }
    return constructorFunction;
    }

    exports.Task = extend(TolokaHandlebarsTask, function(options) {
    TolokaHandlebarsTask.call(this, options);
    }, {
    getTemplateData: function() {
    var data = TolokaHandlebarsTask.prototype.getTemplateData.apply(this, arguments);
    data.tagsData = updateTagsData(tagsData);

    return data;
    },
    onRender: function() {
    var tagsData = this.getTask().input_values.tagsData;
    createTextAnnotationInterface.call(this, tagsData);
    },
    addError: function(message, field, errors) {
    errors || (errors = {
    task_id: this.getOptions().task.id,
    errors: {}
    });
    errors.errors[field] = {
    message: message
    };

    return errors;
    },

    validate: function(solution) {
    var errors = null;

    // If no words are selected, we show an error message.

    if (Object.keys(solution.output_values).length === 0 || Object.keys(solution.output_values.result).length === 0) {
    errors = this.addError('Select at least one word', '__TASK__', errors);
    }

    return errors || TolokaHandlebarsTask.prototype.validate.call(this, solution);
    },
    onDestroy: function() {
    // The task is completed, you can release global resources (if you used them)
    }
    });
    ```
    {% endif %}

1. In the CSS block, add the following styles:

{% if locale == "en-com" %}
    ```css
    /* Task on the page */
    .task {
    display: block;
    max-width: 1200px;
    margin: 20px auto;
    font-size: 18px;
    }

    .task-suite {
    height: 100%;
    }

    /* Task display on mobile devices */
    @media screen and (max-width: 767px) {
    .task {
    border: none;
    }

    .task_focused {
    box-shadow: none;
    -webkit-box-shadow: none;
    }
    }
    ```
    {% endif %}

1. Click **Preview** and view the result.

## Tag descriptions {#adding_editor}

The editor uses category tags for text segmentation. Each tag has three parameters:

- tag_color — The color the text will be repainted. The editor supports 10 colors for tags.
- tag_name — The category to assign to the selected text.
- tag_hotkey — The button to press to make it faster.

#### Colors and keyboard shortcuts

- Blue — **Q**.
- Yellow — **W**.
- Green — **E**.
- Gray — **T**.
- Red — **R**.
- Brown — **Y**.
- Violet — **U**.
- Orange — **I**.
- Pink — **A**.
- Turquoise — **S**.

You can change the name and color of the tag and the assigned hotkey. You can't change the list of colors because it's hardcoded in the editor's JS library for text highlighting.

#### Example of the JS code with tag descriptions

{% if locale == "en-com" %}
```javascript
var tagsData = [
  {
    'tag_color': 'Blue',
    'tag_name': 'Name',
    'tag_hotkey': 'q'
  },
  {
    'tag_color': 'Yellow',
    'tag_name': 'Brand',
    'tag_hotkey': 'w'
  },
  {
    'tag_color': 'Green',
    'tag_name': 'Volume',
    'tag_hotkey': 'e'
  },
  {
    'tag_color': 'Red',
    'tag_name': 'Error',
    'tag_hotkey': 'r'
  },
  {
    'tag_color': 'Gray',
    'tag_name': 'Manufacturer',
    'tag_hotkey': 't'
  },
  {
    'tag_color': 'Brown',
    'tag_name': 'Name',
    'tag_hotkey': 'y'
  },
  {
    'tag_color': 'Violet',
    'tag_name': 'Brand',
    'tag_hotkey': 'u'
  },
  {
    'tag_color': 'Orange',
    'tag_name': 'Volume',
    'tag_hotkey': 'i'
  },
  {
    'tag_color': 'Pink',
    'tag_name': 'Error',
    'tag_hotkey': 'a'
  },
  {
    'tag_color': 'Turquoise',
    'tag_name': 'Manufacturer',
    'tag_hotkey': 's'
  }
];

```
{% endif %}

## Input and output data {#data-platforms}

The editor's output fields need to be marked as optional because JS checks that at least one word is selected and has a tag. The Toloker can't submit a task that doesn't contain markup.

The editor uses:

- The `input` field with the <q>line</q> type where the markup text is substituted.
- The `result` field in the JSON format. It passes information about the task result.
- The `text_review_mode` is auxiliary. It is needed to display tags in the task review mode.

When you [mark up](../task_markup.md) control and training tasks in the Toloka interface, select all the output data fields. Otherwise, the words marked with tags won't be displayed in it.

{% note info %}

Don't change the input and output field names, otherwise the editor won't work.

{% endnote %}


## How do I work with the editor? {#how-to}

Use this information for the task instructions. Let the Tolokers understand everything at once:

- If you select a phrase, it is marked with an active tag.
- If the text belongs to a different category, click the arrow in the frame of the selected word or phrase and select a new tag from the list.
- You can remove selection by clicking the cross in the upper-right corner.

{% include [contact-support](../../_includes/contact-support-help.md) %}