# Input and output data

{% include [toloka-requester-source-html-editor-tb-spec](../_includes/toloka-requester-source/id-toloka-requester-source/html-editor-tb-spec.md) %}

In the **Specifications** field, you set parameters for [input and output data](../../glossary.md#input-output-data). These settings will be valid for all tasks in the [project](../../glossary.md#project).

In the specification, add fields for the data used in the task or for the data you need in the results. Reference these fields when you [configure the interface](spec.md).

Don't repeat the input data in the output data. You will receive all data, including the input, in the results.

## How to edit the specification {#manual-setting}

{% note info %}

Specification editing is available only when the **Define data specification manually** option is enabled.

{% endnote %}

There are two ways to edit the specification in project settings: using either regular mode or JSON mode. JSON mode gives you more options — you can hide input data and use regular expressions to validate output data.

{% list tabs %}

- Regular mode

  To add a field in the regular mode, click **Add field**.

  To edit an existing field, hover over the field and click ![](../_images/edit.svg).

- JSON mode

  To switch modes, click ![](../_images/code.svg). Examples of fields:

  #### Examples of fields:

  {% cut "Text in different formats" %}

  - String of a certain length

      ```json
      "my_string": {
        "type": "string",
        "required": true,
        "min_length": 10,
        "max_length": 100
      }
      ```

  - Only Latin letters and numbers

      ```json
      "my_en_string": {
        "type": "string",
        "required": true,
        "min_length": 10,
        "max_length": 100,
        "pattern": "[a-zA-Z0-9]+"
      }
      ```

  - Only Cyrillic letters and numbers

      ```json
      "my_ru_string": {
        "type": "string",
        "required": true,
        "min_length": 10,
        "max_length": 100,
        "pattern": "[а-яА-Я0-9]+"
      }
      ```

  - Letters and characters without numbers

      ```json
      "my_number_string": {
        "type": "string",
        "required": true,
        "min_length": 10,
        "max_length": 100,
        "pattern": "[^0-9]+"
      }
      ```

  - Link from a specific site

      ```json
      "my_url": {
        "type": "string",
        "required": true,
        "pattern": "(?:http(?:s)?:\\/\\/)?(?:[a-zA-z-]+(\\.)+)*(?:yandex\\.ru){1}(\\/|\\/[a-zA-Z-\\._~:/\\?#\\[\\]@!\\$&'\\(\\)\\*\\+,;=]+)?"
      }
      ```

  - Phone number with the `+`, `-` and space characters

      ```json
      "my_phone_string": {
        "type": "string",
        "required": true,
        "pattern": "\\+?[0-9\\s-]{4,}"
      }
      ```

  - Email with the `@`, `-` and `.` characters

      ```json
      "my_mail_string": {
        "type": "string",
        "required": true,
        "pattern": "[a-zA-Z]{1}[a-zA-Z0-9\\.\\-_]+@[a-zA-Z0-9\\.\\-_]+\\.[a-zA-Z]{2,}"
      }
      ```

  - Month

      ```json
      "my_month_string": {
        "type": "string",
        "required": true,
        "allowed_values": ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October" "November", "December"] }
      ```

  {% endcut %}

  {% cut "Link" %}

  ```json
  "my_url": {
    "type": "url",
    "required": true
  }
  ```

  {% endcut %}

  {% cut "Boolean" %}

  ```json
  "my_boolean": {
    "type": "boolean",
    "required": true
  }
  ```

  {% endcut %}

  {% cut "Numbers" %}

  - Integer from the specified range:

      ```json
      "my_integer": {
        "type": "integer",
        "required": true,
        "min_value": 1,
        "max_value": 100
      }
      ```

  - Integer with a list of allowed values:

      ```json
      "my_integer": {
        "type": "integer",
        "required": true,
        "allowed_values": [10, 20, 30]
      }
      ```

  - Fractional number:

      ```json
      "my_float": {
        "type": "float",
        "required": true,
        "min_value": 10.11,
        "max_value": 65.51
      }
      ```

  - A number with 0, 1, or 2 decimal places.

      To do this, choose the **string** type and use regular expression for validation. Note that the decimal separator is a comma:

      ```json
      "my_mail_string": {
        "type": "string",
        "required": true,
        "pattern": "^([0-9]+)(,([0-9]){1,2})?$"
      }
      ```

  {% endcut %}

  {% cut "File" %}

  ```json
  "my_file": {
    "type": "file",
    "required": true
  }
  ```

  {% endcut %}

  {% cut "Array of files" %}

  ```json
  "my_file_array": {
    "type": "array_file",
    "required": true,
    "max_size": 5
  }
  ```

  {% endcut %}

  {% cut "Coordinates" %}

  ```json
  "my_coordinates": {
    "type": "coordinates",
    "required": true
  }
  ```

  {% endcut %}

  {% cut "JSON" %}

  ```json
  "my_json": {
    "type": "json",
    "required": true
  }
  ```

  {% endcut %}

  {% cut "Hidden field" %}

  The string the Toloker can't access:

  ```json
  "my_string": {
    "type": "string",
    "hidden": true
  }
  ```

  {% endcut %}

{% endlist %}

{% cut "Explanations for configuring fields" %}

#|
|| Parameter  | Parameter in JSON | Overview ||
|| **Name** | `id` | Field ID. Only Latin letters, numbers, hyphens, and underscores are allowed. ||
|| **Type** | `type` | Data type:

- `string`
- `url`
- `boolean`
- `number`
- `float`
- `file`
- `coordinates`
- `json`

For arrays, add the `array_` prefix to the field type in JSON mode. For example: `array_file`. ||
|| **Required** | `required` | Whether the field must be filled when uploading the tasks for the input data.

Whether the Toloker's response is required in the output data.

By default, fields are optional — `false`.||
||**Hidden** | `hidden` | Allows you to hide data from the Toloker. If this is not done, Tolokers can get the field value programmatically. You can configure this parameter in JSON mode.

For example, you can hide the `assigment_id` identifier you will need when [reviewing assignments](../../glossary.md#assignment-review) in a separate project.

By default, the field is visible — `false`.

{% note warning %}

Hidden fields are not available in the task interface, even through JS or the template code in the constructor.

{% endnote %}||
|| **Array** | `array_<type>` | Array of objects of the same type. Used, for example, for multiple photos uploaded by a Toloker.
In JSON mode, there is a separate data type for the array. For example: `"type": "array_file"`.||
|| **Min size** | `min_size` | Minimum number of items in the array.||
|| **Max size** | `max_size` | Maximum number of items in the array.||
|| **Allowed values** | `allowed_values` | Allowed values for string, integer, float and boolean data types.||
|| **Min length** | `min_length` | Minimum length of the string.||
||**Max length** | `max_length` | Maximum length of the string.||
||**Min value** | `min_value` | Minimum values for float and integer numbers.||
||**Max value** | `max_value` | Maximum values for float and integer numbers.||
|| **Current location** | `current_location` | Saving the Toloker's current coordinates (`true`/`false`). Only for the `coordinates` data type. Used in tasks for the mobile app.

The default value is `false`.||
|| **Pattern** | `pattern` | Regular expression that the string must match. You can configure this parameter in JSON mode.||
|#

{% endcut %}

## Recommendations {#recomendations}

- If you edit a required field, the changes apply only to new task [pools](../../glossary.md#pool). For example, if you need to fix an error in a project, [clone the pool](pool-main.md) or [create a new one](pool-main.md). Existing task pools will continue using the previous version of the project.

- In the output, use value validation and don't forget to mark the field as required if the Toloker has to fill it in.
- Hidden fields are intended only for requesters and are not available in the task interface. The values of hidden fields can't be used either in the JS code or in the template constructor.

    Let's say you pass product data (like articles or batch numbers) that Tolokers don't need in order to complete the task. Or you are moderating comments and you need the authors' personal data in the results for further data processing, but the Tolokers shouldn't have access to personal data.

    To create a hidden field, add it to the specification yourself and then add the `"hidden": true` parameter to this field in JSON mode. You should do this in Toloka when configuring your project. The hidden field remains when the specification is re-generated using the Template Builder.

## What's next {#what_next}

- [Create a task pool in the project](pool-main.md).
- Learn more about how to set up a project:

    - [Writing instructions](instruction.md).
    - [Task interface](spec.md).
    - [Adapt a task for mobile devices](mobile.md).
    - [Setting up quality control](project-qa.md).

## See also {#see-also}

- [{#T}](edit-project.md)

## Troubleshooting {#troubleshooting}

{% include [faq-insert-function](../_includes/faq/project-settings/insert-function.md) %}

{% include [faq-add-mask](../_includes/faq/project-settings/add-mask.md) %}

{% include [faq-need-convert](../_includes/faq/project-settings/need-convert.md) %}

{% include [faq-output-data](../_includes/faq/project-settings/output-data.md) %}

{% include [faq-two-versions-text](../_includes/faq/adding-tasks-to-the-pool/two-versions-text.md) %}

{% include [contact-support](../_includes/contact-support.md) %}