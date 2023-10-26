# AppBatchPatch
`toloka.client.app.AppBatchPatch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/app/__init__.py#L428)

```python
AppBatchPatch(
    self,
    *,
    name: Optional[str] = None,
    priority_order: Optional[AppBatch.PriorityOrder] = None
)
```

Parameters of a request for updating an App batch.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**Optional\[str\]**|<p>The new batch name.</p>
`priority_order`|**Optional\[[AppBatch.PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md)\]**|<p>The batch priority. See [PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md) for details.</p>
