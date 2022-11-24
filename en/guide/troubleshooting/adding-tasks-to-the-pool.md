# Adding tasks to a pool

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Uploading tasks {#concept_iy1_3kh_5mb}

{% cut "Why does the preview display all the photos from the file with tasks at once?" %}

You must use a separate row for each task in your file with tasks. For more information, see [here](../concepts/pool_csv.md).

When you create a pool, the pool will have settings for the number of tasks per suite.

{% endcut %}

{% cut "The system interprets commas inside my array elements as separators between the array elements. How do I avoid this?" %}

Escape commas with a backslash (`\`).

{% endcut %}

{% cut "Why do double quotes disappear from the output if I try to escape them using quotation marks?" %}

If you have one word enclosed in quotes, format the uploaded assignment like this: `"How many letters are there in the word ""Liechtenstein"""`. If you are escaping quotes inside your text, then the entire text must be enclosed in quotes. For more information, see the [Guide](../concepts/pool_csv.md#string).

{% endcut %}

{% cut "Why haven't I received assignments since I launched my first project, and all the uploaded assignments are marked as "Training"?" %}

Check the `hint` field. For the general tasks, this field must be empty.

{% endcut %}

{% cut "Why do I see a syntax error when I upload a task where a user has to view an image and write feedback?" %}

The error might occur if the expected input type is URL, but a string is received.

There may be two reasons:

- The input field has the "link" type.

- The pool was created for an outdated project version. It means that the pool was created before you changed the input field type.

{% endcut %}

{% cut "I have a task for photo classification. When there are more than 5 photos on the page, why does Toloka split them across 2 pages?" %}

Toloka will split the links to images in the uploaded file into task suites depending on the method you specified when uploading the file. For more information, see the [Guide](../concepts/distribute-tasks-by-pages.md).

{% endcut %}

## Errors in column headers

If the [column headings](../concepts/pool_csv.md) are incorrect, the whole file is rejected. Otherwise, Toloka specifies the number of tasks with processing errors.

## Processing errors tables

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
- String values with tab characters are enclosed in [quotation marks](../concepts/pool_csv.md#string) `" "`.
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

{% endcut %}

{% cut "The same task appeared on different pages" %}

The same task may appear on different pages if:

- Dynamic overlap is used (incremental relabeling, IRL). As an example, let's say there were 5 tasks on a page. For 4 of them, responses coincided and the common response was counted as correct. The fifth task was mixed into another set because it didn't get into the final response and it needs to be “reassessed”.

- Different tasks have different overlap. Tasks with higher overlap will be additionally shown in sets with the other remaining tasks in the pool.

- If a [quality control rule](../../glossary.md#quality-control-rule) changes a task's overlap, it will appear in a different set.

{% endcut %}

[Other questions](support.md#help)

## Training-exam-retry {#concept_i2g_kkh_5mb}

{% cut "More Tolokers were trained than the training skill shows" %}

The pool shows the total number of Tolokers that completed at least one assignment. A training skill can be lost over time if you set [repeated training](../concepts/train.md) in the pool settings. This setting allows a Toloker to pass the training again after a certain period if the Toloker didn't complete any tasks in associated pools or if there was a large time gap between completing tasks (for example, because of a [ban](../../glossary.md#banning-tolokers)). The training skill displays the Tolokers who either recently completed training, or regularly complete your tasks so that the skill doesn't expire.

{% endcut %}

{% cut "Why do I have an infinite number of pages in the training pool?" %}

Tasks have infinite overlap in the training pool. As long as the training pool is open and the training is running, users can access the tasks. Learn more about [training pools](../concepts/train.md).

{% endcut %}

[Other questions](support.md#help)

{% include [contact-support](../_includes/contact-support-help.md) %}