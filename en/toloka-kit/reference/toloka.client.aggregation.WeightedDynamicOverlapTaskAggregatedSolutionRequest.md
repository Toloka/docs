# WeightedDynamicOverlapTaskAggregatedSolutionRequest
`toloka.client.aggregation.WeightedDynamicOverlapTaskAggregatedSolutionRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/aggregation.py#L65)

```python
WeightedDynamicOverlapTaskAggregatedSolutionRequest(
    self,
    *,
    task_id: Optional[str] = None,
    pool_id: Optional[str] = None,
    answer_weight_skill_id: Optional[str] = None,
    fields: Optional[List[Field]] = None
)
```

Parameters to run weighted aggregation for a single task with a dynamic overlap.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_id`|**Optional\[str\]**|<p>The ID of the task.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of the pool containing the task.</p>
`answer_weight_skill_id`|**Optional\[str\]**|<p>The ID of the skill that determines the weight of the Toloker&#x27;s responses.</p>
`fields`|**Optional\[List\[[Field](toloka.client.aggregation.WeightedDynamicOverlapTaskAggregatedSolutionRequest.Field.md)\]\]**|<p>Output data fields to aggregate. For the best results, each of these fields should have limited number of response options. If the `DAWID_SKENE` aggregation type is selected, you can only specify one value.</p>
