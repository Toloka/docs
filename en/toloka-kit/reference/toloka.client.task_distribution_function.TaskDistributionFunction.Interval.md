# Interval
`toloka.client.task_distribution_function.TaskDistributionFunction.Interval` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/task_distribution_function.py#L37)

```python
Interval(
    self,
    *,
    from_: Optional[int] = None,
    to: Optional[int] = None,
    frequency: Optional[int] = None
)
```

A count interval with associated frequency value.


If the number of tasks is in the interval then the task distribution uses the interval frequency.

The value of the `frequency` parameter encodes a period in a task sequence.
For example, if `frequency` is 3, then the 1st, 4th, 7th tasks are selected. And so on.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`from_`|**Optional\[int\]**|<p>The lower bound of the interval. Allowed values: up to 1,000,000.</p>
`to`|**Optional\[int\]**|<p>The upper bound of the interval. Allowed values: up to 1,000,000.</p>
`frequency`|**Optional\[int\]**|<p>The frequency of tasks within an interval. Allowed values: from 1 to 10,000,000.</p>
