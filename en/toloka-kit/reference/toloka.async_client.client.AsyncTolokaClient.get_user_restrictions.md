# get_user_restrictions
`toloka.async_client.client.AsyncTolokaClient.get_user_restrictions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L0)

Finds all Toloker restrictions that match certain criteria.


`get_user_restrictions` returns a generator. You can iterate over all found Toloker restrictions using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort Toloker restrictions use the [find_user_restrictions](toloka.client.TolokaClient.find_user_restrictions.md) method.

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

* **Yields:**

  The next matching Toloker restriction.

* **Yield type:**

  [AsyncGenAdapter](toloka.util.async_utils.AsyncGenAdapter.md)\[[UserRestriction](toloka.client.user_restriction.UserRestriction.md), None\]

**Examples:**


```python
results_list = list(toloka_client.get_user_restrictions(scope='ALL_PROJECTS'))
```