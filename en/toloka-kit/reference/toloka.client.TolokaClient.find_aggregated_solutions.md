# find_aggregated_solutions
`toloka.client.TolokaClient.find_aggregated_solutions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L635)

Finds aggregated responses that match certain criteria.


Pass to the `find_aggregated_solutions` the ID of the operation started by the [aggregate_solutions_by_pool](toloka.client.TolokaClient.aggregate_solutions_by_pool.md) method.

The number of returned aggregated responses is limited. To find remaining responses call `find_aggregated_solutions` with updated search criteria.

To iterate over all matching aggregated responses you may use the [get_aggregated_solutions](toloka.client.TolokaClient.get_aggregated_solutions.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**str**|<p>The ID of the aggregation operation.</p>
`task_id_lt`|**Optional\[str\]**|<p>Responses for tasks with IDs less than the specified value.</p>
`task_id_lte`|**Optional\[str\]**|<p>Responses for tasks with IDs less than or equal to the specified value.</p>
`task_id_gt`|**Optional\[str\]**|<p>Responses for tasks with IDs greater than the specified value.</p>
`task_id_gte`|**Optional\[str\]**|<p>Responses for tasks with IDs greater than or equal to the specified value.</p>
`sort`|**Union\[List\[str\], [AggregatedSolutionSortItems](toloka.client.search_requests.AggregatedSolutionSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned aggregated responses limit. The maximum allowed value: 100,000. The default value: 50.</p>

* **Returns:**

  Found responses and a flag showing whether there are more matching responses exceeding the limit.

* **Return type:**

  [AggregatedSolutionSearchResult](toloka.client.search_results.AggregatedSolutionSearchResult.md)

**Examples:**

The example shows how to get all aggregated responses using the `find_aggregated_solutions` method.
First, run the [aggregate_solutions_by_pool](toloka.client.TolokaClient.aggregate_solutions_by_pool.md) method and wait for the operation to complete.
The ID of the operation is used to get aggregated results.

```python
current_result = toloka_client.find_aggregated_solutions(aggregation_operation.id)
aggregation_results = current_result.items

while current_result.has_more:
    current_result = toloka_client.find_aggregated_solutions(
        aggregation_operation.id,
        task_id_gt=current_result.items[-1].task_id,
    )
    aggregation_results = aggregation_results + current_result.items
print(len(aggregation_results))
```
