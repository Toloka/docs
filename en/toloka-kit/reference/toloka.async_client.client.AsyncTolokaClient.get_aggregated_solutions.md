# get_aggregated_solutions
`toloka.async_client.client.AsyncTolokaClient.get_aggregated_solutions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L0)

Finds all aggregated responses that match certain criteria.


Pass to the `get_aggregated_solutions` the ID of the operation started by the [aggregate_solutions_by_pool](toloka.client.TolokaClient.aggregate_solutions_by_pool.md) method.

`get_aggregated_solutions` returns a generator. You can iterate over all found aggregated responses using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort aggregated responses use the [find_aggregated_solutions](toloka.client.TolokaClient.find_aggregated_solutions.md) method.

{% note tip %}

Try [crowd-kit library](https://toloka.ai/en/docs/crowd-kit). It has many aggregation methods and executes on your computer.

{% endnote %}

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**str**|<p>The ID of the aggregation operation.</p>
`task_id_lt`|**Optional\[str\]**|<p>Responses for tasks with IDs less than the specified value.</p>
`task_id_lte`|**Optional\[str\]**|<p>Responses for tasks with IDs less than or equal to the specified value.</p>
`task_id_gt`|**Optional\[str\]**|<p>Responses for tasks with IDs greater than the specified value.</p>
`task_id_gte`|**Optional\[str\]**|<p>Responses for tasks with IDs greater than or equal to the specified value.</p>
`batch_size`|**Optional\[int\]**|<p>Returned aggregated responses limit for each request. The default batch_size is 50. The maximum allowed limit is 100,000.</p>

* **Yields:**

  The next matching aggregated response.

* **Yield type:**

  [AsyncGenAdapter](toloka.util.async_utils.AsyncGenAdapter.md)\[[AggregatedSolution](toloka.client.aggregation.AggregatedSolution.md), None\]

**Examples:**

The example shows how to aggregate responses in a pool.

```python
aggregation_operation = toloka_client.aggregate_solutions_by_pool(
    type=toloka.aggregation.AggregatedSolutionType.WEIGHTED_DYNAMIC_OVERLAP,
    pool_id=some_existing_pool_id,
    answer_weight_skill_id=some_skill_id,
    fields=[toloka.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
)
aggregation_operation = toloka_client.wait_operation(aggregation_operation)
aggregation_results = list(toloka_client.get_aggregated_solutions(aggregation_operation.id))
```
