# AppItemImport
`toloka.client.app.AppItemImport` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/app/__init__.py#L242)

```python
AppItemImport(
    self,
    *,
    id: Optional[str] = None,
    records_count: Optional[int] = None,
    records_processed: Optional[int] = None,
    errors: Optional[Dict] = None
)
```

Information about an operation that adds items.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID.</p>
`records_count`|**Optional\[int\]**|<p>The total number of items sent by a client.</p>
`records_processed`|**Optional\[int\]**|<p>The number of items processed during the operation.</p>
`errors`|**Optional\[Dict\]**|<p>Information about items with incorrect parameters which were not added.</p>
