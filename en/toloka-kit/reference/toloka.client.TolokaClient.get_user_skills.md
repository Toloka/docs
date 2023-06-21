# get_user_skills
`toloka.client.TolokaClient.get_user_skills` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L3413)

Finds all Toloker's skills that match certain criteria.


`get_user_skills` returns a generator. You can iterate over all found Toloker's skills using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort Toloker's skills use the [find_user_skills](toloka.client.TolokaClient.find_user_skills.md) method.

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
`batch_size`|**Optional\[int\]**|<p>Returned skills limit for each request. The maximum allowed batch_size is 1000.</p>

* **Yields:**

  The next matching Toloker's skill.

* **Yield type:**

  Generator\[[UserSkill](toloka.client.user_skill.UserSkill.md), None, None\]

**Examples:**


```python
results_list = list(toloka_client.get_user_skills())
```
