# find_user_skills
`toloka.async_client.client.AsyncTolokaClient.find_user_skills` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/__init__.py#L0)

Finds Toloker's skills that match certain criteria.


The number of returned Toloker's skills is limited. To find remaining skills call `find_user_skills` with updated search criteria.

To iterate over all matching skills you may use the [get_user_skills](toloka.client.TolokaClient.get_user_skills.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The ID of a Toloker.</p>
`skill_id`|**Optional\[str\]**|<p>The ID of a skill.</p>
`id_lt`|**Optional\[str\]**|<p>Skills with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Skills with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Skills with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Skills with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Skills created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Skills created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Skills created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Skills created on or after the specified date.</p>
`modified_lt`|**Optional\[datetime\]**|<p>Skills that changed before the specified date.</p>
`modified_lte`|**Optional\[datetime\]**|<p>Skills that changed before the specified date.</p>
`modified_gt`|**Optional\[datetime\]**|<p>Skills changed after the specified date.</p>
`modified_gte`|**Optional\[datetime\]**|<p>Skills created on or after the specified date.</p>
`sort`|**Union\[List\[str\], [UserSkillSortItems](toloka.client.search_requests.UserSkillSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned skills limit. The maximum allowed limit is 1000.</p>

* **Returns:**

  Found Toloker's skills and a flag showing whether there are more matching skills exceeding the limit.

* **Return type:**

  [UserSkillSearchResult](toloka.client.search_results.UserSkillSearchResult.md)

**Examples:**


```python
skills = toloka_client.find_user_skills(limit=10)
```

If there are skills exceeding the `limit`, then `skills.has_more` is set to `True`.
