{% cut "I add tasks to the pool via the create task method, but tasks are not created. What is the reason?" %}

You can upload tasks with the help of [create task](https://toloka.ai/docs/api/api-reference/#post-/tasks) method to the pool that uses smart mixing only. If you want to use a pool without smart mixing, use the [create task suite](https://toloka.ai/docs/api/api-reference/#post-/task-suites) method.

{% endcut %}