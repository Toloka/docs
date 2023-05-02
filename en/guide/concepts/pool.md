# Adding tasks to a pool

To add tasks to a pool:

1. [Place the files for tasks](cloud-storage.md).

1. [Create a file with tasks](pool_csv.md).

1. [Upload tasks to the pool](task_upload.md).

    {% note alert "Restriction" %}

    You can add up to one million tasks to the pool. To upload more tasks, create another pool.

    {% endnote %}

1. If you haven't yet marked up [control](../../glossary.md#control-task) and [training](../../glossary.md#training-task) tasks in the file, [mark up the tasks in the interface](task_markup.md).

    {% note info %}

    If you created a project in the [sandbox](../../glossary.md#sandbox), keep in mind that when you move a project to the [Toloka production version]({{ production-version }}), tasks aren't moved, including those that are already labeled.

    {% endnote %}

## What's next {#what_next}

- [Add a training pool](train.md).

- [Top up your account](refill.md).

- [Start the pool](pool-run-and-stop.md).

## For developers {#for-developers}

- [Toloka API: Tasks](https://toloka.ai/docs/api/api-reference/#tag--task)
- [Toloka-Kit: Creating tasks](../../toloka-kit/reference/toloka.client.TolokaClient.create_task.md)

{% include [contact-support](../_includes/contact-support.md) %}