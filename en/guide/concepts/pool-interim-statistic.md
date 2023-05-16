# Interim statistics

For your convenience, we put all key statistics on the main pool page. For detailed statistics, see [Pool statistics](pool_statistic-pool.md).

#|
|| **Field**  | **Overview**||
||**Task suites** | The total number of task suites (pages) in the pool.||
||**Tasks** | The total number of tasks in the pool.||
||**Training tasks** | The number of training tasks in the pool.||
||**Control tasks** | The number of [control tasks](../../glossary.md#control-task) in the pool.||
||**Average assignment submit time** | The average time for completing a [task suite](../../glossary.md#task-suite) in the pool. Specified in seconds.

Calculated based on 1000 recently completed task suites.||
||**Approximate finish time** | The anticipated time for finishing tasks, in days and hours. Calculated using the average time per task suite.

Formula: $T_{left}={Assign_{left}}\times{T_{assign}}$,

where:

$Assign_{left}$ is the number of task suite remaining uncompleted or those completed with insufficient [overlap](../../glossary.md#overlap).

$T_{assign}$ is the average time per task suite. Calculated based on the amount of time since the pool opened and the number of task suites completed.

The time is updated as task suites are completed by Tolokers.||
||**Budget spent (+ fee)** | The amount of money spent in the pool. The [fee](budget.md) amount is shown in parentheses.||
||**Approximate budget (+ fee)** | The amount of money spent and expected costs (if all the tasks are completed and all responses are approved). The [fee](../../glossary.md#fee) amount is shown in parentheses.||
||**Active Tolokers with access to pool** | The number of Tolokers selected for the pool with [filters](filters.md). The number includes only Tolokers who viewed and completed tasks in Toloka in the recent hour.||
||**Interested in pool** | The number of Tolokers who started or completed at least one task suite.

It includes both interested and engaged Tolokers.||
||**Submitted in pool** | The number of Tolokers who completed at least one task suite.||
||**Submitted assignments per Toloker** | The average number of task suites per Toloker.||
||**Expired task suites** | The number of expired task suites.

Includes the pages that Tolokers failed to complete on time. You specify the time allotted for a task suite when [setting up a pool](pool-main.md#table_n3q_vhz_jlb).

The task can also get the expired status when the Toloker clicks **Exit**. In this case, the Toloker can return to the task again, unless it was completed by someone else or the requester deleted it from the pool.||
||**Skipped task suites** | The number of task suites skipped by Tolokers. Includes the pages that the Tolokers decided to skip and moved on to the next tasks.

When the Toloker clicks **Skip**, the task gets the skipped status. In this case, the Toloker can no longer return to the task.||
|#

{% include [contact-support](../_includes/contact-support.md) %}