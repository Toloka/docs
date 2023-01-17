# How to upload tasks

To upload a [file with tasks](../../glossary.md#tsv) to a [pool](pool-main.md):

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.

1. Attach a prepared dataset or media files.

    {% list tabs %}

    - A prepared dataset

        1. Download the template and replace the sample data in it with [your own data](pool_csv.md).

        1. Click **Select prepared dataset** and choose your [file with tasks](../../glossary.md#tsv).

        {% cut "Use sample data" %}

        If you want to see what your project will look like after the launch, but you don't have any labeling tasks yet, you can upload ready-made sample data to the pool. Sample data is available for the templates:

        - {% if locale == "en-com" %}**Image classification**{% endif %}
        - {% if locale == "en-com" %}**Product search relevance**{% endif %}
        - {% if locale == "en-com" %}**Object recognition & detection**{% endif %}
        - {% if locale == "en-com" %}**Clickbait or not?**{% endif %}

        Click {% if locale == "en-com" %}**Use sample data**{% endif %} next to {% if locale == "en-com" %}**Attach the prepared file with data**{% endif %}. This lets you avoid any additional actions with files.

        Once you've finished working with the sample data and everything looks good, prepare your data and upload it to the pool.

        {% endcut %}

    - Media files

        {% include [media-files](../_includes/toloka-requester-source/id-toloka-requester-source/media-files.md) %}

    {% endlist %}

1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. Choose a way to put tasks into suites and specify the number of tasks per suite. For more information, see [Ways to group tasks in suites](distribute-tasks-by-pages.md).

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

1. Wait for the result.

To delete all the tasks in the pool, click {% if locale == "en-com" %}**Delete**{% endif %}.

{% note alert "Restriction" %}

You can add up to one million tasks to the pool. To upload more tasks, create another pool.

{% endnote %}

## Tips and recommendations {#tips}

- Set the number of tasks per suite depending on the complexity and time allocated for a task.

    We recommend that you distribute them so that each task suite takes no more than five minutes to complete.

- If you get a processing error, it means that the data file is not formatted correctly. For example, there are unnecessary tabs in the file or some lines, headers, or quotes are missing.

    In this case, click {% if locale == "en-com" %}**Cancel**{% endif %}, correct the mistakes, and then upload the file again.

## Processing errors {#table-with-errors}

If an error occurred while uploading the file, use the table.

To view the processing log, click **More on uploading errors**. The processing log is written in JSON format. Objects inside `result` match the line number of the uploaded file. Lines that were processed with an error have the status `"success": false`.

{% note tip %}

To work with a large log conveniently, copy it to the text editor.

{% endnote %}

{% cut "Processing errors tables" %}

```json
"parsing_error_of": "https://tlk.s3.yandex.net/wsdm2020/photos/2d5f63a3184919ce7e3e7068cf93da4b.jpg\t\t",
"exception_msg": "the nameMapping array and the sourceList should be the same size (nameMapping length = 1, sourceList size = 3)"
```

#|
||**Overview**|**How to fix**||
||**Extra tabs.**

If the uploaded file contains more `\t` column separators after the data or the link than the number of columns set in the [input data](../../glossary.md#input-output-data), you get an error message.

For example, if 1 column is set in the input data, and two more `\t\t` tabs are added in the file after the link, you get 3 columns, 2 of which are excessive. | Remove extra column separators in the above example — both `\t\t` characters.||
|#

```json
"exception_msg": "the nameMapping array and the sourceList should be the same size (nameMapping length = 4, sourceList size = 6)"
```

#|
||**Overview**|**How to fix**||
||**The number of fields in the header and in the row doesn't match.** | Make sure that:

- The number of tabs in the file structure is correct.
- String values with tab characters are enclosed in [quotation marks](pool_csv.md#string)`" "`.
|#

```json
"code": "VALUE_REQUIRED", "message": "Value must be present and not equal to null"
```

#|
||**Overview**|**How to fix**||
||**The value is missing for a required input field.** | Make sure that columns with required input data fields are filled.||
|#

```json
"code": "INVALID_URL_SYNTAX", "message": "Value must be in valid url format"
```

#|
||**Overview**|**How to fix**||
||**Invalid data in a “link” (“url”) field.** | Make sure that:

- Links start with the `http://`, `https://` or `www` prefix.||
|#

```json
"exception_msg": "unexpected end of file while reading quoted column beginning on line 2 and ending on line 4"
```

#|
||**Overview**|**How to fix**||
||**Unpaired quotation mark in a string.** | Check that all quotation marks are [escaped](pool_csv.md#string).||
|#

{% endcut %}

## What's next {#what_next}

- Learn more about [ways to group tasks in suites](distribute-tasks-by-pages.md).

- Check the project settings and tasks with the help of [special labeling mode](self-labeling.md) before you send them to real Tolokers.

- If you haven't labeled your [control](../../glossary.md#control-task) and [training](../../glossary.md#training-task) tasks in the file, [edit the tasks in the interface](task_markup.md).

## See also {#see-also}

- [{#T}](cloud-storage.md)
- [{#T}](amazon-cloud-storage.md)
- [{#T}](azure-cloud-storage.md)
- [{#T}](google-cloud-storage.md)
- [{#T}](use-object-storage.md)

## For developers {#for-developers}

- [Toloka API: Tasks](../../api/concepts/tasks.md)
- [Toloka-Kit: Creating tasks](../../toloka-kit/reference/toloka.client.TolokaClient.create_task.md)

## Troubleshooting {#troubleshooting}

{% cut "Errors in column headers" %}

If the [column headings](pool_csv.md) are incorrect, the whole file is rejected. Otherwise, Toloka specifies the number of tasks with processing errors.

{% endcut %}

{% cut "Why haven't I received assignments since I launched my first project, and all the uploaded assignments are marked as "Training"?" %}

Check the `hint` field. For the general tasks, this field must be empty.

{% endcut %}

{% cut "How many tasks should be in a suite?" %}

The number of tasks depends on how difficult and time-consuming the tasks are. Keep the size reasonably small. Large task suites are unpopular, partly because they are inconvenient for Tolokers (for example, if the internet connection is unstable).

{% endcut %}

{% cut "What is the right time limit for the task completion?" %}

Try completing the tasks yourself. Ask your colleagues and friends to complete them. Find out average completion time and add 50% to it.

{% endcut %}

{% cut "Why do I see a syntax error when I upload a task where a Toloker has to view an image and write feedback?" %}

The error might occur if the expected input type is URL, but a string is received.

There may be two reasons:

- The input field has the "link" type.

- The pool was created for an outdated project version. It means that the pool was created before you changed the input field type.

{% endcut %}

{% cut "What is the maximum number of tasks per suite?" %}

It depends on the task. Technically, you can use as many tasks you want.

But Tolokers don't like to take lengthy tasks. They'd rather do 10 tasks that take one minute each than one task that takes 10 minutes.

In addition, if you use a large number of tasks on the page, there might be issues with uploading the files to be labeled. This problem might occur with images.

The third thing to consider is quality control and manual review. If you allow recompletion of assignments by banned Tolokers, you should split the task into smaller parts so that fewer assignments are recompleted. You are more likely to meet your budget this way.

{% endcut %}

{% cut "I have a task for photo classification. When there are more than 5 photos on the page, why does Toloka split them across 2 pages?" %}

Toloka will group the uploaded image links in the file into suites depending on the task distribution method you use. For more information, see [Ways to group tasks in suites](distribute-tasks-by-pages.md).

{% endcut %}

{% cut "What is the difference between "task" and "task_suite"?" %}

A task means a separate task. A task suite means a page with tasks. The Toloker gets paid for a task suite.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}