# Pool statistics

You can track task completion on the [pool](../../glossary.md#pool) page or by clicking **Statistics**. You can also get notifications by email, in the browser or on the **Messages** page. In the [Profile]({{ profile }}), open the **Notifications** tab and choose which notifications you want to receive and how you want to receive them.

#|
|| **Field** | **Overview**||
||**Approximate completion time** | The anticipated time for finishing tasks, in days and hours. Calculated using the average time per task suite.

Formula: $T_{left}={Assign_{left}}\times{T_{assign}}$,

where:

- $Assign_{left}$ is the number of task suite remaining uncompleted or those completed with insufficient [overlap](../../glossary.md#overlap).

- $T_{assign}$ is the average time per task suite. Calculated based on the amount of time since the pool opened and the number of task suites completed.

The time is updated as task suites are completed by Tolokers.

{% cut "Recommendations" %}

- If the time is too long, it's likely you don't have enough Tolokers left in your project. Check the number of [active Tolokers](#active-users) and the average time per task suite.

- If the time has increased since the project started, you may have too many banned Tolokers.

- If the time started out long and it hasn't decreased, and the number of [active Tolokers](#active-users) is small, check the filter settings and training. Perhaps few people can see your tasks or Tolokers can't pass training.

{% endcut %}
||
||**Average assignment submit time** | The average time for completing a [task suite](../../glossary.md#task-suite) in the pool. Specified in seconds.

Calculated based on 1000 recently completed task suites.

{% cut "Recommendations" %}

If the average time is longer than you expected, and the quality of results is low, recheck the instructions.

Perhaps your tasks are too complicated. Use [decomposition](solution-architecture.md) and check the task interface. Then try testing your task on the same Tolokers in the training or survey format.

If the average time is short, and the quality of results is low, review [quality control settings](control.md).

{% endcut %}
||
||**Expired task suites** | The number of expired task suites.

Includes the pages that Tolokers failed to complete on time. You specify the time allotted for a task suite when [setting up a pool](pool-main.md#table_n3q_vhz_jlb).

The task can also get the expired status when the Toloker clicks **Exit**. In this case, the Toloker can return to the task again, unless it was completed by someone else or the requester deleted it from the pool.

{% cut "Recommendations" %}

Tolokers might click the **Exit** button because:

- Tasks are too complex.
- There are too many tasks on the page.
- Tasks don't work and Tolokers can't submit the assignments.
- Tolokers couldn't understand the instructions and task interface.

If you have a lot of expired task suites in your pool, we recommend that you read our [Tips for designing tasks](faq.md).

{% endcut %}
||
||**Skipped task suites** | The number of task suites skipped by Tolokers. Includes the pages that the Tolokers decided to skip and moved on to the next tasks.

When the Toloker clicks **Skip**, the task gets the skipped status. In this case, the Toloker can no longer return to the task.

{% cut "Recommendations" %}

If you have a lot of skipped task suites in your pool, we recommend that you read our [Tips for designing tasks](faq.md) and set up the [skipped assignments](skipped-assignments.md) rule.

{% endcut %}
||
||**Submit time** | The time between the start and completion of the pool. Displayed if all pool tasks are completed.||
||**Start date** | Pool start date||
||**Completion date** | The date when all pool tasks were completed.||
||**Assignments** | The graph shows the number of tasks by type:

- **Submitted** — The number of task suites submitted for review.

- **Accepted** — The number of accepted task suites.

- **Skipped** — The number of task suites [skipped by Tolokers](pool_statistic-pool.md#skipped-tasks).

- **Expired** — The number of expired task suites. Includes the pages that Tolokers failed to complete on time or decided to skip.

{% cut "Recommendations" %}

If you have a lot of skipped or expired tasks, we recommend that you read our [Tips for designing tasks](faq.md) and set up the [skipped assignments](skipped-assignments.md) rule.

{% endcut %}
||
||**Average overlap** | The average number of Tolokers who completed the same task in the pool.

{% cut "Recommendations" %}

If you think that this number is too large or small, you may have incorrectly configured [Recompletion of assignments from banned users](restore-task-overlap.md) or [Processing rejected and accepted tasks](reassessment-after-accepting.md). You may also want to check:

- [Dynamic overlap](dynamic-overlap.md) (incremental relabeling, IRL).

- [Selective majority vote check](selective-mvote.md).

{% endcut %}
||
||**Assignment submit time** | The average time spent by Tolokers to complete a task suite in the pool. Specified in seconds.||
||**Budget spent (+ fee)** | The amount of money spent in the pool. The [fee](budget.md) amount is shown in parentheses.

If you spent more than you planned, check the price settings in the pool and the quality control rules. For example, [Dynamic pricing](dynamic-pricing.md#section_ucl_3hl_vlb) and [Recompletion of assignments from banned users](restore-task-overlap.md) increase the cost of the pool.

{% cut "Recommendations" %}

First, check the [quality control rules](control.md), disable the rules that increase overlap, and then revise the price per task suite. You might need to reduce it, but don't make it unreasonably small.

You can also increase or decrease the number of tasks per suite and adjust the price accordingly.

{% endcut %}
||
||**Approximate budget (+ fee)** | The amount of money spent and expected costs (if all the tasks are completed and all responses are approved). The [fee](../../glossary.md#fee) amount is shown in parentheses.

{% cut "Recommendations" %}

This indicator uses available data to predict the total cost. If you are not satisfied with it, stop the pool and change the settings. Think about whether you need [dynamic overlap](dynamic-overlap.md), [dynamic pricing](dynamic-pricing.md), and, for example, [recompletion of assignments from banned users](restore-task-overlap.md).

Review the price per task suite. You might be able to lower it without losing Tolokers.

{% endcut %}
||
||**Spending (excluding fee)** | The graph shows the amount of money spent without the fee:

- **Spending on bonuses** — The amount of money spent on extra bonuses.

- **Spending on assignments** — The amount of money spent on tasks.||
||**Average cost per task** | The average price in USD per general task in the pool, including overlap.

Note that this is the price per task, not per suite with overlap.

{% cut "Recommendations" %}

If you think that the price is too high, check the price settings in the pool and the quality control rules. For example, [Dynamic pricing](dynamic-pricing.md#section_ucl_3hl_vlb) and [Recompletion of assignments from banned users](restore-task-overlap.md) increase the cost of the pool.

{% endcut %}
||
||**Earnings per hour** | Average Toloker earnings per hour of data labeling in the pool, in US dollars. Earnings include bonuses.||
||**Quality on control tasks and training tasks in the pool****Quality on control tasks and training tasks** | This graph shows the percentage of correct responses in the control and training tasks.

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
||**Banned Tolokers** | The total number of Tolokers banned in this pool.

The graph shows two indicators:

- **In the pool** — Number of Tolokers banned in the pool.
- **By the requester** — Number of Tolokers banned by the requester.

Note that the graph only shows banned Tolokers. It doesn't include Tolokers whose access is suspended.

{% cut "Recommendations" %}

If there are too many banned Tolokers, check the quality control rules. Maybe they are too strict.

{% endcut %}
||
||**Active Tolokers with access to the pool** | The number of Tolokers selected for the pool with [filters](filters.md). The number includes only Tolokers who viewed and completed tasks in Toloka in the last hour.

{% cut "Recommendations" %}

If this number is too small, check the filter settings and the quality control rules.

{% endcut %}
||
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
||**Submitted assignments per Toloker** | The average number of task suites per Toloker.

If your pool is large and it is taking a long time to finish it, but there are very few task suites per Toloker, you may have incorrectly configured quality control rules or filters.

{% cut "Recommendations" %}

If the number of task suites per Toloker is close to the threshold for triggering quality control rules, check the quality control rules that are used for banning Tolokers. You should also check the [banned Tolokers](#banned-users) and [banned by rules](#blocked-rules) graphs.

{% endcut %}
||
||**Tolokers completing tasks in the pool** | This graph shows the total number of Tolokers who completed at least one task suite in the pool.

{% cut "Recommendations" %}

If there aren't enough Tolokers, check the settings for the quality control rules and filters.

You should also check the [banned Tolokers](#banned-users) and [banned by rules](#blocked-rules) graphs.

{% endcut %}
||
|#

## Troubleshooting {#troubleshooting}

{% include [troubleshooting-speed-dropped](../_includes/troubleshooting/pool-setup/speed-dropped.md) %}

{% include [faq-labeling-speed](../_includes/faq/project-settings/labeling-speed.md) %}

{% include [faq-speed-up-completion](../_includes/faq/pool-setup/speed-up-completion.md) %}

{% include [troubleshooting-max-number](../_includes/troubleshooting/pool-setup/max-number.md) %}

{% include [contact-support](../_includes/contact-support.md) %}