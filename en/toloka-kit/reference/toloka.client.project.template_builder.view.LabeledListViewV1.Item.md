# Item
`toloka.client.project.template_builder.view.LabeledListViewV1.Item` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/view.py#L279)

```python
Item(
    self,
    content: Optional[BaseComponent] = None,
    label: Optional[Any] = None,
    *,
    center_label: Optional[Union[BaseComponent, bool]] = None,
    hint: Optional[Any] = None
)
```

A labeled list item.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The content of the item.</p>
`label`|**Optional\[Any\]**|<p>An item label.</p>
`center_label`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Label vertical alignment.</p> <ul> <li>`True` — The label is centered.</li> <li>`False` — The label is aligned to the top of the item content.</li> </ul> <p></p><p>Default value: `False`.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
