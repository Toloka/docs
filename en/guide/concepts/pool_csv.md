# Creating a file with tasks

Tasks are uploaded to the [pool](pool-main.md) in the [tasks file](../../glossary.md#tsv-file-definition-ru).

Download the file template for your [project](../../glossary.md#project-ru) on the [pool](../../glossary.md#pool-ru) page. Use the template to create your own task file and upload it to the pool.

If you need to add different task types to the pool, upload multiple files, one for each task type.

## Tasks file structure {#structure}

The first line of the file contains the column headers:
- `INPUT:<name of the [input data field](incoming.md)>` — Input data for tasks.

- `GOLDEN:<name of the [output data field](incoming.md)>` — Responses for [control tasks](../../glossary.md#control-task-ru).
- `HINT:text` — Hints for [training tasks](../../glossary.md#training-task-ru). The Toloker will see the hint text at the top of the task (on a red background) if their response to the control task is different from the correct one.

- Point coordinates for [field tasks](walk.md):
    - `Al:latitude` — Latitude.

    - `Al:longitude` — Longitude.

Task type depends on which fields are filled in:

#### General task

To create a [general task](../../glossary.md#general-task-ru), fill in the columns with the `INPUT` header.

#### Example with a simple object (string, link, and so on)
![](../_images/location-job/pool_csv/main_tsv.png)
#### Example with a string array
![](../_images/location-job/pool_csv/main_tsv2.png)

#### Control task

To create a control task, add:

- The task input data in the columns with the `INPUT` header.
- Correct responses in the columns with the `GOLDEN` header.

{% note info %}

You can also add responses when creating a pool in [task markup mode](task_markup.md) (you need to use [“smart mixing”](distribute-tasks-by-pages.md#smart-mixing) when uploading tasks).

{% endnote %}


#### Example
![](../_images/location-job/pool_csv/controls_tsv.png)

#### Training task

To create a training task, add:
- The task input data in the columns with the `INPUT` header.
- Correct responses in the columns with the `GOLDEN` header.
- A hint in the `HINT:text` column.

For training tasks, it is convenient to create a [separate pool](train.md).

{% note info %}

You can also add responses and hints when creating a pool in [task markup mode](task_markup.md) (you need to use [“smart mixing”](distribute-tasks-by-pages.md#smart-mixing) when uploading tasks).

{% endnote %}


#### Example
![](../_images/location-job/pool_csv/cats_tsv.png)

#### Field task

The task that the Toloker chooses on the map in the Toloka mobile app.

To create a field task, add:

- The task input data in the columns with the `INPUT` header.
- Coordinates in the `Al:latitude` and `Al:longitude` columns.

#### Example
![](../_images/tutorials/walk/squirrel_tsv.png)

The columns with [required input data fields](incoming.md) must be filled. The other columns can be deleted if they are empty.

## Working with the file {#applications}

In popular spreadsheet editors, you can import and export data in TSV or XLSX:

- [MS Excel]({{ ms-excel }})
- [LibreOffice]({{ libre-office }})
- [Google Documents]({{ google-docs }}).

You can work with data in a spreadsheet and then save it to the desired format.

#### TSV

1. Create a spreadsheet with [appropriate headings](#structure) or copy them from the template.
1. Add data for tasks.
1. Copy the entire spreadsheet. Paste it into a simple text editor (such as {% if locale == "en-com" %}Notepad{% endif %} in Windows or TextEdit in Mac).
1. Save the file in UTF-8 encoding with the `tsv` extension.

#### XLSX

1. Create a spreadsheet with [appropriate headings](#structure) or copy them from the template.
1. Add data for tasks.
1. Save the file in `XLSX`.

The maximum file size is 100 MB.

## Escaping {#string}

Escaping is the replacement of control characters in the text that are used for labeling with the corresponding text substitutions. It is used when you need to display a control character as a regular one.

The type of input data determines how control characters are escaped. Determine the type of data and study the corresponding paragraph. Possible options:

#### String type data

To display quotation marks ``"`` in the string type field:
- The quotation marks of this type come in pairs. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Enclose the field in quotation marks `" "`.

Unescaped quotation marks are removed when processing the file.

Data | Example of transferring data to a file | Status | What the Toloker will see
----- | ----- | ----- | -----
{% if locale == "en-com" %}``` monitor 24" buy ```{% endif %} | {% if locale == "en-com" %}``` "monitor 24"" buy" ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` monitor 24" buy ```{% endif %}
{% if locale == "en-com" %}``` book "All about dogs" ```{% endif %} | {% if locale == "en-com" %}``` book "All about dogs" ```{% endif %} | {% if locale == "en-com" %}``` correct, but the quotes won't be displayed ```{% endif %} | {% if locale == "en-com" %}``` book All about dogs ```{% endif %}
{% if locale == "en-com" %}``` book “All about dogs” ```{% endif %} | {% if locale == "en-com" %}``` "book “All about dogs”" ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` book “All about dogs” ```{% endif %}
{% if locale == "en-com" %}``` monitor 24" buy ```{% endif %} | {% if locale == "en-com" %}``` monitor 24" buy ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |


#### Data in JSON format

#### To load data in a field with the json type

- Add another quotation mark to each ``"`` type of quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Enclose the field in quotation marks `" "`.


Data | Example of transferring data to a file | Status | What the Toloker will see
----- | ----- | ----- | -----
{% if locale == "en-com" %}``` {"query": "monitor 24 inch buy"} ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24 inch buy""}" ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` monitor 24 inch buy ```{% endif %}
{% if locale == "en-com" %}``` {"query": "monitor 24 inch buy"} ```{% endif %} | {% if locale == "en-com" %}``` "{"query": "monitor 24 inch buy"}" ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |


#### To display a quotation mark inside an object with the JSON type

- Add another quotation mark `"` or a backslash and a quotation mark `\"` if there is no backslash before the quotation mark.

- Enclose the field in quotation marks `" "`.


Data | Example of transferring data to a file | Status | What the Toloker will see
----- | ----- | ----- | -----
{% if locale == "en-com" %}``` {"query": "monitor 24\" buy"} ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24\"" buy""}" ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` monitor 24" buy ```{% endif %}
{% if locale == "en-com" %}``` {"query": "monitor 24" buy"} ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24\"" buy""}" ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` monitor 24" buy ```{% endif %}
{% if locale == "en-com" %}``` {"query": "book \"All about dogs\""} ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""book \""All about dogs\""""}" ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` book "All about dogs" ```{% endif %}
{% if locale == "en-com" %}``` {"query": "monitor 24\" buy"} ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24\"\" buy""}" ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |
{% if locale == "en-com" %}``` {"query": "book \"All about dogs\""} ```{% endif %} | {% if locale == "en-com" %}``` "{"query": "book \"All about dogs\""}" ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |


#### To display a backslash `\` inside an object with the JSON type

- Escape it with an additional slash `\`.

- Enclose the field in quotation marks `" "`.


Data | Example of transferring data to a file | Status | What the Toloker will see
----- | ----- | ----- | -----
``` {"query": "array A\B"} ``` | ``` "{""query"": ""array A\\B""}" ``` | ``` correct ``` | ``` array A\B ```
{% if locale == "en-com" %}``` {"query": "array A\B"} ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""array A\B""}" ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |

#### An array of data in the JSON format

#### To load an array of data in a field with the JSON type

- Add another quotation mark to each `"` quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Add a backslash `\` before each comma inside the object if it isn't there already. Don't escape commas that separate objects inside the array.

- Enclose the field in quotation marks `" "`.


Data | Example of transferring data to a file | Status | What the Toloker will see
----- | ----- | ----- | -----
{% if locale == "en-com" %}```  [{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}] ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24 inch buy""},{""query"": ""monitor 19 inch buy""}"  ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` monitor 24 inch buy monitor 19 inch buy ```{% endif %}
{% if locale == "en-com" %}``` [{"query": "monitor 24 inch\, system unit buy"},{"query": "monitor 17 inch\, system unit buy"}]  ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24 inch\, system unit buy""},""query"": ""monitor 19 inch\, system unit buy""}"  ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` monitor 24 inch, system unit buy monitor 19 inch, system unit buy ```{% endif %}
{% if locale == "en-com" %}``` [{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}]  ```{% endif %} | {% if locale == "en-com" %}``` "{"query": "monitor 24 inch buy"},{"query": "monitor 19 inch buy"}"  ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |
{% if locale == "en-com" %}``` [{"query": "monitor 24 inch, system unit buy"},"query": "monitor 17 inch, system unit buy"}]  ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24 inch, system unit buy""},""query"": ""monitor 19 inch, system unit buy""}"  ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |


#### To display a quotation mark in an array of data in a field with the JSON type

- Add another quotation mark `"` or a backslash and a quotation mark `\"` if there is no backslash before the quotation mark. Don't escape other types of quotation marks (`« »` and `“ ”`).

- Enclose the field in quotation marks `" "`.


Data | Example of transferring data to a file | Status | What the Toloker will see
----- | ----- | ----- | -----
{% if locale == "en-com" %}```  [{"query": "monitor 24\" buy"},{"query": "monitor 19\" buy"}] ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24\"" inch buy""},{""query"": ""monitor 19\"" buy""}"  ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` monitor 24" buy monitor 19" buy ```{% endif %}
{% if locale == "en-com" %}```  [{"query": "monitor 24\" buy"},{"query": "monitor 19\" buy"}] ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""monitor 24\"" inch buy""},{""query"": ""monitor 19\" buy""}"  ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |


#### To display a backslash `\` in an array of data in a field with the JSON type

- Escape it with two backslashes `\\`.

- Enclose the field in quotation marks `" "`.


Data | Example of transferring data to a file | Status | What the Toloker will see
----- | ----- | ----- | -----
{% if locale == "en-com" %}```  [{"query": "array A\B"},{"query": "array C\B"}] ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""array A\\\B""},{""query"": ""array C\D""}"  ```{% endif %} | {% if locale == "en-com" %}``` correct ```{% endif %} | {% if locale == "en-com" %}``` array A\B array C\D ```{% endif %}
{% if locale == "en-com" %}```  [{"query": "array A\B"},{"query": "array C\B"}] ```{% endif %} | {% if locale == "en-com" %}``` "{""query"": ""array A\\B""},{""query"": ""array C\\D"}"  ```{% endif %} | {% if locale == "en-com" %}``` loading error ```{% endif %} |


## What's next {#what_next}

- [Upload tasks to the pool.](task_upload.md).


## Troubleshooting {#troubleshooting}

#### Uploading tasks to a pool

#### How many tasks should be in a suite?

The number of tasks depends on how difficult and time-consuming the tasks are. Keep the size reasonably small. Large task suites are unpopular, partly because they are inconvenient for Tolokers (for example, if the internet connection is unstable).

#### Errors when uploading tasks in the pool

#### How do I view the processing log?

To view the processing log, click **More on uploading errors**. The processing log is written in JSON format. Objects inside `result` match the line number of the uploaded file. Lines that were processed with an error have the status `"success": false`.
{% note info %}

To work with a large log conveniently, copy it to the text editor.

{% endnote %}

#### Errors in column headers

If the [column headings](pool_csv.md) are incorrect, the whole file is rejected. Otherwise, Toloka specifies the number of tasks with processing errors.

#### Processing errors table

Overview | How to fix
----- | -----
``` "parsing_error_of": "https://tlk.s3.yandex.net/wsdm2020/photos/2d5f63a3184919ce7e3e7068cf93da4b.jpg\t\t", "exception_msg": "the nameMapping array and the sourceList should be the same size (nameMapping length = 1, sourceList size = 3)" ```
**Extra tabs.**<br/><br/>If the uploaded file contains more `\t` column separators after the data or the link than the number of columns set in the [input data](../../glossary.md#input-output-data-ru), you get an error message.<br/><br/>For example, if 1 column is set in the input data, and two more `\t\t` tabs are added in the file after the link, you get 3 columns, 2 of which are excessive. | Remove extra column separators in the above example — both `\t\t` characters.
``` "exception_msg": "the nameMapping array and the sourceList should be the same size (nameMapping length = 4, sourceList size = 6)" ```
**The number of fields in the header and in the row doesn't match.** | Make sure that:<br/><br/>- The number of tabs in the file structure is correct.<br/>- String values with tab characters are enclosed in [quotation marks](pool_csv.md#string)`" "`.
``` "code": "VALUE_REQUIRED", "message": "Value must be present and not equal to null" ```
**The value is missing for a required input field.** | Make sure that columns with required input data fields are filled.
``` "code": "INVALID_URL_SYNTAX", "message": "Value must be in valid url format" ```
**Invalid data in a “link” (“url”) field.** | Make sure that:<br/>- Links start with the `http://`, `https://` or `www` prefix.
``` "exception_msg": "unexpected end of file while reading quoted column beginning on line 2 and ending on line 4" ```
**Unpaired quotation mark in a string.** | Check that all quotation marks are [escaped](pool_csv.md#string).

#### How do I know how many tasks a Toloker will see on the page?

You can specify the number of tasks on the page when you upload your tasks to the pool. For more information about distributing tasks across pages, see [this article](distribute-tasks-by-pages.md).

#### How do I upload the file with the accepted assignments back to Toloka for projects with non-automatic acceptance? Where do I find the format of the upload data?

Use the button **Upload review results** to upload your file. You can see the format [here](accept.md).

Assignments are reviewed in the tasks file.

#### Why haven't I received assignments since I launched my first project, and all the uploaded assignments are marked as "Training"?

Check the `hint` field. For the general tasks, this field must be empty.

#### How do I create the task file properly so that there are no errors?

In the file with the general tasks, the columns with the `INPUT` headers must be filled out. You can see those headers if you download a sample file from the pool.

If you are creating control tasks, fill out the `GOLDEN` columns with the correct responses.

If you are creating a training task, you also need to fill in the `HINT:text` column. For the general tasks you don't need any columns other than `INPUT`, so feel free to delete them.

You have to use TSV or XLSX file format and UTF-8 encoding.

For more information about creating the file, see the [Guide](pool_csv.md). If there are errors during the upload, look up the error description on this [page](task_upload.md).

#### Why do I see a syntax error when I upload a task where a user has to view an image and write feedback?

The error might occur if the expected input type is URL, but a string is received.

There may be two reasons:
- The input field has the "link" type.
- The pool was created for an outdated project version. It means that the pool was created before you changed the input field type.

#### What is the maximum number of tasks per suite?

It depends on the task. Technically, you can use as many tasks you want.

But users don't like to take lengthy tasks. They'd rather do 10 tasks that take one minute each than one task that takes 10 minutes.

In addition, if you use a large number of tasks on the page, there might be issues with uploading the files to be labeled. This problem might occur with images.

The third thing to consider is quality control and assignment review. If you allow recompletion of assignments by banned users, you should split the task into smaller parts so that fewer assignments are recompleted. You are more likely to meet your budget this way.

#### How do I specify smart mixing settings in the interface when uploading a file?

Smart mixing settings are specified for the file rather than for the pool.

The settings specified during the first file upload are applied to all the files that are uploaded to this pool later on.

#### What is the right time limit for the task completion?
Try completing the tasks yourself. Ask your colleagues and friends to complete them. Find out average completion time and add 50% to it.
#### What is the difference between "task" and "task_suite"?

A task means a separate task. A task suite means a page with tasks. The Toloker gets paid for a task suite.

#### The same task appeared on different pages

The same task may appear on different pages if:

- Dynamic overlap is used (incremental relabeling, IRL). As an example, let's say there were 5 tasks on a page. For 4 of them, responses coincided and the common response was counted as correct. The fifth task was mixed into another set because it didn't get into the final response and it needs to be “reassessed”.
- Different tasks have different overlap. Tasks with higher overlap will be additionally shown in sets with the other remaining tasks in the pool.
- If a [quality control rule](../../glossary.md#quality-control-rules-ru) changes a task's overlap, it will appear in a different set.

#### Tasks file

#### Why does the preview display all the photos from the tasks file at once?

You must use a separate row for each task in your tasks file. For more information, see [here](pool_csv.md).

When you create a pool, the pool will have settings for the number of tasks per suite.

#### How do I add multiple "known_solutions" to a training task file?

You can't use the interface to upload the tasks with multiple correct responses to the pool. You can only use the [API]({{ toloka-api-tasks }}) for that.

#### Where is my file added if I upload it to the running pool?

If you have the **Keep task order** option enabled, labeling will start after the previously uploaded tasks are taken by users. If this option is disabled, we can't guarantee that the tasks are assigned in their sequence order.

#### How do I properly structure the file used for data upload if the input includes JSON data?

All the values are written to the same column. Make sure to escape quotes. For more information about escaping quotes in JSON format, see the [Guide](pool_csv.md#json).

#### How do I write an array to the input file?

The array of strings in the input data must be comma-separated. For example: `INPUT:typestext1, text2, text3, text4`

#### Does the order of the INPUT field and GOLDEN fields in the file matter?

The order of the fields in the file does not matter. Use your preferred order of fields.

#### If there are no headers for some input columns in the tasks file, are they skipped during import? Will they be skipped if they have headers without the "INPUT:.." prefix?

No. If you try to upload a file with missing headers to the pool, the system issues an upload error. All the INPUT fields required in the specification must be present in the tasks file. There must be no extra fields or columns.

If you don't want to show some data to Tolokers, but you still need this data in the file, create the optional hidden input fields for such data in the project.

#### Input data

#### The system interprets commas inside my array elements as separators between the array elements. How do I avoid this?

Escape commas with a backslash (`\`).

#### How is the data from the "hint" column displayed?

The text from the `hint`field will be shown to the Toloker in a red box at the top of the page if they give a response to the control task that differs from the correct one.

If you need to display the text from the `hint` field in several lines, add hyphens to the file and enclose the text in quotation marks.

#### What do the lines "Add your text here" mean?

"Add your text here" is a hint for you. It means that you can replace the text in the field with your task data. The file structure and how to fill it out is described [here](pool_csv.md).

#### Why do double quotes disappear from the output if I try to escape them using quotation marks?

If you have one word enclosed in quotes, format the uploaded assignment like this: `"How many letters are there in the word ""Liechtenstein"""`. If you are escaping quotes inside your text, then the entire text must be enclosed in quotes. For more information, see the [Guide](pool_csv.md#string).

#### How do I insert a link in the GOLDEN field?

Text in the GOLDEN field must match the control text exactly.

Usually, if you copy site links from the browser, the copied links have the same format. But this is not the case when the link is trimmed or typed manually.

Check the links that you use. There are several ways to unify links:
- Add requirements for the link format in your instructions and hints in your training pool.
- Use RegExp in your JS to trim the received links and write the result to the new output field, and then match the received value against the control value.


{% include [contact-support](../_includes/contact-support-help.md) %}
