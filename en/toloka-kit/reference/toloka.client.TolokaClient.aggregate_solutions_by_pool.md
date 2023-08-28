# aggregate_solutions_by_pool
`toloka.client.TolokaClient.aggregate_solutions_by_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L564)

Starts aggregation of responses in all completed tasks in a pool.


The method starts the aggregation process on the Toloka server. To wait for the completion of the operation use the [wait_operation](toloka.client.TolokaClient.wait_operation.md) method.

{% note tip %}

Try [crowd-kit library](https://toloka.ai/docs/crowd-kit). It has many aggregation methods and executes on your computer.

{% endnote %}

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`type`|**Union\[[AggregatedSolutionType](toloka.client.aggregation.AggregatedSolutionType.md), str, None\]**|<p>Aggregation model:</p> <ul> <li>`WEIGHTED_DYNAMIC_OVERLAP` — [Aggregation](https://toloka.ai/docs/guide/result-aggregation#aggr-by-skill) based on Tolokers' skill in a pool with a dynamic overlap.</li> <li>`DAWID_SKENE` — [Dawid-Skene aggregation model](https://toloka.ai/docs/guide/result-aggregation#dawid-skene). It is used in pools without a dynamic overlap.</li> </ul>
`pool_id`|**Optional\[str\]**|<p>The ID of the pool.</p>
`answer_weight_skill_id`|**Optional\[str\]**|<p>The ID of the skill that determines the weight of the Toloker's responses.</p>
`fields`|**Optional\[List\[[PoolAggregatedSolutionRequest.Field](toloka.client.aggregation.PoolAggregatedSolutionRequest.Field.md)\]\]**|<p>Output data fields to aggregate. For the best results, each of these fields should have limited number of response options. If the `DAWID_SKENE` aggregation type is selected, you can only specify one value.</p>

* **Returns:**

  An object to track the progress of the operation.

* **Return type:**

  [AggregatedSolutionOperation](toloka.client.operations.AggregatedSolutionOperation.md)

**Examples:**

The example shows how to aggregate responses in a pool.

```python
aggregation_operation = toloka_client.aggregate_solutions_by_pool(
        type=toloka.client.aggregation.AggregatedSolutionType.WEIGHTED_DYNAMIC_OVERLAP,
        pool_id='36502086',
        answer_weight_skill_id='11294',
        fields=[toloka.client.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
    )
aggregation_operation = toloka_client.wait_operation(aggregation_operation)
aggregation_results = list(toloka_client.get_aggregated_solutions(aggregation_operation.id))
```
