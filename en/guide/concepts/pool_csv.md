# Creating a file with tasks

Tasks are uploaded to the [pool](pool-main.md) in [the tasks file](../../glossary.md#tsv).

Download the file template for your [project](../../glossary.md#project) on the [pool](../../glossary.md#pool) page. Use the template to create your own task file and upload it to the pool.

{% cut "Use sample data" %}

If you want to see what your project will look like after the launch, but you don't have any labeling tasks yet, you can upload ready-made sample data to the pool. Sample data is available for templates:

- **Image classification**
- **Product search relevance**
- **Object recognition & detection**
- **Clickbait or not?**

Click **Use sample data** next to **Attach the prepared file with data**. This lets you avoid any additional actions with files.

Once you've finished working with the sample data and everything looks good, prepare your data and upload it to the pool.

{% endcut %}

If you need to add different task types to the pool, upload multiple files, one for each task type.

## Tasks file structure {#structure}

{% list tabs %}

- TSV/XLSX 

  The first line of the file contains the column headers:

  - `INPUT:<name of the input data field>` — input data for tasks.

  - `GOLDEN:<name of the output data field>` — responses for [control tasks](../../glossary.md#control-task).

  - `HINT:text` — hints for [training tasks](../../glossary.md#training-task). The Toloker will see the hint text at the top of the task (on a red background) if their response to the control task is different from the correct one.

  - Point coordinates for [field tasks](../tutorials/walk.md):

      - `Al:latitude` — latitude.

      - `Al:longitude` — longitude.

  Task type depends on which fields are filled in.

  {% cut "General task" %}

    To create a [general task](../../glossary.md#general-task), fill in the columns with the `INPUT` header.

    {% cut "Example with a simple object (string, link, and so on)" %}

    ![](../_images/location-job/pool_csv/main_tsv.png)

    {% endcut %}

    {% cut "Example with a string array" %}

    ![](../_images/location-job/pool_csv/main_tsv2.png)

    {% endcut %}

  {% endcut %}

  {% cut "Control task" %}

    To create a control task, add:

    - The task input data in the columns with the `INPUT` header.

    - Correct responses in the columns with the `GOLDEN` header.

    {% note tip %}

    You can also add responses when creating a pool in [task markup mode](task_markup.md) (you need to use [“smart mixing”](distribute-tasks-by-pages.md#smart-mixing) when uploading tasks).

    {% endnote %}

    {% cut "Example" %}

    ![](../_images/location-job/pool_csv/controls_tsv.png)

    {% endcut %}

  {% endcut %}

  {% cut "Training task" %}

    To create a training task, add:

    - The task input data in the columns with the `INPUT` header.

    - Correct responses in the columns with the `GOLDEN` header.

    - A hint in the `HINT:text` column.

    For training tasks, it is convenient to create a [separate pool](train.md).

    {% note info %}

    You can also add responses and hints when creating a pool in [task markup mode](task_markup.md) (you need to use ["smart mixing"](distribute-tasks-by-pages.md#smart-mixing) when uploading tasks).

    {% endnote %}

    {% cut "Example" %}

    ![](../_images/location-job/pool_csv/cats_tsv.png)

    {% endcut %}

  {% endcut %}

  {% cut "Field task" %}

    The task that the Toloker chooses on the map in the Toloka mobile app.

    To create a field task, add:

    - The task input data in the columns with the `INPUT` header.

    - Coordinates in the `Al:latitude` and `Al:longitude` columns.

    {% cut "Example" %}

    ![](../_images/tutorials/walk/squirrel_tsv.png)

    {% endcut %}

    {% include [toloka-requester-source-field-tasks-suites](../_includes/toloka-requester-source/id-toloka-requester-source/field-tasks-suites.md) %}

  {% endcut %}

  The columns with [required input data fields](incoming.md) must be filled. The other columns can be deleted if they are empty.

- JSON

  {% note alert %}

  Check the format of the file with tasks. If the format of your file is old, download the template on the pool page and replace the sample data in it with your own data.

  {% endnote %}

  The file is a JSON object which contains:

  - `input_values` — input data for tasks.

  - `known_solutions` — responses for control tasks.

  - `message_on_unknown_solution` — hints for training tasks. The Toloker will see the hint text at the top of the task (on a red background) if their response to the control task is different from the correct one.

  - Point coordinates for field tasks:

      - `latitude` — latitude.

      - `longitude` — longitude.

  {% cut "General task" %}

  To create a [general task](../../glossary.md#general-task), specify the names and the values of the input fields in the `input_values` object.

  {% cut "Example" %}

  ```json
  [
    {
      "input_values": {
       "image_url": "https://www.example.com/image1.png"
      }
    },
    {
      "input_values": {
       "image_url": "https://www.example.com/image2.png"
      }
    },
    {
      "input_values": {
       "image_url": "https://www.example.com/image3.png"
      }
    }
  ]
  ```

  #|
  || Key | Description ||
  || **input_values** | **object**

  Input data for a task. List of pairs:

  ```json
    "<ID of field 1>": "<value of field 1>",
    "<ID of field 2>": "<value of field 2>",
    ...
    "<ID of field N>": "<value of field N>"
  ```
  ||
  |#

  {% endcut %}

  {% endcut %}

  {% cut "Control task" %}

  To create a control task, specify:

  - The names and the values of the input fields in the `input_values` object.

  - Correct responses in the `known_solutions` object.

  {% cut "Example" %}

  ```json
  {
    "input_values": {
      "image_url": "https://www.example.com/image1.png"
    },
    "known_solutions": [
      {
        "output_values": {
          "result": "OK",
          "like": false
        }
      }
    ]
  }
  ```

  #|
  || Key | Description ||
  || **input_values** | **object**

  Input data for a task. List of pairs:

  ```json
    "<ID of field 1>": "<value of field 1>",
    "<ID of field 2>": "<value of field 2>",
    ...
    "<ID of field N>": "<value of field N>"
  ```
  ||
  || **known_solutions[].output_values** | **object**

  Output data values to check. You should specify values for all required output data fields.

  ```json
    "<ID of field 1>": "<correct response>",
    "<ID of field 2>": "<correct response>",
    ...
    "<ID of field N>": "<correct response>"
  ```
  ||
  |#

  {% endcut %}

  {% endcut %}

  {% cut "Training task" %}

  To create a training task, specify:

  - The names and the values of the input fields in the `input_values` object.

  - Correct responses in the `known_solutions` object.

  - A hint in the `message_on_unknown_solution` property.

  For training tasks, it is convenient to create a [separate pool](train.md).

  {% note info %}

  You can also add responses and hints when creating a pool in [task markup mode](task_markup.md) (you need to use ["smart mixing"](distribute-tasks-by-pages.md#smart-mixing) when uploading tasks).

  {% endnote %}

  {% cut "Example" %}

  ```json
  {
    "input_values": {
      "image_url": "https://www.example.com/image1.png"
    },
    "known_solutions": [
      {
        "output_values": {
          "result": "OK",
          "like": false
        }
      }
    ],
    "message_on_unknown_solution": "The cat is in a good mood."
  }
  ```

  #|
  || Key | Description ||
  || **input_values** | **object**

  Input data for a task. List of pairs:

  ```json
    "<ID of field 1>": "<value of field 1>",
    "<ID of field 2>": "<value of field 2>",
    ...
    "<ID of field N>": "<value of field N>"
  ```
  ||
  || **known_solutions[].output_values** | **object**

  Output data values to check. You should specify values for all required output data fields.

  ```json
    "<ID of field 1>": "<correct response>",
    "<ID of field 2>": "<correct response>",
    ...
    "<ID of field N>": "<correct response>"
  ```
  ||
  || **message_on_unknown_solution** | **string**

  Hint for the task.

  ||
  |#

  {% endcut %}

  {% endcut %}

  {% cut "Field task" %}

  To create a field task, specify:

  - The names and the values of the input fields in the `input_values` object.

  - Point coordinates in the `latitude` and `longitude` properties.

  {% cut "Example" %}

  ```json
  {
    "input_values": {
      "image_url": "https://www.example.com/image1.png"
    },
    "latitude": "12.21",
    "longitude": "24.32"
  }
  ```

  #|
  || Key | Description ||
  || **input_values** | **object**

  Input data for a task. List of pairs:

  ```json
    "<ID of field 1>": "<value of field 1>",
    "<ID of field 2>": "<value of field 2>",
    ...
    "<ID of field N>": "<value of field N>"
  ```
  ||
  || **latitude** | **string**

  Latitude of a point on the map.

  ||
  || **longitude** | **string**

  Longitude of a point on the map.

  ||
  |#

  {% endcut %}

  {% include [toloka-requester-source-field-tasks-suites](../_includes/toloka-requester-source/id-toloka-requester-source/field-tasks-suites.md) %}

  {% endcut %}

  {% cut "Old format" %}

  ```json
  [
    {
      "INPUT:image_url": "https://www.example.com/image1.png"
    },
    {
      "INPUT:image_url": "https://www.example.com/image2.png"
    },
    {
      "INPUT:image_url": "https://www.example.com/image3.png"
    }
  ]
  ```

  {% endcut %}

{% endlist %}

## Working with the file {#applications}

In popular spreadsheet editors, you can import and export data in TSV or XLSX:

- [MS Excel]({{ ms-excel }})
- [LibreOffice]({{ libre-office }})
- [Google Documents]({{ google-docs }}).

A text editor is good for JSON files (for example, Notepad on Windows or TextEdit on Mac OS).

You can work with data in an editor and then save it in the desired format.

{% list tabs %}

- TSV

  1. Create a spreadsheet with [appropriate headings](#structure) or copy them from the template.

  1. Add data for tasks.

  1. Copy the entire spreadsheet. Paste it into a simple text editor (such as Notepad in Windows or TextEdit in Mac).

  1. Save the file in UTF-8 encoding with the `tsv` extension.

- XLSX

  1. Create a spreadsheet with [appropriate headings](#structure) or copy them from the template.

  1. Add data for tasks.

  1. Save the file in `XLSX`.

- JSON

  1. Download the file template in `JSON`.

  1. Open the template in a text editor and add your data.

  1. Save the file.

{% endlist %}

The maximum file size is 100 MB.

## Escaping {#string}

Escaping is the replacement of control characters in the text that are used for labeling with the corresponding text substitutions. It is used when you need to display a control character as a regular one.

The type of input data determines how control characters are escaped. Determine the type of data and study the corresponding paragraph. Possible options:

{% cut "String type data" %}

To display quotation marks `"` in the string type field:

- The quotation marks of this type come in pairs. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Enclose the field in quotation marks `" "`.

Unescaped quotation marks are removed when processing the file.

Data | Example of transferring data to a file | Status | What the Toloker will see
----- | ----- | ----- | -----
`monitor 24" buy` | `"monitor 24"" buy"` | `correct` | `monitor 24" buy`
`book "All about dogs"` | `book "All about dogs"` | `correct, but the quotes won't be displayed` | `book All about dogs`
`book “All about dogs”` | `"book “All about dogs”"` | `correct` | `book “All about dogs”`
`monitor 24" buy` | `monitor 24" buy` | `loading error` |

{% endcut %}

{% cut "Data in JSON format" %}

{% cut "To load data in a field with the json type" %}

- Add another quotation mark to each `"` type of quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Enclose the field in quotation marks `" "`.

| Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|`{"query": "monitor 24 inch buy"}` | `"{""query"": ""monitor 24 inch buy""}"` | `correct` | `monitor 24 inch buy`
|`{"query": "monitor 24 inch buy"}` | `"{"query": "monitor 24 inch buy"}"` | `loading error` |

{% endcut %}

{% cut "To display a quotation mark inside an object with the JSON type" %}

- Add another quotation mark `"` or a backslash and a quotation mark `\"` if there is no backslash before the quotation mark.

- Enclose the field in quotation marks `" "`.

|Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|`{"query": "monitor 24\" buy"}` | `"{""query"": ""monitor 24\"" buy""}"` | `correct` | `monitor 24" buy`
|`{"query": "monitor 24" buy"}` | `"{""query"": ""monitor 24\"" buy""}"` | `correct` | `monitor 24" buy`
|`{"query": "book \"All about dogs\""}` | `"{""query"": ""book \""All about dogs\""""}"` | `correct` | `book "All about dogs"`
|`{"query": "monitor 24\" buy"}` | `"{""query"": ""monitor 24\"\" buy""}"` | `loading error` |
|`{"query": "book \"All about dogs\""}` | `"{"query": "book \"All about dogs\""}"` | `loading error` |

{% endcut %}

{% cut "To display a backslash `\` inside an object with the JSON type" %}

- Escape it with an additional slash `\`.

- Enclose the field in quotation marks `" "`.

| Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|`{"query": "array A\B"}` |`"{""query"": ""array A\\B""}"` |`correct` |`array A\B`
|`{"query": "array A\B"}` | `"{""query"": ""array A\B""}"` | `loading error` |

{% endcut %}

{% endcut %}

{% cut "An array of data in the JSON format" %}

{% cut "To load an array of data in a field with the JSON type" %}

- Add another quotation mark to each `"` quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Add a backslash `\` before each comma inside the object if it isn't there already. Don't escape commas that separate objects inside the array.

- Enclose the field in quotation marks `" "`.

|Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|`[{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}]` | `"{""query"": ""monitor 24 inch buy""},{""query"": ""monitor 19 inch buy""}"` | `correct` | `monitor 24 inch buy monitor 19 inch buy`
|`[{"query": "monitor 24 inch\, system unit buy"},{"query": "monitor 17 inch\, system unit buy"}]` | `"{""query"": ""monitor 24 inch\, system unit buy""},""query"": ""monitor 19 inch\, system unit buy""}"` | `correct` | `monitor 24 inch, system unit buy monitor 19 inch, system unit buy`
|`[{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}]` | `"{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}"` | `loading error` |
|`[{"query": "monitor 24 inch, system unit buy"},"query": "monitor 17 inch, system unit buy"}]` | `"{""query"": ""monitor 24 inch, system unit buy""},""query"": ""monitor 19 inch, system unit buy""}"` | `loading error` |

{% endcut %}

{% cut "To display a quotation mark in an array of data in a field with the JSON type" %}

- Add another quotation mark `"` or a backslash and a quotation mark `\"` if there is no backslash before the quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Enclose the field in quotation marks `" "`.

|Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|`[{"query": "monitor 24\" buy"},{"query": "monitor 19\" buy"}]` | `"{""query"": ""monitor 24\"" inch buy""},{""query"": ""monitor 19\"" buy""}"` | `correct` | `monitor 24" buy monitor 19" buy`
|`[{"query": "monitor 24\" buy"},{"query": "monitor 19\" buy"}]` | `"{""query"": ""monitor 24\"" inch buy""},{""query"": ""monitor 19\" buy""}"` | `loading error` |

{% endcut %}

{% cut "To display a backslash `\` in an array of data in a field with the JSON type" %}

- Escape it with two backslashes `\\`.

- Enclose the field in quotation marks `" "`.

|Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|`[{"query": "array A\B"},{"query": "array C\B"}]` | `"{""query"": ""array A\\\B""},{""query"": ""array C\D""}"` | `correct` | `array A\B array C\D`
|`[{"query": "array A\B"},{"query": "array C\B"}]` | `"{""query"": ""array A\\B""},{""query"": ""array C\\D"}"` | `loading error` |

{% endcut %}

{% endcut %}

## What's next {#what_next}

- [Upload tasks to the pool](task_upload.md).

## Troubleshooting {#troubleshooting}

{% cut "Uploading tasks to a pool" %}

{% include [faq-how-many-tasks-in-suite](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-in-suite.md) %}

{% include [troubleshooting-uploading-tasks-errors](../_includes/troubleshooting/adding-tasks-to-the-pool/uploading-tasks-errors.md) %}

{% include [troubleshooting-uploading-too-long](../_includes/troubleshooting/adding-tasks-to-the-pool/uploading-too-long.md) %}

{% include [faq-how-many-tasks-toloker-will-see](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-toloker-will-see.md) %}

{% include [faq-upload-accepted-assignments](../_includes/faq/adding-tasks-to-the-pool/upload-accepted-assignments.md) %}

{% include [troubleshooting-marked-as-training](../_includes/troubleshooting/adding-tasks-to-the-pool/marked-as-training.md) %}

{% include [faq-create-task-file-properly](../_includes/faq/adding-tasks-to-the-pool/create-task-file-properly.md) %}

{% include [troubleshooting-syntax-error](../_includes/troubleshooting/adding-tasks-to-the-pool/syntax-error.md) %}

{% include [faq-max-number-per-suite](../_includes/faq/adding-tasks-to-the-pool/max-number-per-suite.md) %}

{% include [faq-smart-mixing](../_includes/faq/adding-tasks-to-the-pool/smart-mixing.md) %}

{% include [faq-right-time-limit](../_includes/faq/adding-tasks-to-the-pool/right-time-limit.md) %}

{% include [faq-task-suite-difference](../_includes/faq/adding-tasks-to-the-pool/task-suite-difference.md) %}

{% include [troubleshooting-same-task-on-different-pages](../_includes/troubleshooting/adding-tasks-to-the-pool/same-task-on-different-pages.md) %}

{% endcut %}

{% cut "Tasks file" %}

{% include [troubleshooting-preview-all-photos](../_includes/troubleshooting/adding-tasks-to-the-pool/preview-all-photos.md) %}

{% include [faq-multiple-known-solutions](../_includes/faq/adding-tasks-to-the-pool/multiple-known-solutions.md) %}

{% include [faq-where-is-file-added](../_includes/faq/adding-tasks-to-the-pool/where-is-file-added.md) %}

{% include [faq-properly-structure-json](../_includes/faq/adding-tasks-to-the-pool/properly-structure-json.md) %}

{% include [faq-array-input-file](../_includes/faq/adding-tasks-to-the-pool/array-input-file.md) %}

{% include [faq-order-input](../_includes/faq/adding-tasks-to-the-pool/order-input.md) %}

{% include [faq-missing-headers](../_includes/faq/adding-tasks-to-the-pool/missing-headers.md) %}

{% endcut %}

{% cut "Input data" %}

{% include [troubleshooting-commas-inside-array](../_includes/troubleshooting/adding-tasks-to-the-pool/commas-inside-array.md) %}

{% include [faq-how-hint-displayed](../_includes/faq/adding-tasks-to-the-pool/how-hint-displayed.md) %}

{% include [faq-add-your-text-here](../_includes/faq/adding-tasks-to-the-pool/add-your-text-here.md) %}

{% include [troubleshooting-double-quotas-disappear](../_includes/troubleshooting/adding-tasks-to-the-pool/double-quotas-disappear.md) %}

{% include [faq-link-golden-field](../_includes/faq/adding-tasks-to-the-pool/link-golden-field.md) %}

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}