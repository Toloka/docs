# ButtonRadioGroupFieldV1
`toloka.client.project.template_builder.fields.ButtonRadioGroupFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/fields.py#L118)

```python
ButtonRadioGroupFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    options: Optional[Union[BaseComponent, List[Union[BaseComponent, GroupFieldOption]]]] = None,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A group of buttons for choosing one option.


For more information, see [field.button-radio-group](https://toloka.ai/docs/template-builder/reference/field.button-radio-group).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`options`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [GroupFieldOption](toloka.client.project.template_builder.fields.GroupFieldOption.md)\]\]\]\]**|<p>A list of options.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>

**Examples:**


```python
import toloka.client.project.template_builder as tb
classification_buttons = tb.fields.ButtonRadioGroupFieldV1(
    data=tb.data.OutputData(path='class'),
    options=[
        tb.fields.GroupFieldOption('Cat', 'cat'),
        tb.fields.GroupFieldOption('Dog', 'dog'),
    ],
    validation=tb.conditions.RequiredConditionV1(hint='Choose one of the answer options'),
)
```
