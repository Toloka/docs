{% cut "The same task appeared on different pages" %}

The same task may appear on different pages if:

- Dynamic overlap is used (incremental relabeling, IRL). As an example, let's say there were 5 tasks on a page. For 4 of them, task responses coincided and the common response was counted as correct. The fifth task was mixed into another set because it didn't get into the final task response and it needs to be “reassessed”.

- Different tasks have different overlap. Tasks with higher overlap will be additionally shown in sets with the other remaining tasks in the pool.

- If a [quality control rule](../../../../glossary.md#quality-control-rule) changes a task's overlap, it will appear in a different set.

{% endcut %}