# DateFieldV1
`toloka.client.project.template_builder.fields.DateFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/fields.py#L184)

```python
DateFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    format: Optional[Any] = None,
    *,
    block_list: Optional[Union[BaseComponent, List[Any]]] = None,
    max: Optional[Any] = None,
    min: Optional[Any] = None,
    placeholder: Optional[Any] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A field for entering a date and time.


For more information, see [field.date](https://toloka.ai/docs/template-builder/reference/field.date).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`format`|**Optional\[Any\]**|<p>The format of the field:</p> <ul> <li>`date-time` — Date and time.</li> <li>`date` — Date only.</li> </ul>
`block_list`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Any\]\]\]**|<p>A list of dates that a Toloker can&#x27;t select.</p>
`max`|**Optional\[Any\]**|<p>The latest date and time in the `YYYY-MM-DD hh:mm` format that a Toloker can select.</p>
`min`|**Optional\[Any\]**|<p>The earliest date and time in the `YYYY-MM-DD hh:mm` format that a Toloker can select.</p>
`placeholder`|**Optional\[Any\]**|<p>A text that is shown when no date is entered.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
