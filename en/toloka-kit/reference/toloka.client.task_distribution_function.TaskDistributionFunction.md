# TaskDistributionFunction
`toloka.client.task_distribution_function.TaskDistributionFunction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/task_distribution_function.py#L9)

```python
TaskDistributionFunction(
    self,
    *,
    scope: Union[Scope, str, None] = None,
    distribution: Union[Distribution, str, None] = None,
    window_days: Optional[int] = None,
    intervals: Optional[List[Interval]] = None
)
```

A configuration of selecting tasks.


It is used:
- To control the selection of tasks for the selective majority vote checks.
- To change the frequency of assigning control or training tasks.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`scope`|**Optional\[[Scope](toloka.client.task_distribution_function.TaskDistributionFunction.Scope.md)\]**|<p>A way of counting tasks completed by a Toloker:</p> <ul> <li>`POOL` — Completed pool tasks are counted.</li> <li>`PROJECT` — All completed project tasks are counted.</li> </ul>
`distribution`|**Optional\[[Distribution](toloka.client.task_distribution_function.TaskDistributionFunction.Distribution.md)\]**|<p>The distribution of selected tasks within an interval. Allowed values: `UNIFORM`.</p>
`window_days`|**Optional\[int\]**|<p>The number of days in which completed tasks are counted. Allowed values: from 1 to 365.</p>
`intervals`|**Optional\[List\[[Interval](toloka.client.task_distribution_function.TaskDistributionFunction.Interval.md)\]\]**|<p>A list of count intervals with frequency values. The maximum number of list items is 10,000.</p>
