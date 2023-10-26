# SyncBatchCreateRequest
`toloka.client.app.SyncBatchCreateRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/app/__init__.py#L416)

```python
SyncBatchCreateRequest(
    self,
    *,
    name: Optional[str] = None,
    items: Optional[List[Dict[str, Any]]] = None
)
```

The batch to be created with the list of the task items.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**Optional\[str\]**|<p>The batch name.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with task items. The items must follow the solution schema described in the `App.input_spec`.</p>
