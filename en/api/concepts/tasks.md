# Overview

In order to upload tasks to a pool, you need to create JSON objects that contain:

- The input data for the tasks (such as text or image URLs).
- Correct responses (for control tasks).
- Hints (for training tasks).

Toloka automatically combines tasks into suites. You only need to specify the number of tasks to include in each suite (the `mixer_config` key in the [pool](pool.md)).

If you want to create the task suites yourself, follow the instructions in [Overview](task-suite.md).

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
POST | [/tasks](create-task.md) | Creates one or multiple tasks.
POST | [/tasks](create-tasks-batch.md) | Creates multiple tasks.
GET | [/tasks/<task_id>](get-task.md) | Gets task data.
GET | [/tasks](get-tasks-list.md) | Gets the list of tasks in the pool.
PATCH | [/tasks/<task_id>](edit-task-overlap.md) | Changes the task overlap.
PATCH | [/tasks/<task_id>/set-overlap-or-min](set-min-task-overlap.md) | Stops assigning a task to Tolokers.

## Merging tasks {#task-merge}

Tasks with identical input data can be merged. This allows you to save money if the same task was uploaded to different pools.

{% note alert %}

- You can only merge tasks in open pools. If a new pool got a task that was previously completed in a pool that has been closed or archived, the tasks won't be merged.
- You can only merge your general tasks.

{% endnote %}

The response to the task received will be automatically assigned to another task if:

- Both tasks have the same input data.
- The tasks are located in different pools of the same project.
- An identical task is available to the Toloker responding.
- It has fewer responses than the overlap.

The response will be recorded with a zero price, and the overlap will be reduced by one.

This option is only available for general tasks without  automatic acceptance that were uploaded using ["smart mixing"](https://toloka.ai/docs/guide/concepts/task_upload.html).

To activate task merging in a  project, specify `"assignments_automerge_enabled": true` in the [project](project.md).

## Learn more {#links}

For more information about creating task suites, see the [Requester's guide](https://toloka.ai/docs/guide/concepts/pool-main.html).