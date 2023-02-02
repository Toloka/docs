# get_assignments_df
`toloka.client.TolokaClient.get_assignments_df` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/__init__.py#L3482)

Downloads assignments as pandas.DataFrame.


{% note warning %}

Requires toloka-kit[pandas] extras. Install it with the following command:

```shell
pip install toloka-kit[pandas]
```

{% endnote %}

Experimental method.
Implements the same behavior as if you download results in web-interface and then read it by pandas.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>From which pool the results are loaded.</p>
`status`|**Optional\[List\[[GetAssignmentsTsvParameters.Status](toloka.client.assignment.GetAssignmentsTsvParameters.Status.md)\]\]**|<p>Statuses of assignments to download.</p>
`start_time_from`|**Optional\[datetime\]**|<p>Download assignments submitted after the specified date and time.</p>
`start_time_to`|**Optional\[datetime\]**|<p>Download assignments submitted before the specified date and time.</p>
`exclude_banned`|**Optional\[bool\]**|<p>Exclude answers from banned Tolokers, even if their assignments have suitable status.</p>
`field`|**Optional\[List\[[GetAssignmentsTsvParameters.Field](toloka.client.assignment.GetAssignmentsTsvParameters.Field.md)\]\]**|<p>Names of `Assignment` fields to be downloaded. Fields other then from `Assignment` class are always downloaded.</p>

* **Returns:**

  DataFrame with all results. Contains groups of fields with prefixes:
* "INPUT" - Fields that were at the input in the task.
* "OUTPUT" - Fields that were received as a result of execution.
* "GOLDEN" - Fields with correct answers. Filled in only for golden tasks and training tasks.
* "HINT" - Hints for completing tasks. Filled in for training tasks.
* "ACCEPT" - Fields describing the deferred acceptance of tasks.
* "ASSIGNMENT" - fields describing additional information about the Assignment.

* **Return type:**

  DataFrame

**Examples:**

Get all assignments from the specified pool by `pool_id` to [pandas.DataFrame](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html).
And apply the native pandas `rename` method to change columns' names.

```python
answers_df = toloka_client.get_assignments_df(pool_id='1')
answers_df = answers_df.rename(columns={
    'INPUT:image': 'task',
    'OUTPUT:result': 'label',
    'ASSIGNMENT:worker_id': 'annotator'
})
```
