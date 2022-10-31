# find_aggregated_solutions
`toloka.client.TolokaClient.find_aggregated_solutions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/__init__.py#L504)

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
`limit`|**Optional\[int\]**|<p>Returned aggregated responses limit. The default limit is 50. The maximum allowed limit is 100,000.</p>

* **Returns:**

  Found responses and a flag showing whether there are more matching responses exceeding the limit.

* **Return type:**

  [AggregatedSolutionSearchResult](toloka.client.search_results.AggregatedSolutionSearchResult.md)

**Examples:**

The example shows how to get all aggregated responses using the `find_aggregated_solutions` method.

```python
# run toloka_client.aggregate_solutions_by_pool and wait for the operation to complete.
current_result = toloka_client.find_aggregated_solutions(aggregation_operation.id)
aggregation_results = current_result.items
# If we have more results, let's get them
while current_result.has_more:
    current_result = toloka_client.find_aggregated_solutions(
        aggregation_operation.id,
        task_id_gt=current_result.items[-1].task_id,
    )
    aggregation_results = aggregation_results + current_result.items
print(len(aggregation_results))
```
