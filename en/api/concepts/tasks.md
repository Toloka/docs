# Merging tasks

Merging saves you money if the same task was uploaded to different pools.

{% note alert "Restriction" %}

- You can only merge tasks with **identical input data**. The order of fields in the JSON object must also match.

- You can only merge tasks in **open pools**. If a new pool got a task that was previously completed in a pool that has been closed or archived, the tasks won't be merged.

- You can only merge **general tasks**.

{% endnote %}

The task response will be automatically assigned to another task if:

- Both tasks have the same input data.
- The tasks are located in different pools of the same project.
- An identical task is available to the Tolokers and has fewer task responses than the overlap.

The response will be recorded with a zero price, and the overlap will be reduced by one.

This option is only available for general tasks without manual review that were uploaded using ["smart mixing"](../../guide/concepts/distribute-tasks-by-pages.md#smart-mixing).

To activate task merging in a project, specify `"assignments_automerge_enabled": true` in the [project](https://toloka.ai/docs/api/api-reference/#tag--project).

## See also {#see-also}

- [{#T}](../../guide/concepts/pool.md)
- [{#T}](../../guide/concepts/task_upload.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}