# Working with results

{% note tip %}

If you are looking for the answer to a specific question, use **Ctrl+F** to search the page (**Cmd+F** on MacOS).

{% endnote %}

## Aggregation {#results}

{% cut "What is the difference between the confidence in the aggregated response in the Dawid-Skene aggregation model and the confidence in aggregation by skill?" %}

In the way it's calculated. In both aggregations, confidence means the same thing.

{% endcut %}

{% cut "How does the Dawid-Skene aggregation model work?" %}

The Dawid-Skene aggregation model analyzes the Toloker responses and creates a confusion matrix for each Toloker. This lets us evaluate the statistical significance of the Toloker in the context of each assignment. [Learn more about the model](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.469.1377&rep=rep1&type=pdf).

{% endcut %}

{% cut "Why does the Dawid-Skene aggregation model return a result that the Tolokers didn't select?" %}

The method doesn't guarantee that original Toloker responses will be used for aggregation. The algorithm takes into account Tolokers' quality parameters and response patterns. Consequently, it can return a result that's different from the Tolokers' responses to this task.

{% endcut %}

{% cut "Where do I see the aggregation progress?" %}

The pool page contains the {% if locale == "en-com" %}**List of Operations**{% endif %} button.

{% endcut %}

{% cut "Why might aggregation by Toloker skill be unavailable?" %}

You cannot aggregate by project fields that have no valid values. Specify the possible values for all the fields of all types.

{% endcut %}

{% cut "You can't aggregate by skill. When running via the API, I get the error code `ONLY_FOR_POOL_WITH_MIXER`. Why?" %}

You need to use [smart mixing](../concepts/task_upload.md#smart-mixing_1).

{% endcut %}

{% cut "Can I get notifications when results aggregation finishes?" %}

Yes. To set up notifications in your account, go to [Learn more about setting up notifications.](../concepts/result-aggregation.md#notification)

{% endcut %}

[Other questions](support.md#help)

## Processing the results file {#results_1}

{% cut "Why do I get blank spaces inside my TSV file?" %}

When you upload a file with rows, double quotes indicate an area where you can use special characters (tabs or line breaks). Toloka merges everything in between the quotes into one row to make up one task. To use double quotes inside such an area, you need to escape them with another quote. [Read more here](../concepts/pool_csv.md#string).

{% endcut %}

{% cut "What is the result of processing an empty text field?" %}

If a Toloker typed some text and then deleted it, the result is `null`, otherwise, it's `undefined`.

{% endcut %}

[Other questions](support.md#help)

## Assignment review {#results_2}

{% cut "How do I send an assignment back to the Toloker for revision?" %}

You can only accept or reject an assignment.

{% endcut %}

{% cut "Can I disable tasks for Tolokers who do a poor job on tasks?" %}

You can deny access to the pool if the Toloker's responses are [too fast](../concepts/quick-answers.md), if they don't match the [majority vote](../concepts/mvote.md), or if the Toloker makes too many mistakes in [control tasks](../concepts/goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](../concepts/restore-task-overlap.md).

{% endcut %}

{% cut "Can I fix something in a completed task myself?" %}

No, you can't fix anything in the task itself. However, you can do this manually in the results file.

{% endcut %}

{% cut "What should I do if I want to accept a completed task but the pool is already archived or the Toloker wrote to me after the allowed time?" %}

Simply [give the Toloker a separate reward](../concepts/bonus.md) without changing the task status. You can't change the task status in the pool in this case.

{% endcut %}

{% cut "What should I do if I rejected a task for a reason that isn't specified in the instructions?" %}

Accept the task and update the instructions. Otherwise, you violate the [**Requester Agreement**]({{ customeragreement }}) that requires to clearly state the task requirements and the results expected from the Toloker.

{% endcut %}

{% cut "Can I reject part of the responses on the page and accept part of them?" %}

No. For example, there are 10 tasks in a suite that costs $0.10, and the Toloker did 2 of them incorrectly.

You can't accept the correct answers and pay for this part ($0.08). Response pages are accepted or rejected in their entirety.

{% endcut %}

{% cut "How can I notify the Toloker of changes in the instructions?" %}

Add the notification to the project description (for example: “Attention! The instructions changed”) and send a message to all the people who completed your tasks. To do this:

- Assign them a hidden skill, or use an existing [skill](../concepts/nav-assign.md) linked to the pool.

- Go to **Messages** and click {% if locale == "en-com" %}**Write** → **Group** → **Add filter** → **Choose your skill** → **&lt;skill name&gt;**{% endif %}.

- If you created a new skill, specify the value you assigned to the chosen group, (for example, 1). If you use an existing skill, specify the minimum value.

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

[Other questions](support.md#help)

## Statistics {#results_3}

{% cut "What is the formula for calculating the percentage of pool completion?" %}

The percentage is calculated based on the total number of pages, including the overlap. If the pool uses smart mixing with control tasks, the maximum progress bar value and the currently completed percentage are calculated approximately.

{% endcut %}

{% cut "What happens to the tasks that have the `expired` or `skipped` status?" %}

They return to the pool until the full overlap is reached.

{% endcut %}

{% cut "How are the statistics for “Quality: training tasks” and “Quality: control tasks” calculated? Do they include the training tasks uploaded to the main pool?" %}

“Quality: training tasks” includes only the training pools linked to the main pools, but the control and training tasks uploaded to the main pools are counted in “Quality: control tasks”.

{% endcut %}

{% cut "Can I get the exact start and end time from the Toloker with the results of the task?" %}

When you download the results file, select the **Start time** and **Submit time** checkboxes. The downloaded file will include the exact UTC date and time when the Toloker accepted the assignment and submitted it.

{% endcut %}

[Other questions](support.md#help)

{% include [contact-support](../_includes/contact-support-help.md) %}