# PoolPatchRequest
`toloka.client.pool.PoolPatchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/pool/__init__.py#L282)

```python
PoolPatchRequest(self, priority: Optional[int] = None)
```

New pool parameters.


This class is used with the [patch_pool](toloka.client.TolokaClient.patch_pool.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`priority`|**Optional\[int\]**|<p>The new priority of the pool. Possible values: from -100 to 100.</p>
