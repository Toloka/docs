# AppItemsCreateRequest
`toloka.client.app.AppItemsCreateRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/app/__init__.py#L230)

```python
AppItemsCreateRequest(
    self,
    *,
    batch_id: Optional[str] = None,
    items: Optional[List[Dict[str, Any]]] = None
)
```

Parameters of a request for creating multiple items.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`batch_id`|**Optional\[str\]**|<p>The ID of the batch to place items to.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with items. The items must follow the solution schema described in `App.input_spec`.</p>
