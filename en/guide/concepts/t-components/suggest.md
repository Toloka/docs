# String input with suggest list

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder](../../../template-builder/index.md).

{% endnote %}

Contains text suggestions that are displayed when the Toloker points the cursor at the input field. There are two types of text suggestions:

- Universal suggestions used in all tasks.

- Individual suggestions for different tasks.

{% list tabs %}

- Universal suggestions

  1. Set the array of suggestion strings in the **JS code** (`getTemplateData` method) to include it in the [project's](../../../glossary.md#project)[input data](../../../glossary.md#input-output-data) set:

      {% cut "Example 1" %}

      {% if locale == "en-com" %}

      ```javascript
      exports.Task = extend(TolokaHandlebarsTask, function (options) {
      TolokaHandlebarsTask.call(this, options);
      }, {
      getTemplateData: function() {
      var data = TolokaHandlebarsTask.prototype.getTemplateData.apply(this, arguments);
      data. < array name > = ['string 1', 'string 2', ...
      'string n'
      ];
      return data;
      },
      OnRender: function () {
      //Generated DOM element for the task (available via #getDOMElement())
      },
      onDestroy: function () {
      //The task is completed, you can release global resources (if you used them) }
      });

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
      ```

      {% endif %}

      {% endcut %}

      {% cut "Example 2" %}

      {% if locale == "en-com" %}

      ```javascript
      exports.Task = extend(TolokaHandlebarsTask, function (options) {
      TolokaHandlebarsTask.call(this, options);
      }, {
      getTemplateData: function() {
      var data = TolokaHandlebarsTask.prototype.getTemplateData.apply(this, arguments);
      data.countries = ['Poland', 'Lithuania', 'Russia', 'Belarus', 'Latvia', 'Germany', 'France'];
      return data;
      },
      OnRender: function () {
      //Generated DOM element for the task (available via #getDOMElement())
      },
      onDestroy: function () {
      //The task is completed, you can release global resources (if you used them) }
      });

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
      ```

      {% endif %}

     {% endcut %}

  1. Add the `{{field type="suggest" name="<output field name>" source=<array name>}}` component to the **HTML** code. Example:

      ```plaintext
      {{field type="suggest" name="result" source=countries allowCustomInput=true}}
      ```

- Individual suggestions

  1. Add the `{{field type="suggest" name="<output field name>" source=<input field name>}}` component to the **HTML** code. Example:

      ```plaintext
      {{field type="suggest" name="result" source=countries allowCustomInput=true}}
      ```

  1. Add a field of array string type in the description of input data. Example:

      ```json
      {
      "counries": {
      "type": "array_string",
      "required": true
      }
      }
      ```

  1. [Escape](../pool_csv.md#json) the data and add it to the [file with tasks](../../../glossary.md#tsv).

      {% cut "Example" %}

      ![](../../_images/location-job/pool_csv/main_tsv2.png)

      {% endcut %}

{% endlist %}

#### Parameters

#|
||**Parameter**|**Description**|**Required**|**Default value**||
||`type`| Field type: `suggest` — String input field with suggestions. | yes | no||
||`name`| Attribute for the output data field. Contains the output field name. | yes | no||
||`source`| Name of array with suggested strings. For example: `source=countries`. The array is defined in the JS-code of the project ( `getTemplateData` method). | yes | no||
||`allowCustomInput`| Whether the Toloker can ignore suggestions and enter their own string. | no | `false`||
||`validation-show`| The position of popup hints (displayed if the response didn't pass validation). The position is relative to the input field.

Supported values:

- Above the input field: `"top-left"`, `"top-center"`, `"top-right"`.

- Below the input field: `"bottom-left"`, `"bottom-center"`, `"bottom-right"`.

- To the left of the input field: `"left-top"`, `"left-center"`, `"left-bottom"`.

- To the right of the input field: `"right-top"`, `"right-center"`, `"right-bottom"`.

- Don't display the message (`"false"`). | no | `"top-left"`||
||`placeholder`| The text to display in the empty field.

{% note info %}

If `value` is set, the input field shows `value` instead of `placeholder`.

{% endnote %}

| no | no||
||`hotkey`| Shortcut for setting focus on the field. | no | no||
||`value`| The value to write in responses if the Toloker didn't fill in the field.

{% note info %}

`Value` is displayed in the empty field instead of `placeholder`.

{% endnote %}

| no | no||
||`class`| The CSS class for the field. For example: `class="mytask_field"`. | no | `".field" ".field_type_suggest"`||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}