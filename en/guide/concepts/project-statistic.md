# Project statistics

To view the graphs, go to the project and open the **Statistics** tab.

#|
|| Field  | Overview ||
||**Open pools** | The number of open [pools](../../glossary.md#pool).||
||**Pools (total)** | The total number of pools.||
||**Submitted responses** | The total number of completed [task suites](../../glossary.md#task-suite) (taking [overlap](../../glossary.md#overlap) into account).

There may be few completed tasks if your tasks are only available to a small number of Tolokers. This could be due to incorrectly configured [filters](filters.md) or [skills](nav.md). In this case, some Tolokers don't see your tasks.

It's also possible that training is too complicated or training settings are incorrect.

{% cut "Recommendations" %}

It there are fewer completed tasks than expected, we recommend that you check the number of active Tolokers who can access your tasks. If there are none or very few, check Toloker filters, skill settings, and selection pools.

Also, try checking how this parameter might be related to the number of interested Tolokers, task completion time, and the number of banned Tolokers.

{% endcut %}
||
||**Assignments** | The graph shows the number of tasks by type:

- **Submitted** — The number of task suites submitted for review in all pools.

- **Accepted**— The number of accepted task suites in all pools.

- **Skipped** — The number of task suites [skipped by Tolokers](pool_statistic-pool.md#skipped-tasks).

- **Expired** — The number of expired task suites. Includes the pages that Tolokers failed to complete on time or decided to skip.

{% cut "Recommendations" %}

If you have a lot of skipped or expired tasks, we recommend that you read our [Tips for designing tasks](faq.md) and set up the [skipped assignments](skipped-assignments.md) rule.

{% endcut %}
||
||**Average overlap** | The average number of Tolokers who completed the same task in the project.

{% cut "Recommendations" %}

If you think that this number is too large or small, you may have incorrectly configured [Recompletion of assignments from banned Tolokers](restore-task-overlap.md) or [Processing rejected and accepted tasks](reassessment-after-accepting.md). You may also want to check:

- [Dynamic overlap](dynamic-overlap.md) (incremental relabeling, IRL).
- [Random majority vote check](selective-mvote.md).

{% endcut %}
||
||**Task completion time** | The average time spent on one task suite across all project pools. Specified in seconds.||
||**Spent (+ fee)** | The total amount of money spent on the project. The [fee](budget.md) amount is shown in parentheses.

{% cut "Recommendations" %}

If you spent more than you planned, check the price settings in the pool and the quality control rules. For example, [Dynamic pricing](dynamic-pricing.md#section_ucl_3hl_vlb) and [Recompletion of assignments from banned Tolokers](restore-task-overlap.md) increase the cost of the pool.

Disable rules that increase overlap and then revise the price per task suite. You might need to decrease it, but don't make it unreasonably small.

You can also increase or decrease the number of tasks per suite and adjust the price accordingly.

{% endcut %}
||
||**Spending (excluding fee)** | The graph shows the amount of money spent without the fee:

- **Spending on bonuses** — The amount of money spent on extra rewards.

- **Spending on assignments** — The amount of money spent on tasks.||
||**Average task price** | The average price in USD per general task in the project, including overlap.

Note that this is the price per task, not per suite with overlap. The Toloka fee isn't taken into account when calculating the average task price.

{% cut "Recommendations" %}

If you think that the price is too high, check the price settings in the pool and the quality control rules. For example, [Dynamic pricing](dynamic-pricing.md#section_ucl_3hl_vlb) and [Recompletion of assignments from banned Tolokers](restore-task-overlap.md) increase the cost of the pool.

{% endcut %}
||
||**Earnings per hour** | Average Toloker earnings per hour of data labeling in the project, in US dollars. Earnings are calculated for all tasks in the project and include extra rewards for tasks.||
||**Banned Tolokers** | The number of Tolokers who are blocked from accessing the project.||
||**Quality on control tasks and training tasks** | This graph shows the percentage of correct responses in the control and training tasks.

{% cut "Recommendations" %}

If the percentage is too low, maybe your tasks are too complicated or the instructions are not clear enough.

Maybe there are errors in the control tasks or they are irrelevant. If the tasks have links, make sure that they work.

Another possible reason is incorrect settings for the quality control rules. Maybe they fail to filter negligent Tolokers.

{% endcut %}
||
||**Blocked by rules** | The number of Tolokers banned by the quality control rules.

Note that the number of Tolokers is counted separately for each rule.

{% cut "Recommendations" %}

If the number is too large or too small, check the settings for the quality control rules.

{% endcut %}
||
||**Banned Tolokers** | The graph shows two indicators:

- **On the project** — Number of Tolokers banned from the project.
- **By the requester** — Number of Tolokers blocked by the requester.

Note that the graph only shows banned Tolokers. It doesn't include Tolokers whose access is suspended.

{% cut "Recommendations" %}

If there are too many blocked Tolokers, review and adjust the quality control rules.

{% endcut %}
||
||**Active Tolokers** | The number of Tolokers who started at least one task suite within the last hour and have access to the [project](../../glossary.md#project).||
||**Interested in pool** | The number of Tolokers who started or completed at least one task suite.

It includes both interested and engaged Tolokers.

{% cut "Recommendations" %}

If there is a large difference between the numbers of interested and engaged Tolokers, perhaps the instructions are unclear, the task is too complicated, or there are errors in the interface.

{% endcut %}
||
||**Submitted in pool** | The number of Tolokers who completed at least one task suite.

{% cut "Recommendations" %}

If this number is low but you're satisfied with the number of properly completed tasks, it means that you set up the project correctly.

{% endcut %}
||
||**Tolokers completing tasks in the project** | The total number of Tolokers who completed tasks in the project.

{% cut "Recommendations" %}

If the number is too small, check the instructions, quality control rules, and filters. Perhaps Tolokers find the task too difficult or can't access it due to incorrect settings.

{% endcut %}
||
|#

## Troubleshooting {#troubleshooting}

{% include [faq-quality-stat](../_includes/faq/result-questions/quality-stat.md) %}

{% include [contact-support](../_includes/contact-support.md) %}