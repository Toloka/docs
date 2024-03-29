# PoolAggregatedSolutionRequest
`toloka.client.aggregation.PoolAggregatedSolutionRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/aggregation.py#L31)

```python
PoolAggregatedSolutionRequest(
    self,
    *,
    type: Union[AggregatedSolutionType, str, None] = None,
    pool_id: Optional[str] = None,
    answer_weight_skill_id: Optional[str] = None,
    fields: Optional[List[Field]] = None
)
```

Parameters for aggregating results in a pool using the [aggregate_solutions_by_pool](toloka.client.TolokaClient.aggregate_solutions_by_pool.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`type`|**Optional\[[AggregatedSolutionType](toloka.client.aggregation.AggregatedSolutionType.md)\]**|<p>Aggregation model:</p> <ul> <li>`WEIGHTED_DYNAMIC_OVERLAP` — [Aggregation](https://toloka.ai/docs/guide/result-aggregation#aggr-by-skill) based on Tolokers' skill in a pool with a dynamic overlap.</li> <li>`DAWID_SKENE` — [Dawid-Skene aggregation model](https://toloka.ai/docs/guide/result-aggregation#dawid-skene). It is used in pools without a dynamic overlap.</li> </ul>
`pool_id`|**Optional\[str\]**|<p>The ID of the pool.</p>
`answer_weight_skill_id`|**Optional\[str\]**|<p>The ID of the skill that determines the weight of the Toloker's responses.</p>
`fields`|**Optional\[List\[[Field](toloka.client.aggregation.PoolAggregatedSolutionRequest.Field.md)\]\]**|<p>Output data fields to aggregate. For the best results, each of these fields should have limited number of response options. If the `DAWID_SKENE` aggregation type is selected, you can only specify one value.</p>

**Examples:**


```python
aggregation_operation = toloka_client.aggregate_solutions_by_pool(
    type=toloka.client.aggregation.AggregatedSolutionType.WEIGHTED_DYNAMIC_OVERLAP,
    pool_id='1080020',
    answer_weight_skill_id='11294',
    fields=[toloka.client.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
)
aggregation_operation = toloka_client.wait_operation(aggregation_operation)
aggregation_results = list(toloka_client.get_aggregated_solutions(aggregation_operation.id))
```
