# OpenCloseActionV1
`toloka.client.project.template_builder.actions.OpenCloseActionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/actions.py#L88)

```python
OpenCloseActionV1(
    self,
    view: Optional[Union[BaseComponent, RefComponent]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

The action changes the display mode of another component.


It can expand an [image](toloka.client.project.template_builder.view.ImageViewV1.md) to a full screen
or collapse a [section](toloka.client.project.template_builder.view.CollapseViewV1.md).

For more information, see [action.open-close](https://toloka.ai/docs/template-builder/reference/action.open-close).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`view`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [RefComponent](toloka.client.project.template_builder.base.RefComponent.md)\]\]**|<p>References the component to perform the action with.</p>
