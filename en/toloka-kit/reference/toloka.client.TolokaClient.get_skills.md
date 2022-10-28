# get_skills
`toloka.client.TolokaClient.get_skills` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/__init__.py#L2044)

Finds all skills that match certain criteria.


`get_skills` returns a generator. You can iterate over all found skills using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort skills use the [find_skills](toloka.client.TolokaClient.find_skills.md) method.

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

* **Yields:**

  The next matching skill.

* **Yield type:**

  Generator\[[Skill](toloka.client.skill.Skill.md), None, None\]

**Examples:**

How to check that a skill exists.

```python
segmentation_skill = next(toloka_client.get_skills(name='Area selection of road signs'), None)
if segmentation_skill:
    print(f'Segmentation skill already exists, with id {segmentation_skill.id}')
else:
    print('Create new segmentation skill here')
```
