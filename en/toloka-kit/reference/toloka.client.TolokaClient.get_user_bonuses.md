# get_user_bonuses
`toloka.client.TolokaClient.get_user_bonuses` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L3196)

Finds all Tolokers' bonuses that match certain rules and returns them in an iterable object


`get_user_bonuses` returns a generator. You can iterate over all found Tolokers' bonuses using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort bonuses use the [find_user_bonuses](toloka.client.TolokaClient.find_user_bonuses.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The ID of a Toloker.</p>
`assignment_id`|**Optional\[str\]**|<p>The ID of an assignment a bonus was granted for.</p>
`private_comment`|**Optional\[str\]**|<p>Bonuses with specified comment.</p>
`id_lt`|**Optional\[str\]**|<p>Bonuses with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Bonuses with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Bonuses with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Bonuses with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Bonuses given before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Bonuses given before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Bonuses given after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Bonuses given after or on the specified date.</p>
`batch_size`|**Optional\[int\]**|<p>Returned Tolokers&#x27; bonuses limit for each request. The maximum allowed `batch_size` is 300.</p>

* **Yields:**

  The next matching Toloker's bonus.

* **Yield type:**

  Generator\[[UserBonus](toloka.client.user_bonus.UserBonus.md), None, None\]

**Examples:**


```python
bonuses = list(toloka_client.get_user_bonuses(created_lt='2021-06-01T00:00:00'))
```
