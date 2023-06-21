# get_trainings
`toloka.client.TolokaClient.get_trainings` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L2043)

Finds all trainings that match certain criteria.


`get_trainings` returns a generator. You can iterate over all found trainings using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort trainings use the [find_trainings](toloka.client.TolokaClient.find_trainings.md) method.

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
`batch_size`|**Optional\[int\]**|<p>Returned trainings limit for each request. The maximum allowed batch_size is 300.</p>

* **Yields:**

  The next matching training.

* **Yield type:**

  Generator\[[Training](toloka.client.training.Training.md), None, None\]

**Examples:**

Getting all trainings in a project.

```python
trainings = toloka_client.get_trainings(project_id='1')
```
