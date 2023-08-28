# wait_operation
`toloka.client.TolokaClient.wait_operation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L2931)

```python
wait_operation(
    self,
    op: Operation,
    timeout: timedelta = ...,
    disable_progress: bool = False
)
```

Waits for a Toloka operation to complete.


To get information about the operation, call the [get_operation](toloka.client.TolokaClient.get_operation.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`op`|**[Operation](toloka.client.operations.Operation.md)**|<p>The ID of the operation.</p>
`timeout`|**timedelta**|<p>The wait timeout. </p><p>Default value: 10 minutes.</p>
`disable_progress`|**bool**|<ul> <li>`False` — A progress bar is shown.</li> <li>`True` — A progress bar is hidden.</li> </ul> <p>Default value: `False`.</p>

* **Returns:**

  The completed operation.

* **Return type:**

  [Operation](toloka.client.operations.Operation.md)

**Examples:**

The example starts aggregation and waits for it.

```python
aggregation_operation = toloka_client.aggregate_solutions_by_pool(
        type=toloka.client.aggregation.AggregatedSolutionType.WEIGHTED_DYNAMIC_OVERLAP,
        pool_id='1086170',
        answer_weight_skill_id='11294',
        fields=[toloka.client.aggregation.PoolAggregatedSolutionRequest.Field(name='result')]
    )
aggregation_operation = toloka_client.wait_operation(aggregation_operation)
aggregation_results = list(toloka_client.get_aggregated_solutions(aggregation_operation.id))
```
