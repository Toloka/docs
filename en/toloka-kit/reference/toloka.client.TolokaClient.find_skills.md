# find_skills
`toloka.client.TolokaClient.find_skills` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L2068)

Finds skills that match certain criteria.


The number of returned skills is limited. To find remaining skills call `find_skills` with updated search criteria.

To iterate over all matching skills you may use the [get_skills](toloka.client.TolokaClient.get_skills.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**Optional\[str\]**|<p>The name of the skill.</p>
`id_lt`|**Optional\[str\]**|<p>Skills with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Skills with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Skills with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Skills with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Skills created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Skills created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Skills created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Skills created on or after the specified date.</p>
`sort`|**Union\[List\[str\], [SkillSortItems](toloka.client.search_requests.SkillSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned skills limit. The maximum allowed limit is 100.</p>

* **Returns:**

  Found skills and a flag showing whether there are more matching skills exceeding the limit.

* **Return type:**

  [SkillSearchResult](toloka.client.search_results.SkillSearchResult.md)

**Examples:**

The example shows how to find ten most recently created skills.

```python
toloka_client.find_skills(sort=['-created', '-id'], limit=10)
```
