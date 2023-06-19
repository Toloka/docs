# AppBatchCreateRequest
`toloka.client.app.AppBatchCreateRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/app/__init__.py#L265)

```python
AppBatchCreateRequest(
    self,
    *,
    name: Optional[str] = None,
    items: Optional[List[Dict[str, Any]]] = None
)
```

Parameters of a request for creating multiple App task items in a batch.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**Optional\[str\]**|<p>The batch name.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with task items. The items must follow the solution schema described in the `App.input_spec`.</p>
