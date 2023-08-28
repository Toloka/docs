# AggregatedSolution
`toloka.client.aggregation.AggregatedSolution` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/aggregation.py#L106)

```python
AggregatedSolution(
    self,
    *,
    pool_id: Optional[str] = None,
    task_id: Optional[str] = None,
    confidence: Optional[float] = None,
    output_values: Optional[Dict[str, Any]] = None
)
```

An aggregated response to a task.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**Optional\[str\]**|<p>The ID of the pool containing the task.</p>
`task_id`|**Optional\[str\]**|<p>The ID of the task.</p>
`confidence`|**Optional\[float\]**|<p>The confidence level for the aggregated response.</p>
`output_values`|**Optional\[Dict\[str, Any\]\]**|<p>Output data fields with aggregated responses.</p>

**Examples:**


```python
aggregated = toloka_client.aggregate_solutions_by_task(
    pool_id='1238218',
    task_id='000012e4ca--62e97a75dbab805456309d81',
    answer_weight_skill_id='12648',
    fields=[toloka.client.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
)
print(aggregated.output_values['result'], aggregated.confidence)
```
