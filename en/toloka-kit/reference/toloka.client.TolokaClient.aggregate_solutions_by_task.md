# aggregate_solutions_by_task
`toloka.client.TolokaClient.aggregate_solutions_by_task` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L603)

Aggregates responses to a single task on the Toloka server.


{% note tip %}

Try [crowd-kit library](https://toloka.ai/docs/crowd-kit). It has many aggregation methods and executes on your computer.

{% endnote %}

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_id`|**Optional\[str\]**|<p>The ID of the task.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of the pool containing the task.</p>
`answer_weight_skill_id`|**Optional\[str\]**|<p>The ID of the skill that determines the weight of the Toloker&#x27;s responses.</p>
`fields`|**Optional\[List\[[WeightedDynamicOverlapTaskAggregatedSolutionRequest.Field](toloka.client.aggregation.WeightedDynamicOverlapTaskAggregatedSolutionRequest.Field.md)\]\]**|<p>Output data fields to aggregate. For the best results, each of these fields should have limited number of response options. If the `DAWID_SKENE` aggregation type is selected, you can only specify one value.</p>

* **Returns:**

  Aggregated response.

* **Return type:**

  [AggregatedSolution](toloka.client.aggregation.AggregatedSolution.md)

**Examples:**

The example shows how to aggregate responses to a single task.

```python
aggregated_response = toloka_client.aggregate_solutions_by_task(
    pool_id='36502086',
    task_id='000012bb84--62d80429f20bf20e50f36a27',
    answer_weight_skill_id='11294',
    fields=[toloka.client.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
)
print(aggregated_response.output_values['result'])
```
