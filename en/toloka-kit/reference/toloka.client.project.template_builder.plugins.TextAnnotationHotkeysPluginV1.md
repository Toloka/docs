# TextAnnotationHotkeysPluginV1
`toloka.client.project.template_builder.plugins.TextAnnotationHotkeysPluginV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/plugins.py#L61)

```python
TextAnnotationHotkeysPluginV1(
    self,
    labels: Optional[Union[BaseComponent, List[str]]] = None,
    remove: Optional[Union[BaseComponent, str]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

Hotkeys for the [TextAnnotationFieldV1](toloka.client.project.template_builder.fields.TextAnnotationFieldV1.md) component.


For more information, see [plugin.field.text-annotation.hotkeys](https://toloka.ai/docs/template-builder/reference/plugin.field.text-annotation.hotkeys).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`labels`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[str\]\]\]**|<p>A list of hotkeys for choosing labels.</p>
`remove`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A hotkey for clearing the label of the annotated text.</p>
