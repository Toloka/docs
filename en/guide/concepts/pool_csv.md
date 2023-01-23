# Creating a file with tasks

Tasks are uploaded to the [pool](pool-main.md) in [the tasks file](../../glossary.md#tsv).

Download the file template for your [project](../../glossary.md#project) on the [pool](../../glossary.md#pool) page. Use the template to create your own task file and upload it to the pool.

{% cut "Use sample data" %}

If you want to see what your project will look like after the launch, but you don't have any labeling tasks yet, you can upload ready-made sample data to the pool. Sample data is available for templates:

- {% if locale == "en-com" %}**Image classification**{% endif %}
- {% if locale == "en-com" %}**Product search relevance**{% endif %}
- {% if locale == "en-com" %}**Object recognition & detection**{% endif %}
- {% if locale == "en-com" %}**Clickbait or not?**{% endif %}

Click {% if locale == "en-com" %}**Use sample data**{% endif %} next to {% if locale == "en-com" %}**Attach the prepared file with data**{% endif %}. This lets you avoid any additional actions with files.

Once you've finished working with the sample data and everything looks good, prepare your data and upload it to the pool.

{% endcut %}

If you need to add different task types to the pool, upload multiple files, one for each task type.

## Tasks file structure {#structure}

The first line of the file contains the column headers:

- `INPUT:<name of the input data field>` — Input data for tasks.

- `GOLDEN:<name of the output data field>` — Responses for [control tasks](../../glossary.md#control-task).

- `HINT:text` — Hints for [training tasks](../../glossary.md#training-task). The Toloker will see the hint text at the top of the task (on a red background) if their response to the control task is different from the correct one.

- Point coordinates for [field tasks](../tutorials/walk.md):

    - `Al:latitude` — Latitude.

    - `Al:longitude` — Longitude.

Task type depends on which fields are filled in:

{% list tabs %}

- General task

  To create a [general task](../../glossary.md#general-task), fill in the columns with the `INPUT` header.

  {% cut "Example with a simple object (string, link, and so on)" %}

  ![](../_images/location-job/pool_csv/main_tsv.png)

  {% endcut %}

  {% cut "Example with a string array" %}

  ![](../_images/location-job/pool_csv/main_tsv2.png)

  {% endcut %}

- Control task

  To create a control task, add:

  - The task input data in the columns with the `INPUT` header.

  - Correct responses in the columns with the `GOLDEN` header.

  {% note tip %}

  You can also add responses when creating a pool in [task markup mode](task_markup.md) (you need to use [“smart mixing”](distribute-tasks-by-pages.md#smart-mixing) when uploading tasks).

  {% endnote %}

  {% cut "Example" %}

  ![](../_images/location-job/pool_csv/controls_tsv.png)

  {% endcut %}

- Training task

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

- Field task

  The task that the Toloker chooses on the map in the Toloka mobile app.

  To create a field task, add:

  - The task input data in the columns with the `INPUT` header.

  - Coordinates in the `Al:latitude` and `Al:longitude` columns.

  {% cut "Example" %}

  ![](../_images/tutorials/walk/squirrel_tsv.png)

  {% endcut %}

{% endlist %}

The columns with [required input data fields](incoming.md) must be filled. The other columns can be deleted if they are empty.

## Working with the file {#applications}

In popular spreadsheet editors, you can import and export data in TSV or XLSX:

- [MS Excel]({{ ms-excel }})
- [LibreOffice]({{ libre-office }})
- [Google Documents]({{ google-docs }}).

A text editor is good for JSON files (for example, {% if locale == "en-com" %}Notepad{% endif %} on Windows or TextEdit on Mac OS).

You can work with data in an editor and then save it in the desired format.

{% list tabs %}

- TSV

  1. Create a spreadsheet with [appropriate headings](#structure) or copy them from the template.

  1. Add data for tasks.

  1. Copy the entire spreadsheet. Paste it into a simple text editor (such as {% if locale == "en-com" %}Notepad{% endif %} in Windows or TextEdit in Mac).

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
{% if locale == "en-com" %}`monitor 24" buy`{% endif %} | {% if locale == "en-com" %}`"monitor 24"" buy"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`monitor 24" buy`{% endif %}
{% if locale == "en-com" %}`book "All about dogs"`{% endif %} | {% if locale == "en-com" %}`book "All about dogs"`{% endif %} | {% if locale == "en-com" %}`correct, but the quotes won't be displayed`{% endif %} | {% if locale == "en-com" %}`book All about dogs`{% endif %}
{% if locale == "en-com" %}`book “All about dogs”`{% endif %} | {% if locale == "en-com" %}`"book “All about dogs”"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`book “All about dogs”`{% endif %}
{% if locale == "en-com" %}`monitor 24" buy`{% endif %} | {% if locale == "en-com" %}`monitor 24" buy`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |

{% endcut %}

{% cut "Data in JSON format" %}

{% cut "To load data in a field with the json type" %}

- Add another quotation mark to each `"` type of quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Enclose the field in quotation marks `" "`.

| Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|{% if locale == "en-com" %}`{"query": "monitor 24 inch buy"}`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24 inch buy""}"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`monitor 24 inch buy`{% endif %}
|{% if locale == "en-com" %}`{"query": "monitor 24 inch buy"}`{% endif %} | {% if locale == "en-com" %}`"{"query": "monitor 24 inch buy"}"`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |

{% endcut %}

{% cut "To display a quotation mark inside an object with the JSON type" %}

- Add another quotation mark `"` or a backslash and a quotation mark `\"` if there is no backslash before the quotation mark.

- Enclose the field in quotation marks `" "`.

|Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|{% if locale == "en-com" %}`{"query": "monitor 24\" buy"}`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24\"" buy""}"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`monitor 24" buy`{% endif %}
|{% if locale == "en-com" %}`{"query": "monitor 24" buy"}`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24\"" buy""}"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`monitor 24" buy`{% endif %}
|{% if locale == "en-com" %}`{"query": "book \"All about dogs\""}`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""book \""All about dogs\""""}"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`book "All about dogs"`{% endif %}
|{% if locale == "en-com" %}`{"query": "monitor 24\" buy"}`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24\"\" buy""}"`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |
|{% if locale == "en-com" %}`{"query": "book \"All about dogs\""}`{% endif %} | {% if locale == "en-com" %}`"{"query": "book \"All about dogs\""}"`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |

{% endcut %}

{% cut "To display a backslash `\` inside an object with the JSON type" %}

- Escape it with an additional slash `\`.

- Enclose the field in quotation marks `" "`.

| Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|`{"query": "array A\B"}` |`"{""query"": ""array A\\B""}"` |`correct` |`array A\B`
|{% if locale == "en-com" %}`{"query": "array A\B"}`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""array A\B""}"`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |

{% endcut %}

{% endcut %}

{% cut "An array of data in the JSON format" %}

{% cut "To load an array of data in a field with the JSON type" %}

- Add another quotation mark to each `"` quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Add a backslash `\` before each comma inside the object if it isn't there already. Don't escape commas that separate objects inside the array.

- Enclose the field in quotation marks `" "`.

|Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|{% if locale == "en-com" %}`[{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}]`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24 inch buy""},{""query"": ""monitor 19 inch buy""}"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`monitor 24 inch buy monitor 19 inch buy`{% endif %}
|{% if locale == "en-com" %}`[{"query": "monitor 24 inch\, system unit buy"},{"query": "monitor 17 inch\, system unit buy"}]`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24 inch\, system unit buy""},""query"": ""monitor 19 inch\, system unit buy""}"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`monitor 24 inch, system unit buy monitor 19 inch, system unit buy`{% endif %}
|{% if locale == "en-com" %}`[{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}]`{% endif %} | {% if locale == "en-com" %}`"{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}"`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |
|{% if locale == "en-com" %}`[{"query": "monitor 24 inch, system unit buy"},"query": "monitor 17 inch, system unit buy"}]`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24 inch, system unit buy""},""query"": ""monitor 19 inch, system unit buy""}"`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |

{% endcut %}

{% cut "To display a quotation mark in an array of data in a field with the JSON type" %}

- Add another quotation mark `"` or a backslash and a quotation mark `\"` if there is no backslash before the quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Enclose the field in quotation marks `" "`.

|Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|{% if locale == "en-com" %}`[{"query": "monitor 24\" buy"},{"query": "monitor 19\" buy"}]`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24\"" inch buy""},{""query"": ""monitor 19\"" buy""}"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`monitor 24" buy monitor 19" buy`{% endif %}
|{% if locale == "en-com" %}`[{"query": "monitor 24\" buy"},{"query": "monitor 19\" buy"}]`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""monitor 24\"" inch buy""},{""query"": ""monitor 19\" buy""}"`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |

{% endcut %}

{% cut "To display a backslash `\` in an array of data in a field with the JSON type" %}

- Escape it with two backslashes `\\`.

- Enclose the field in quotation marks `" "`.

|Data | Example of transferring data to a file | Status | What the Toloker will see
|----- | ----- | ----- | -----
|{% if locale == "en-com" %}`[{"query": "array A\B"},{"query": "array C\B"}]`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""array A\\\B""},{""query"": ""array C\D""}"`{% endif %} | {% if locale == "en-com" %}`correct`{% endif %} | {% if locale == "en-com" %}`array A\B array C\D`{% endif %}
|{% if locale == "en-com" %}`[{"query": "array A\B"},{"query": "array C\B"}]`{% endif %} | {% if locale == "en-com" %}`"{""query"": ""array A\\B""},{""query"": ""array C\\D"}"`{% endif %} | {% if locale == "en-com" %}`loading error`{% endif %} |

{% endcut %}

{% endcut %}

## What's next {#what_next}

- [Upload tasks to the pool](task_upload.md).

## Troubleshooting {#troubleshooting}

{% cut "Uploading tasks to a pool" %}

{% include [faq-how-many-tasks-in-suite](../_includes/faq/adding-tasks-to-the-pool/how-many-tasks-in-suite.md) %}

{% include [troubleshooting-uploading-tasks-errors](../_includes/troubleshooting/adding-tasks-to-the-pool/uploading-tasks-errors.md) %}

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