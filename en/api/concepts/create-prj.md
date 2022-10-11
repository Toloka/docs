# Create a project

{% include [announce](../_includes/announce.md) %}

Creates a project.

{% note alert %}

You can send a maximum of 20 requests of this kind per minute and a maximum of 100 requests per day.

{% endnote %}

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/projects
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<project parameters>}
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/projects
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<project parameters>}
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
{
  "public_name": "Image classification",
  "public_description": "Look at the picture and determine the category of shoes",
  "public_instructions": "<div> In this task you will see images of different shoes.<br /><br />  You need to determine their category.<br /><br />  To complete the task faster, use the hotkeys 1, 2, 3, and arrows, if you are performing the task on a desktop computer or laptop.<br /><br />  How to complete the task: <ol><li>Look carefully at the image.</li><li>Click the <strong>Rotate</strong> button if you need to turn the picture, it can be on one side or upside down.</li><li>Choose one of the answer options. If the image doesn&#39;t correspond to any of the categories press <strong>Other</strong>.</li><li>Skip the tasks if the image doesn’t load or loads only partly.</li></ol> </div>",
  "task_spec": {
    "input_spec": {
      "image": {
        "type": "url",
        "required": true,
        "hidden": false
      }
    },
    "output_spec": {
      "result": {
        "type": "string",
        "required": true,
        "hidden": false,
        "allowed_values": [
          "boots",
          "sneakers",
          "other"
        ]
      }
    },
    "view_spec": {
      "type": "tb",
      "settings": {
        "showSubmit": true,
        "showSkip": true,
        "showFinish": true,
        "showTimer": true,
        "showTitle": true,
        "permissions": [],
        "showMessage": true,
        "showReward": true,
        "showFullscreen": true,
        "showInstructions": true
      },
      "config": {...},
      "inputExample": {
        "image": "https://labs-images-testing.s3.yandex.net/presets/for%20tb%20and%20dataset/leather-boots.jpg"
      },
      "lock": {
        "core": "1.13.1",
        "view.list": "1.2.0",
        "action.set": "1.0.8",
        "view.image": "1.4.0",
        "plugin.toloka": "1.1.8",
        "plugin.hotkeys": "1.3.0",
        "condition.required": "1.1.6",
        "field.button-radio-group": "1.3.1"
      },
      "localization_Config": {
        "keys": []
      }
    }
  },
  "assignments_issuing_type": "AUTOMATED"
}
```

#|
|| Parameter {#prj-param} | Overview ||
|| **public_name** {#public_name} | **string \| required**

Name of the project. It will be shown to Tolokers. ||
|| **public_description** {#public_description} | **string \| required**

Description of the project. It will be shown to Tolokers. ||
|| **task_spec** | **object \| required**

Parameters for input and output data and the task interface. ||
|| **task_spec.input_spec** | **object \| required**

The input data parameters for tasks. The complete list of parameters is shown in the [Input and output data](#in-out) table. ||
|| **task_spec.output_spec** | **object \| required**

Parameters for output data from the input fields. The complete list of parameters is shown in the [Input and output data](#in-out) table. ||
|| **task_spec.view_spec** | **object**

Description of the task interface. The complete list of parameters is shown in the [Task interface](#view-spec-section) table. ||
|| **assignments_issuing_view_ config** | **string \| required if**

Required if `assignments_issuing_type=MAP_SELECTOR`.

Settings for displaying field tasks. For a complete list of parameters, see [Settings for displaying field tasks](#assignments-issuing-view-config-section). ||
|| **public_instructions** {#public_instructions} | **string**

Instructions for completing the task. You can use any HTML markup in the instructions. ||
|| **private_comment** | **string**

Comments that are only visible to the requester. ||
|| **assignments_issuing_type** | **string**

How to assign tasks:

- `AUTOMATED` — The Toloker is assigned a task suite from the pool. You can [configure](create-pool.md#issue_task_suites_in_creation_order) the order for assigning task suites.

- `MAP_SELECTOR` — The Toloker selects a task suite on the map. If you are using `MAP_SELECTOR`, specify the text to display in the map name and description in the `assignments_issuing_view_config` key:

    ```json
      "assignments_issuing_view_config": {
        "title_template": "<task name>",
        "description_template": "<brief description of the task>",
        "map_provider": "YANDEX"
      }
    ```

The default value is `AUTOMATED`. ||
|| **assignments_issuing_view_config.map_provider** | **string**

This parameter is available when the project has `"assignments_issuing_type": "MAP_SELECTOR"`.

Map provider for tasks:

- `GOOGLE` — Google Maps.
- `YANDEX` — Yandex Maps.

If the parameter is not set, then the Toloker selects the map. ||
|| **assignments_automerge_ enabled** | **boolean**

Resolve [merging identical tasks](tasks.md#task-merge) in the project. The default value is `false`. ||
|| **max_active_assignments_ count** | **integer**

The number of task suites the Toloker can complete simultaneously ("Active" status). ||
|| **quality_control** | **object**

The quality control rule. ||
|| **quality_control.configs[]** | **array of objects**

[Presets](quality_control.md) ||
|| **localization_config** | **object**

Block of translations to other languages. The complete list of parameters is shown in the [Translations to other languages](#localization-config-section) table.

For more information about translation, see [Translations to other languages](https://toloka.ai/docs/guide/concepts/project-languages.html). ||
|#

## Input and output data (input_spec and output_spec) {#in-out}

The `input_spec` and `output_spec` parameters contain JSON with the input data properties and response validation parameters. Use them to define the data type (string, integer, URL, and so on) and specify validation parameters (such as the string length).

#|
|| Parameter | Overview ||
|| **\<ID\>** | **object \| required**

- For input data,  the ID of the object to display in the task, and its properties.
- For output data, the ID of the response input field and response validation parameters. ||
|| **type** | **string \| required**

Data type:

- `url` — URL of an image, page, and so on.
- `boolean` — Boolean data type (`true`/`false`).
- `integer` — Integer.
- `string` — String.
- `float` — Floating-point number.
- `json` — JSON object.
- `file` — File (only for output data).
- `coordinates` — Geographical coordinates, such as "53.910236, 27.531110"). ||
|| **required** | **boolean**

Whether the object or input field is required. The default value is `true`. ||
|| **hidden** | **boolean**

Whether to hide field with the input value from the Toloker or not. The default value is `false`.

For output data, always `false`. ||
|| **min_value** | **float**

Minimum value of the number. ||
|| **max_value** | **float**

Maximum value of the number. ||
|| **allowed_values[]** | **array of strings, array of integers, array of floats**

Allowed values.

Setting acceptable values improves the quality of [response aggregation](aggregated-solutions.md). ||
|| **min_length** | **integer**

Minimum length of the string. ||
|| **max_length** | **integer**

Maximum length of the string. ||
|| **current_location** | **string**

Only for output data of the `coordinates` type: populate the field with the Toloker's current coordinates in the field (`true`/`false`). Used in tasks for the mobile app. ||
|#

## Task interface (view_spec) {#view-spec-section}

#|
|| Parameter | Overview ||
|| **markup** | **string**

For more information, see the [Requester's guide](https://toloka.ai/docs/guide/). ||
|| **script** | **string**

JavaScript interface for the task.

For more information, see the [Requester's guide](https://toloka.ai/docs/guide/). ||
|| **styles** | **string**

CSS task interface.

For more information, see the [Requester's guide](https://toloka.ai/docs/guide/). ||
|| **settings** | **object \| required**

Whether to display standard UI elements in the task. ||
||**config[]** | **array of objects**

[Configuration for Template Builder](tb-config.md) ||
|| **assets** | **object**

Linked files:

- CSS styles
- JavaScript libraries
- Toloka assets with the `$TOLOKA_ASSETS` prefix.
Add items in the order they should be linked when running the task interface. ||
|| **assets.script_urls[]** | **array of strings**

Links to JavaScript libraries and Toloka assets.

Toloka assets:

- `$TOLOKA_ASSETS/js/toloka-handlebars-templates.js` — Handlebars (see the [description on the template engine website](http://handlebarsjs.com/)).
- `$TOLOKA_ASSETS/js/image-annotation.js` — Image labeling interface (see  [Image with area selection](https://toloka.ai/docs/guide/concepts/t-components/image-annotation.html/) in the Requester's guide).

Note that the image labeling interface should only be connected together with the Handlebars helpers. The order of connection matters:

```json
  "script_urls": ["$TOLOKA_ASSETS/js/toloka-handlebars-templates.js",
  "$TOLOKA_ASSETS/js/image-annotation.js"]
```
||
|| **assets.style_urls[]** | **array of strings**

Links to CSS libraries. ||
|| **type** | **string**

Editor type:

- `tb` — Template Builder. ||
|| **localizationConfig** | **object**

Editor configuration.

In the Template Builder, add to this field the keys for the properties of text components that you need to translate into other languages.

For more information, see [Translating the task interface](https://toloka.ai/docs/guide/concepts/project-languages.html#project-languages__interface-translate). ||
|| **localizationConfig.keys** | **string**

Keys in the source language.

```json
  "key": "<key name>",
  "defaultValue": "<source text>"
```

For more information, see [Translating the task interface](https://toloka.ai/docs/guide/concepts/project-languages.html#project-languages__interface-translate). ||
|| **settings.showTimer** | **boolean**

Show the timer. The default value is `true`. ||
|| **settings.showTitle** | **boolean**

Show the project name in task titles. The default value is `true`. ||
|| **settings.showInstructions** | **boolean**

Show the **Instructions** button. The default value is `true`. ||
|| **settings.showFullscreen** | **boolean**

Show the **Expand to fullscreen** button. The default value is `true`. ||
|| **settings.showSubmit** | **boolean**

Show the **Next** button. The default value is `true`. ||
|| **settings.showSkip** | **boolean**

Show the **Skip** button. The default value is `true`. ||
|| **settings.showFinish** | **boolean**

Show the **Back to main page** button. The default value is `true`. ||
|| **settings.showMessage** | **boolean**

Show the **Message for the requester** button. The default value is `true`. ||
|| **settings.showReward** | **boolean**

Show the price per task suite. The default value is `true`. ||
|#

## Settings for displaying field tasks (assignments_issuing_view_ config) {#assignments-issuing-view-config-section}

#|
|| Parameter | Overview ||
|| **title_template** | **string \| required if**

Required if `assignments_issuing_type=MAP_SELECTOR`.

Name of the task. Tolokers will see it in the task preview. ||
|| **description_template** | **string \| required if**

Required if `assignments_issuing_type=MAP_SELECTOR`.

A description of the task. Tolokers will see it in the task preview. ||
|| **map_provider** | **string**

This parameter is available when the project has `"assignments_issuing_type": "MAP_SELECTOR"`.

Map provider for tasks:

- `GOOGLE` — Google Maps.
- `YANDEX` — Yandex Maps.

If the parameter is not set, then the Toloker selects the map. ||
|#

## Translations to other languages (localization_config) {#localization-config-section}

#|
|| Parameter | Overview ||
|| **default_ language** | **string**

The source language used in the fields [public_name](#public_name), [public_description](#public_description), and [public_instructions](#public_instructions). ||
|| **additional_languages[]** | **array of objects**

Array of target languages. ||
|| **additional_languages[]. language** | **string**

Target language. ||
|| **additional_languages[]. public_name** | **object**

Translation of the project name.

```json
  "value": "<target text>",
  "source": "<source text>"
```

Translation source:

- `REQUESTER` — The requester set the value themselves. ||
|| **additional_languages[]. public_description** | **object**

Translation of the project description.

```json
  "value": "<target text>",
  "source": "<source text>"
```

Translation source:

- `REQUESTER` — The requester set the value themselves. ||
|| **additional_languages[]. public_instructions** | **object**

Translation of instructions for completing tasks.

```json
  "value": "<target text>",
  "source": "<source text>"
```

Translation source:

- `REQUESTER` — The requester set the value themselves. ||
|| **additional_languages[]. tb_view_spec** | **object**

Translating the task interface. ||
|| **additional_languages[]. tb_view_spec.keys[]** | **array of objects**

Keys with the translation of the task interface elements.

```json
  "key": "<key name>",
  "value": "<target text>",
  "source": "<source text>"
```

Translation source:

- `REQUESTER` — The requester set the value themselves.
||
|#

## Response {#response}

Contains information about the uploaded project in JSON format. The project is automatically assigned an ID.

It includes:

- [Parameters that are used when creating a project](#prj-param).
- Parameters that are assigned automatically.

#|
|| Parameter | Overview ||
|| **owner** | **object**

Parameters of the requester that created the project ||
|| **owner.id** | **string**

Parameters to sort by: ||
|| **owner.myself** | **boolean**

Checks who the object belongs to:

- `true` — The user whose OAuth token is specified in the request.
- `false` — Another account (employee or owner).
{% if audience == "internal" %}**owner.company_id** | **string**

The requester's company ID.{% endif %} ||
|| **id** | **string**

Project ID (assigned automatically). ||
|| **status** | **string**

Status of the project:

- `ACTIVE` — Active.
- `ARCHIVED` — Archived. ||
|| **created** | **string**

The UTC date and time the project was created, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|#