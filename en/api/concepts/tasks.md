# Overview

## Description {#description}

To upload tasks to a pool, you need to create JSON objects that contain:

- The input data for the tasks (such as text or image URLs).
- Correct responses (for control tasks).
- Hints (for training tasks).

Toloka automatically combines tasks into suites. You only need to specify the number of tasks to include in each suite (the `mixer_config` key in the [pool](pool.md)).

If you want to create the task suites yourself, follow the instructions in [Overview](task-suite.md).

## Methods {#methods}

#|
||**Method** | **Endpoint** | **Description**||
||POST | [/tasks](create-task.md) |{% include [create-task-create](../_includes/concepts/create-task/id-create-task/create.md) %}||
||POST | [/tasks](create-task.md) |{% include [create-tasks-batch-create](../_includes/concepts/create-tasks-batch/id-create-tasks-batch/create.md) %}||
||GET | [/tasks/<task_id>](get-task.md) |{% include [get-task-get](../_includes/concepts/get-task/id-get-task/get.md) %}||
||GET | [/tasks](get-tasks-list.md) |{% include [get-tasks-list-get-list](../_includes/concepts/get-tasks-list/id-get-tasks-list/get-list.md) %}||
||PATCH | [/tasks/<task_id>](edit-task-overlap.md) |{% include [edit-task-overlap-edit-overlap](../_includes/concepts/edit-task-overlap/id-edit-task-overlap/edit-overlap.md) %}||
||PATCH | [/tasks/<task_id>/set-overlap-or-min](set-min-task-overlap.md) |{% include [set-min-task-overlap-set-min-overlap](../_includes/concepts/set-min-task-overlap/id-set-min-task-overlap/set-min-overlap.md) %}||
|#

## Merging tasks {#task-merge}

{% note alert %}

- You can only merge tasks with identical input data. The order of fields in the JSON object must also match.
- You can only merge tasks in open pools. If a new pool got a task that was previously completed in a pool that has been closed or archived, the tasks won't be merged.
- You can only merge your general tasks.

{% endnote %}

Merging saves you money if the same task was uploaded to different pools.

The response to the task received will be automatically assigned to another task if:

- Both tasks have the same input data.
- The tasks are located in different pools of the same project.
- An identical task is available to the Toloker responding.
- It has fewer responses than the overlap.

The response will be recorded with a zero price, and the overlap will be reduced by one.

This option is only available for general tasks without  non-automatic acceptance that were uploaded using ["smart mixing"]({{ requester-task-upload }}).

To activate task merging in a  project, specify `"assignments_automerge_enabled": true` in the [project](project.md).

## Learn more {#links}

For more information about creating task suites, see the [Requester's guide]({{ requester-pool-main }}).

