# RotateActionV1
`toloka.client.project.template_builder.actions.RotateActionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/actions.py#L127)

```python
RotateActionV1(
    self,
    view: Optional[Union[BaseComponent, RefComponent]] = None,
    payload: Optional[Union[BaseComponent, Payload]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

The action rotates a component by 90 degrees.


For more information, see [action.rotate](https://toloka.ai/docs/template-builder/reference/action.rotate).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`view`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [RefComponent](toloka.client.project.template_builder.base.RefComponent.md)\]\]**|<p>A reference to the component.</p>
`payload`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Payload](toloka.client.project.template_builder.actions.RotateActionV1.Payload.md)\]\]**|<p>The direction of rotation.</p>
