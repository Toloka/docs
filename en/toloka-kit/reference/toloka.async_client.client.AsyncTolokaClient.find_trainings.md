# find_trainings
`toloka.async_client.client.AsyncTolokaClient.find_trainings` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L0)

Finds trainings that match certain criteria.


The number of returned trainings is limited. To find remaining trainings call `find_trainings` with updated search criteria.

To iterate over all matching trainings you may use the [get_trainings](toloka.client.TolokaClient.get_trainings.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`status`|**Optional\[[Training.Status](toloka.client.training.Training.Status.md)\]**|<p>Training pool status. Refer to the [Training.Status](toloka.client.training.Training.Status.md) page for more information on the available `status` values.</p>
`project_id`|**Optional\[str\]**|<p>Training pools belonging to the project with the specified ID.</p>
`id_lt`|**Optional\[str\]**|<p>Training pools with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Training pools with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Training pools with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Training pools with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Training pools created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Training pools created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Training pools created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Training pools created after or on the specified date.</p>
`last_started_lt`|**Optional\[datetime\]**|<p>Training pools that were opened last time before the specified date.</p>
`last_started_lte`|**Optional\[datetime\]**|<p>Training pools that were opened last time before or on the specified date.</p>
`last_started_gt`|**Optional\[datetime\]**|<p>Training pools that were opened last time after the specified date.</p>
`last_started_gte`|**Optional\[datetime\]**|<p>Training pools that were opened last time after or on the specified date.</p>
`sort`|**Union\[List\[str\], [TrainingSortItems](toloka.client.search_requests.TrainingSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned trainings limit. The maximum allowed value: 300.</p>

* **Returns:**

  Found trainings and a flag showing whether there are more matching trainings exceeding the limit.

* **Return type:**

  [TrainingSearchResult](toloka.client.search_results.TrainingSearchResult.md)

**Examples:**

Finding all trainings in all projects.

```python
find_result = toloka_client.find_trainings()
trainings = find_result.items
```

Finding all opened trainings in all projects.

```python
find_result = toloka_client.find_trainings(status='OPEN')
trainings = find_result.items
```

Finding all opened trainings in a specific project.

```python
find_result = toloka_client.find_trainings(status='OPEN', project_id='92694')
trainings = find_result.items
```

If there are trainings exceeding the `limit`, then `find_result.has_more` is set to `True`.
