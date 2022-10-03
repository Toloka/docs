# Input and output data

{% include [toloka-requester-source-html-editor-tb-spec](../_includes/toloka-requester-source/id-toloka-requester-source/html-editor-tb-spec.md) %}


In the **Specifications** field, you set parameters for [input and output data](../../glossary.md#input-output-data-ru). These settings will be valid for all tasks in the [project](../../glossary.md#project-ru).

In the specification, add fields for the data used in the task or for the data you need in the results. Reference these fields when you [configure the interface](spec.md).

Don't repeat the input data in the output data. You will receive all data, including the input, in the results.

## How to edit the specification {#manual-setting}

{% note info %}

Specification editing is available only when the {% if locale == "ru-ru" %}**Define data specification manually**{% endif %}{% if locale == "en-com" %}**Define data specification manually**{% endif %} option is enabled.

{% endnote %}


There are two ways to edit the specification in project settings: using either regular mode or JSON mode. JSON mode gives you more options — you can hide input data and use regular expressions to validate output data.

#### Regular mode

To add a field in the regular mode, click **Add field**.

To edit an existing field, hover over the field and click ![](../_images/edit.svg).

#### JSON mode

To switch modes, click ![](../_images/code.svg). Examples of fields:

#### Examples of fields:

#### Text in different formats

- String of a certain length

    ```json
    "my_string": {
    "type": "string",
    "required": true,
    "min_length": 10,
    "max_length": 100
    }
    ```


- Only Russian letters and numbers
    ```json
    "my_ru_string": {
    "type": "string",
    "required": true,
    "min_length": 10,
    "max_length": 100,
    "pattern": "[а-яА-Я0-9]+"
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

- Month{% if locale == "ru-ru" %}
    ```json
    "my_month_string": {
    "type": "string",
    "required": true,
    "allowed_values": ["январь", "февраль", "март", "апрель", "май", "июнь", "июль", "август", "сентябрь", "октябрь" "ноябрь", "декабрь"]
    }
    ```
    {% endif %}{% if locale == "en-com" %}
    ```json
    "my_month_string": {
    "type": "string",
    "required": true,
    "allowed_values": ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October" "November", "December"] }
    ```
    {% endif %}

#### Link

```json
"my_url": {
    "type": "url",
    "required": true
}
```

#### Boolean

```json
"my_boolean": {
    "type": "boolean",
    "required": true
}
```

#### Numbers

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


#### File

```json
"my_file": {
    "type": "file",
    "required": true
}
```

#### Array of files

```json
"my_file_array": {
    "type": "array_file",
    "required": true,
    "max_size": 5
}
```

#### Coordinates

```json
"my_coordinates": {
    "type": "coordinates",
    "required": true
}
```

#### JSON

```json
"my_json": {
    "type": "json",
    "required": true
}
```

#### Hidden field
The string the Toloker can't access:
```json
"my_string": {
    "type": "string",
    "hidden": true
}
```

#### Explanations for configuring fields


Parameter
 | Parameter in JSON |
Overview

----- | ----- | -----
{% if locale == "ru-ru" %}**Name**{% endif %}{% if locale == "en-com" %}**Name**{% endif %} | `id` | Field ID. Only Latin letters, numbers, hyphens, and underscores are allowed.
{% if locale == "ru-ru" %}**Type**{% endif %}{% if locale == "en-com" %}**Type**{% endif %} | `type` | Data type:<br/><br/>- `string`<br/>    <br/>- `url`<br/>    <br/>- `boolean`<br/>    <br/>- `number`<br/>    <br/>- `float`<br/>    <br/>- `file`<br/>- `coordinates`<br/>    <br/>- `json`<br/>    <br/><br/>For arrays, add the `array_` prefix to the field type in JSON mode. For example: `array_file`.
{% if locale == "ru-ru" %}**Required**{% endif %}{% if locale == "en-com" %}**Required**{% endif %} | `required` | Whether the field must be filled when uploading the tasks for the input data.<br/><br/>Whether the Toloker's response is required in the output data.<br/><br/>By default, fields are optional — `false`.
{% if locale == "ru-ru" %}**Hidden**{% endif %}{% if locale == "en-com" %}**Hidden**{% endif %} | `hidden` | Allows you to hide data from the Toloker. If this is not done, Tolokers can get the field value programmatically. You can configure this parameter in JSON mode.<br/><br/>For example, you can hide the `assigment_id` identifier you will need when [reviewing assignments](../../glossary.md#left-off-acceptance-ru) in a separate project.<br/><br/>By default, the field is visible — `false`.<br/><br/>{% note warning %}<br/><br/>Hidden fields are not available in the task interface, even through JS or the template code in the constructor.<br/><br/>{% endnote %}
{% if locale == "ru-ru" %}**Array**{% endif %} {% if locale == "en-com" %}**Array**{% endif %} | `array_<type>` | Array of objects of the same type. Used, for example, for multiple photos uploaded by a Toloker.<br/>In JSON mode, there is a separate data type for the array. For example: `"type": "array_file"`.
{% if locale == "ru-ru" %}**Min size**{% endif %}{% if locale == "en-com" %}**Min size**{% endif %} | `min_size` | Minimum number of items in the array.
{% if locale == "ru-ru" %}**Max size**{% endif %} {% if locale == "en-com" %}**Max size**{% endif %} | `max_size` | Maximum number of items in the array.
{% if locale == "ru-ru" %}**Allowed values**{% endif %}{% if locale == "en-com" %}**Allowed values**{% endif %} | `allowed_values` | Allowed values for string, integer, float and boolean data types.
{% if locale == "ru-ru" %}**Min length**{% endif %}{% if locale == "en-com" %}**Min length**{% endif %} | `min_length` | Minimum length of the string.
{% if locale == "ru-ru" %}**Max length**{% endif %}{% if locale == "en-com" %}**Max length**{% endif %} | `max_length` | Maximum length of the string.
{% if locale == "ru-ru" %}**Min value**{% endif %}{% if locale == "en-com" %}**Min value**{% endif %} | `min_value` | Minimum values for float and integer numbers.
{% if locale == "ru-ru" %}**Max value**{% endif %}{% if locale == "en-com" %}**Max value**{% endif %} | `max_value` | Maximum values for float and integer numbers.
{% if locale == "ru-ru" %}**Current location**{% endif %} {% if locale == "en-com" %}**Current location**{% endif %} | `current_location` | Saving the Toloker's current coordinates (`true`/`false`). Only for the `coordinates` data type. Used in tasks for the mobile app.<br/><br/>The default value is `false`.
{% if locale == "ru-ru" %}**Pattern**{% endif %} {% if locale == "en-com" %}**Pattern**{% endif %} | `pattern` | Regular expression that the string must match. You can configure this parameter in JSON mode.

## Recommendations {#recomendations}

- If you edit a required field, the changes apply only to new task [pools](../../glossary.md#pool-ru). For example, if you need to fix an error in a project, [clone the pool](pool-main.md) or [create a new one](pool-main.md). Existing task pools will continue using the previous version of the project.

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
    - {% if locale == "ru-ru" %}
    - [Toloka blog post.]({{ toloka-blog-edit-templates }})
    - {% endif %}



## Troubleshooting {#troubleshooting}

#### How do I insert a function that is called by an image click in my task?

You can find an example of the task template for selecting image groups at this [link]({{ selection-of-images-groups }}). The input and output data, as well as a fragment of the instructions, are in the comments to the project.

#### How do I add a mask for the input field, like dd.mm.yyyy for the date field or numbers only (10 or 12) for INN (Taxpayer Identification Number)?

To validate the input data format, you can use the output field type, specifying the acceptable or minimum/maximum values. For example, create an output field for the taxpayer number with the “string” type and enter its minimum and maximum length (like 10 and 12). To use a more sophisticated validation in the template, use RegExp.

To enter a date, you can add a calendar to the task interface. See an [example of a calendar]({{ how-to-insert-a-calendar }}).

#### Do I need to convert all the images in the task to the same size or can they be different?
You can use different image sizes.
#### If a project's output data may include any number from 1 to 999999, can I specify a range?

You can't use a range as a fixed value.

#### How do I show two different versions of the text to Tolokers?

If you pass texts to the input data, you can upload 2 different tasks to the pool: pass Text 1 in the `INPUT: <input field name>` field of Task 1. In Task 2, use this field to pass Text 2.

If the text is in the HTML block of the task template, then clone the project. To limit a Toloker to doing only one task in your project, use the [Submitted responses](submitted-answers.md) rule. You can assign a skill or ban the Toloker after they submit one response.


{% include [contact-support](../_includes/contact-support-help.md) %}
