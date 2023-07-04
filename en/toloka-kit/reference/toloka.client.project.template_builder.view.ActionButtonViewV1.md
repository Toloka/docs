# ActionButtonViewV1
`toloka.client.project.template_builder.view.ActionButtonViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/view.py#L64)

```python
ActionButtonViewV1(
    self,
    action: Optional[BaseComponent] = None,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A button that calls an action.


For more information, see [view.action-button](https://toloka.ai/docs/template-builder/reference/view.action-button).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`action`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The action.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label on the button.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
