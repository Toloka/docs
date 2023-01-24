# find_user_restrictions
`toloka.client.TolokaClient.find_user_restrictions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L3089)

Finds Toloker restrictions that match certain criteria.


The number of returned restrictions is limited. To find remaining restrictions call `find_user_restrictions` with updated search criteria.

To iterate over all matching Toloker restrictions you may use the [get_user_restrictions](toloka.client.TolokaClient.get_user_restrictions.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`scope`|**Optional\[[UserRestriction.Scope](toloka.client.user_restriction.UserRestriction.Scope.md)\]**|<p>The scope of a restriction. Refer to the [UserRestriction.Scope](toloka.client.user_restriction.UserRestriction.Scope.md) page for more information on the available `scope` values.</p>
`user_id`|**Optional\[str\]**|<p>The Toloker&#x27;s ID.</p>
`project_id`|**Optional\[str\]**|<p>The ID of a project with restricted access.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of a pool with restricted access.</p>
`id_lt`|**Optional\[str\]**|<p>Restrictions with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Restrictions with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Restrictions with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Restrictions with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Restrictions created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Restrictions created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Restrictions created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Restrictions created after or on the specified date.</p>
`sort`|**Union\[List\[str\], [UserRestrictionSortItems](toloka.client.search_requests.UserRestrictionSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned Toloker restrictions limit. The maximum allowed limit is 500.</p>

* **Returns:**

  Found Toloker restrictions and a flag showing whether there are more matching restrictions exceeding the limit.

* **Return type:**

  [UserRestrictionSearchResult](toloka.client.search_results.UserRestrictionSearchResult.md)

**Examples:**


```python
restrictions = toloka_client.find_user_restrictions(sort=['-created', '-id'], limit=10)
```

If there are restrictions exceeding the `limit`, then `restrictions.has_more` is set to `True`.
