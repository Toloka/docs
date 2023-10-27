# AppItemCreateRequest
`toloka.client.app.AppItemCreateRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/app/__init__.py#L243)

```python
AppItemCreateRequest(
    self,
    *,
    batch_id: Optional[str] = None,
    input_data: Optional[Dict[str, Any]] = None,
    force_new_original: Optional[bool] = None
)
```

Parameters of a request for creating single item.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`batch_id`|**Optional\[str\]**|<p>The ID of the batch that contains the item.</p>
`input_data`|**Optional\[Dict\[str, Any\]\]**|<p>Input data. It must follow the solution schema described in `App.input_spec`.</p>
`force_new_original`|**Optional\[bool\]**|<p>Whether to enable or disable the deduplication for the item in the request. When set to true, the item will be re-labeled regardless of whether pre-labeled duplicates exist. Default is `False`.</p>
