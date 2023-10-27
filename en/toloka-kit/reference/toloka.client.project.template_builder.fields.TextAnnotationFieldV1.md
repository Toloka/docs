# TextAnnotationFieldV1
`toloka.client.project.template_builder.fields.TextAnnotationFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/fields.py#L487)

```python
TextAnnotationFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    adjust: Optional[Union[BaseComponent, str]] = None,
    content: Optional[Union[BaseComponent, str]] = None,
    disabled: Optional[Union[BaseComponent, bool]] = None,
    labels: Optional[Union[BaseComponent, List[Union[BaseComponent, Label]]]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component for text annotation.


For more information, see [field.text-annotation](https://toloka.ai/docs/template-builder/reference/field.text-annotation).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`adjust`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>If `adjust` is set to `words`, entire words are selected and annotated. If `adjust` is omitted, any part of a text can be selected.</p>
`content`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A text for annotation.</p>
`disabled`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Disabling the component. </p><p>Default value: `False`.</p>
`labels`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Label](toloka.client.project.template_builder.fields.TextAnnotationFieldV1.Label.md)\]\]\]\]**|<p>A list of annotation categories.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
