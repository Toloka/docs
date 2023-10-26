# BaseApp
`toloka.client.app.BaseApp` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/app/__init__.py#L137)

```python
BaseApp(
    self,
    *,
    id: Optional[str] = None,
    name: Optional[str] = None,
    image: Optional[str] = None,
    description: Optional[str] = None,
    default_item_price: Optional[Decimal] = None,
    examples: Optional[Any] = None
)
```

A lightweight representation of an [App](https://toloka.ai/docs/api/apps-reference/#tag--app) solution.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the App solution.</p>
`name`|**Optional\[str\]**|<p>The solution name.</p>
`image`|**Optional\[str\]**|<p>A link to the solution interface preview image.</p>
`description`|**Optional\[str\]**|<p>The solution description.</p>
`default_item_price`|**Optional\[Decimal\]**|<p>The default cost of one annotated item.</p>
`examples`|**Optional\[Any\]**|<p>Example description of tasks which can be solved with this solution.</p>
