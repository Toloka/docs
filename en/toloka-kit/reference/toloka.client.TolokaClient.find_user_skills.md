# find_user_skills
`toloka.client.TolokaClient.find_user_skills` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L3468)

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
`limit`|**Optional\[int\]**|<p>Returned skills limit. The maximum allowed value: 1000.</p>

* **Returns:**

  Found Toloker's skills and a flag showing whether there are more matching skills exceeding the limit.

* **Return type:**

  [UserSkillSearchResult](toloka.client.search_results.UserSkillSearchResult.md)

**Examples:**

Getting a list of skills that a Toloker has.

```python
find_result = toloka_client.find_user_skills(user_id='fac97860c7929add8048ed2ef63b66fd')
skills = find_result.items
```

Getting a list of Tolokers who have a certain skill.

```python
find_result = toloka_client.find_user_skills(skill_id='11294')
skills = find_result.items
```

If there are skills exceeding the `limit`, then `find_result.has_more` is set to `True`.
