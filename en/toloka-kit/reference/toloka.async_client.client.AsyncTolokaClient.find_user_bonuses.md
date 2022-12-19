# find_user_bonuses
`toloka.async_client.client.AsyncTolokaClient.find_user_bonuses` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L0)

Finds Tolokers' rewards that match certain criteria.


The number of returned rewards is limited. To find remaining rewards call `find_user_bonuses` with updated search criteria.

To iterate over all matching Tolokers' rewards you may use the [get_user_bonuses](toloka.client.TolokaClient.get_user_bonuses.md) method.

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
`sort`|**Union\[List\[str\], [UserBonusSortItems](toloka.client.search_requests.UserBonusSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned Tolokers&#x27; rewards limit. The maximum allowed limit is 300.</p>

* **Returns:**

  Found Tolokers' rewards and a flag showing whether there are more matching rewards exceeding the limit.

* **Return type:**

  [UserBonusSearchResult](toloka.client.search_results.UserBonusSearchResult.md)

**Examples:**


```python
toloka_client.find_user_bonuses(user_id='1', sort=['-created', '-id'], limit=3)
```
