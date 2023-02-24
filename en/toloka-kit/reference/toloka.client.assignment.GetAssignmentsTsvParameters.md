# GetAssignmentsTsvParameters
`toloka.client.assignment.GetAssignmentsTsvParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/assignment.py#L125)

```python
GetAssignmentsTsvParameters(
    self,
    *,
    status: Optional[List[Status]] = ...,
    start_time_from: Optional[datetime] = None,
    start_time_to: Optional[datetime] = None,
    exclude_banned: Optional[bool] = None,
    field: Optional[List[Field]] = ...
)
```

Parameters for downloading assignments.


These parameters are used in the [TolokaClient.get_assignments_df](toloka.client.TolokaClient.get_assignments_df.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`status`|**Optional\[List\[[Status](toloka.client.assignment.GetAssignmentsTsvParameters.Status.md)\]\]**|<p>Statuses of assignments to download.</p>
`start_time_from`|**Optional\[datetime\]**|<p>Download assignments submitted after the specified date and time.</p>
`start_time_to`|**Optional\[datetime\]**|<p>Download assignments submitted before the specified date and time.</p>
`exclude_banned`|**Optional\[bool\]**|<p>Exclude answers from banned Tolokers, even if their assignments have suitable status.</p>
`field`|**Optional\[List\[[Field](toloka.client.assignment.GetAssignmentsTsvParameters.Field.md)\]\]**|<p>Names of `Assignment` fields to be downloaded. Fields other then from `Assignment` class are always downloaded.</p>
