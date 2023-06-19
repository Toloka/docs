# get_user_bonuses
`toloka.async_client.client.AsyncTolokaClient.get_user_bonuses` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L0)

Finds all Tolokers' rewards that match certain rules and returns them in an iterable object


`get_user_bonuses` returns a generator. You can iterate over all found Tolokers' rewards using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort rewards use the [find_user_bonuses](toloka.client.TolokaClient.find_user_bonuses.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The ID of a Toloker.</p>
`assignment_id`|**Optional\[str\]**|<p>The ID of an assignment a reward was granted for.</p>
`private_comment`|**Optional\[str\]**|<p>Rewards with specified comment.</p>
`id_lt`|**Optional\[str\]**|<p>Rewards with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Rewards with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Rewards with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Rewards with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Rewards given before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Rewards given before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Rewards given after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Rewards given after or on the specified date.</p>
`batch_size`|**Optional\[int\]**|<p>Returned Tolokers&#x27; rewards limit for each request. The maximum allowed batch_size is 300.</p>

* **Yields:**

  The next matching Toloker's reward.

* **Yield type:**

  [AsyncGenAdapter](toloka.util.async_utils.AsyncGenAdapter.md)\[[UserBonus](toloka.client.user_bonus.UserBonus.md), None\]

**Examples:**


```python
bonuses = list(toloka_client.get_user_bonuses(created_lt='2021-06-01T00:00:00'))
```
