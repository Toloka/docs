# ListFieldV1
`toloka.client.project.template_builder.fields.ListFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/fields.py#L298)

```python
ListFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    render: Optional[BaseComponent] = None,
    *,
    button_label: Optional[Any] = None,
    direction: Optional[Union[BaseComponent, ListDirection]] = None,
    editable: Optional[Union[BaseComponent, bool]] = None,
    max_length: Optional[Union[BaseComponent, float]] = None,
    size: Optional[Union[BaseComponent, ListSize]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component that allows a Toloker to add and remove list items, such as text fields.


Use RelativeData(toloka.client.project.template_builder.data.RelativeData.md) in list items,
otherwise all list items will change the same data.

For more information, see [field.list](https://toloka.ai/docs/template-builder/reference/field.list).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`render`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A template for the list item.</p>
`button_label`|**Optional\[Any\]**|<p>A text on a button that adds the list item.</p>
`direction`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [ListDirection](toloka.client.project.template_builder.base.ListDirection.md)\]\]**|<p>The direction of the list:</p> <ul> <li>`horizontal`</li> <li>`vertical`</li> </ul>
`editable`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<ul> <li>`True` — A Toloker can add or remove list items.</li> <li>`False` — The list can&#x27;t be changed.</li> </ul> <p></p><p>Default value: `True`.</p>
`max_length`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The maximum number of list items.</p>
`size`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [ListSize](toloka.client.project.template_builder.base.ListSize.md)\]\]**|<p>The distance between list items:</p> <ul> <li>`s` — Small.</li> <li>`m` — Medium.</li> </ul> <p></p><p>Default value: `m`.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
