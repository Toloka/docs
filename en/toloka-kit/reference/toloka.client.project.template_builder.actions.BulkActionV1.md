# BulkActionV1
`toloka.client.project.template_builder.actions.BulkActionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/actions.py#L33)

```python
BulkActionV1(
    self,
    payload: Optional[Union[BaseComponent, List[BaseComponent]]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

A group of actions to be called together.


For more information, see [action.bulk](https://toloka.ai/docs/template-builder/reference/action.bulk).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`payload`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]\]\]**|<p>A list of actions.</p>
