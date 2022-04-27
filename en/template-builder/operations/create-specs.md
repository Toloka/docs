# Creating specifications

A Toloka project must include specifications for
{% cut "input and output data" %}

_Input data_ is the source data you want to display or use. For example, links to images that will be shown to performers. Use the `data.input` component to access the input data.

_Output_ is the data you receive after the task is completed, like the performer's answers to your questions. Use the `data.output` component to access the output data.

See the [Read and write](input-output-data.md) instructions to learn about working with data.

{% endcut %}

. If you use Template Builder in the Toloka interface, the specification is created automatically.

{% note warning %}

Creating a specification is in test mode, so double check the results. If you have any problems, please contact [support](../concepts/support.md).

{% endnote %}

## Filling in input data {#input-data-create}

Input data fields are created from the code on the **Example of input data** tab. Provide a detailed example to get a ready-to-use specification. If you have optional fields, include them also.

**Examples:**
#### String

In this example, the `question` field with the **string** type will be created in the specification.

```json
{
  "question": "Do you like dogs?"
}
```

#### true/false

In this example, the `verdict` field with the **boolean** type will be created in the specification.

```json
{
  "verdict": true
}
```

#### Number

In this example, the `age` field with the **number** type will be created in the specification.

```json
{
  "age": 42
}
```

#### JSON

In this example, the `registration_address` field with the **JSON** type will be created in the specification.

```json
{
    ...
    "registration_address": {
        "country": "Russia",
        "city": "Moscow",
        "address": "Tverskaya str, 3-53"
    }
}
```

#### Array

In this example, the `images` field with the **array** type will be created in the specification.

```json
{
  "images": [
    "https://cdn.stocksnap.io/img-thumbs/960w/surfer-wave_3DBOYBPB3X.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/fisherman-silhouette_UADULRRHEK.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/old-photo_GEQ27OWZVV.jpg"
  ]
}
```

{% note info %}

By default, all the input data fields are marked as required in the specification. To make the field optional, in the [data.input](work-with-data.md) configuration component specify the `default` property.

{% endnote %}


## Filling in output data {#output-data-create}

The output data fields depend on the components that use `data.output` and values supported by it.

**Examples:**

#### true/false

In this example, the specification will contain the `verdict` field with the **boolean** type.

```json
{
  "type": "field.radio-group",
  "options": [
    {
      "label": "Yes",
      "value": true
    },
    {
      "label": "No",
      "value": false
    }
  ],
  "data": {
    "type": "data.output",
    "path": "verdict"
  }
}
```

#### String

In this example, the specification will contain the `verdict` field with the **string** type and the acceptable values "true" and "false".

```json
{
  "type": "field.radio-group",
  "options": [
    {
      "label": "Yes",
      "value": "true"
    },
    {
      "label": "No",
      "value": "false"
    }
  ],
  "data": {
    "type": "data.output",
    "path": "verdict"
  }
}
```

#### Number

In this example, the specification will contain the `verdict` field with the **number** type and acceptable values `0` and `1`.

```json
{
  "type": "field.radio-group",
  "options": [
    {
      "label": "Yes",
      "value": 1
    },
    {
      "label": "No",
      "value": 0
    }
  ],
  "data": {
    "type": "data.output",
    "path": "verdict"
  }
}
```

#### JSON

In this example, the specification will contain the `results` field with the **JSON** type. The `results` field will have the JSON object `{ "verdict": true }` or `{ "verdict": false }`.

```json
{
  "type": "field.radio-group",
  "options": [
    {
      "label": "Yes",
      "value": true
    },
    {
      "label": "No",
      "value": false
    }
  ],
  "data": {
    "type": "data.output",
    "path": "results.verdict"
  }
}
```

#### Array

In this example, the specification will contain the `images` field with the **array** type.

```json
{
  "type": "field.radio-group",
  "options": [
    {
      "label": "Yes",
      "value": 1
    },
    {
      "label": "No",
      "value": 0
    }
  ],
  "data": {
    "type": "data.output",
    "path": "verdicts.0"
  }
}
```

{% note info %}

If there are different types of values in the output, the **JSON** type will be included in the specification.

{% endnote %}


## How to edit the specification {#manual-setting}

There are two ways to edit a specification in project settings: you can do it either in regular mode or in JSON mode. JSON mode gives you more options — you can hide input data and use regular expressions to validate output data.

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
    "my_ru_string": {    "type": "string",    "required": true,    "min_length": 10,    "max_length": 100,     "pattern": "[а-яА-Я0-9]+" }
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

- Month
    ```json
    "my_month_string": {     "type": "string",    "required": true,    "allowed_values": ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October" "November", "December"] }
    ```


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
The string the performer can't access:
```json
"my_string": {
    "type": "string",
    "hidden": true
}
```

#### Explanations for configuring fields
**Parameter in JSON:** `id`

**
Overview
:**
Field ID. Only Latin letters, numbers, hyphens, and underscores are allowed.


**Parameter in JSON:** `type`

**
Overview
:**
Data type:

- `string`

- `url`

- `boolean`

- `number`

- `float`

- `file`
- `coordinates`

- `json`


For arrays, add the `array_` prefix to the field type in JSON mode. For example: `array_file`.


**Parameter in JSON:** `required`

**
Overview
:**
Whether the field must be filled when uploading the tasks for the input data.

Whether the performer's response is required in the output data.

By default, fields are optional — `false`.


**Parameter in JSON:** `hidden`

**
Overview
:**
Allows you to hide data from the performer. If this is not done, performers can get the field value programmatically. You can configure this parameter in JSON mode.

For example, you can hide the `assigment_id` identifier you will need when
{% cut "reviewing assignments" %}

A
{% cut "pool" %}

A set of paid tasks sent out for completion at the same time.

{% endcut %}

 setting that allows you to check responses so you don't have to pay for poorly completed tasks.

{% endcut %}

 in a separate project.

By default, the field is visible — `false`.

{% note warning %}

Hidden fields are not available in the task interface, even through JS or the template code in the constructor.

{% endnote %}



**Parameter in JSON:** `array_<type>`

**
Overview
:** Array of objects of the same type. Used, for example, for multiple photos uploaded by a performer.
In JSON mode, there is a separate data type for the array. For example: `"type": "array_file"`.


**Parameter in JSON:** `min_size`

**
Overview
:** Minimum number of items in the array.

**Parameter in JSON:** `max_size`

**
Overview
:** Maximum number of items in the array.

**Parameter in JSON:** `allowed_values`

**
Overview
:**
Allowed values for string, integer, float and boolean data types.


**Parameter in JSON:** `min_length`

**
Overview
:**
Minimum length of the string.


**Parameter in JSON:** `max_length`

**
Overview
:** Maximum length of the string.

**Parameter in JSON:** `min_value`

**
Overview
:** Minimum values for float and integer numbers.

**Parameter in JSON:** `max_value`

**
Overview
:** Maximum values for float and integer numbers.

**Parameter in JSON:**
`current_location`


**
Overview
:**
Saving the performer's current coordinates (`true`/`false`). Only for the `coordinates` data type. Used in tasks for the mobile app.

The default value is `false`.


**Parameter in JSON:** `pattern`

**
Overview
:**
Regular expression that the string must match. You can configure this parameter in JSON mode.

## Recommendations {#recomendations}

- If you edit a required field, the changes apply only to new task
    {% cut "pools" %}

    A set of paid tasks sent out for completion at the same time.

    {% endcut %}

    . For example, if you need to fix an error in a project, [clone the pool](https://toloka.ai/docs/guide/concepts/pool-main.html) or [create a new one](https://toloka.ai/docs/guide/concepts/pool-main.html). Existing task pools will continue using the previous version of the project.

- In the output, use value validation and don't forget to mark the field as required if the performer has to fill it in.
- Hidden fields are intended only for requesters and are not available in the task interface. The values of hidden fields can't be used either in the JS code or in the template constructor.

    Let's say you pass product data (like articles or batch numbers) that performers don't need in order to complete the task. Or you are moderating comments and you need the authors' personal data in the results for further data processing, but the performers shouldn't have access to personal data.

    To create a hidden field, add it to the specification yourself and then add the `"hidden": true` parameter to this field in JSON mode. You should do this in Toloka when configuring your project. The hidden field remains when the specification is re-generated using the Template Builder.


## What's next {#what-next}

- [See examples of data read and write](input-output-data.md).
- [Learn how to clear the entered data](clear-data.md).


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
