# AggregatedSolution
`toloka.client.aggregation.AggregatedSolution` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/aggregation.py#L85)

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
