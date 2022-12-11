# Working with results

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Aggregation {#results}

{% cut "Why does the Dawid-Skene aggregation model return a result that the Tolokers didn't select?" %}

The method doesn't guarantee that original Toloker responses will be used for aggregation. The algorithm takes into account Tolokers' quality parameters and response patterns. Consequently, it can return a result that's different from the Tolokers' responses to this task.

{% endcut %}

{% cut "Why might aggregation by Toloker skill be unavailable?" %}

You cannot aggregate by project fields that have no valid values. Specify the possible values for all the fields of all types.

{% endcut %}

{% cut "You can't aggregate by skill. When running via the API, I get the error code `ONLY_FOR_POOL_WITH_MIXER`. Why?" %}

You need to use [smart mixing](../concepts/task_upload.md#smart-mixing_1).

{% endcut %}

## Processing the results file {#results_1}

{% cut "Why do I get blank spaces inside my TSV file?" %}

When you upload a file with rows, double quotes indicate an area where you can use special characters (tabs or line breaks). Toloka merges everything in between the quotes into one row to make up one task. To use double quotes inside such an area, you need to escape them with another quote. [Read more here](../concepts/pool_csv.md#string).

{% endcut %}

## Assignment review {#results_2}

{% cut "What should I do if I want to accept a completed task but the pool is already archived or the Toloker wrote to me after the allowed time?" %}

Simply [give the Toloker a separate reward](../concepts/bonus.md) without changing the task status. You can't change the task status in the pool in this case.

{% endcut %}

{% cut "What should I do if I rejected a task for a reason that isn't specified in the instructions?" %}

Accept the task and update the instructions. Otherwise, you violate the [**Requester Agreement**]({{ customeragreement }}) that requires to clearly state the task requirements and the results expected from the Toloker.

{% endcut %}

{% cut "How can I increase the project's rating?" %}

The project rating is the average rating across all categories. Pay particular attention to the categories for which you got the least points.

{% endcut %}

{% cut "Low rating for “Will you take similar tasks in the future”" %}

Perhaps the Tolokers found your tasks too difficult. Try to simplify them.

{% endcut %}

{% cut "Low rating for “Clarity of instructions”" %}

Shorten instructions and rewrite using simpler language. Add pictures and examples.

{% endcut %}

{% cut "Low rating for “Task interface usability”" %}

Make the interface [more user-friendly](../concepts/spec.md) and don't make the Toloker complete unnecessary actions. Use keyboard shortcuts.

Starting from December 15, 2021, tasks in pools are automatically available in the web version of Toloka and the mobile app. If your task isn't available on mobile devices, it means that you might have forgotten to add the {% if locale == "en-com" %}**Client**{% endif %} filter.

{% endcut %}

{% cut "Low rating for “Communication with the requester”" %}

Reply to [messages from Tolokers](../concepts/messaging.md) regularly. Try to provide feedback as fast as possible. Correct errors promptly and use mailing lists to notify Tolokers of changes.
If you don't understand what the problem is, run a mini-survey and ask the Tolokers who completed your tasks what they like and what they don't like.

{% endcut %}

[Other questions](troubleshooting.md)

{% include [contact-support](../_includes/contact-support.md) %}