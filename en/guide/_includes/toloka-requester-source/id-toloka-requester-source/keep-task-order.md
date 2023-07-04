#### Option disabled (default value)

The uploaded tasks are grouped in suites and given to Tolokers in random order. Within the suite, the task order is always random.

{% cut "Example" %}

If you specified 2 tasks per suite when uploading the [file](../../../../glossary.md#tsv) with image links to the pool, the system can generate them as follows:

Tasks in the file | Page 1 | Page 2 | Page 3
----- | ----- | ----- | -----
Image 1 | Image 2 | Image 6 | Image 4
Image 2 | Image 5 | Image 1 | Image 3
Image 3 |  |  |
Image 4 |  |  |
Image 5 |  |  |
Image 6 |  |  |

{% endcut %}

#### Option enabled

Tasks will be grouped on suites in the order they are listed in the task file.

{% cut "Example" %}

If you specified 2 tasks per suite when uploading the file with image links to the pool, you're equally likely to get suites where the first link goes first and the second goes second, and the other way around:

Tasks in the file | Page 1 | Page 2 | Page 3
----- | ----- | ----- | -----
Image 1 | Image 1 | Image 3 | Image 5
Image 2 | Image 2 | Image 4 | Image 6
Image 3 | _or_ | _or_ | _or_
Image 4 | Image 2 | Image 4 | Image 6
Image 5 | Image 1 | Image 3 | Image 5
Image 6 |  |  |

{% endcut %}

If the pool has an overlap, the next task is distributed only when the previous task is completed by the necessary number of Tolokers.

Use this parameter to:

- Speed up collection of responses for [majority vote](../../../../guide/concepts/mvote.md) check.

- Assign tasks by priority.

    Put important tasks in the beginning of the file. They will be completed faster and with the necessary overlap.