# Overview

A task suite is a set of tasks grouped on a single web page. If the tasks are simple, you can add 10–20 tasks per suite. Don't make task suites too long because it slows down the loading speed for Tolokers.

To create a task suite, upload JSON containing:

- Input data for tasks (such as text or image URLs).
- Correct responses (for control tasks).
- Hints (for training tasks).
- Parameters for assigning tasks.

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
POST | [/task-suites](create-task-suite.md) | Creates one or multiple task suites.
POST | [/task-suites](create-task-suite-batch.md) | Creates multiple task suites.
GET | [/task-suites](get-task-suite-list.md) | Gets the list of task suites in the pool.
GET | [/task-suites/<task_suite_id>](get-task-suite.md) | Gets a task suite.
PATCH | [/task-suites/<task_suite_id>](edit-overlap.md) | Changes task suite overlap.
PATCH | [/task-suites/<task_suite_id>](edit-order.md) | Changes the priority of a task suite in the pool.
PATCH | [/task-suites/<task_suite_id>/set-overlap-or-min](set-min-suite-overlap.md) | Stops assigning a task suite to Tolokers.

## See also {#see-also}

- [{#T}](../../guide/concepts/distribute-tasks-by-pages.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}