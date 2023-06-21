# LabeledListViewV1
`toloka.client.project.template_builder.view.LabeledListViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/view.py#L266)

```python
LabeledListViewV1(
    self,
    items: Optional[Union[BaseComponent, List[Union[BaseComponent, Item]]]] = None,
    *,
    min_width: Optional[Union[BaseComponent, float]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A list of components with labels placed on the left.


For more information, see [view.labeled-list](https://toloka.ai/docs/template-builder/reference/view.labeled-list).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Item](toloka.client.project.template_builder.view.LabeledListViewV1.Item.md)\]\]\]\]**|<p>List items.</p>
`min_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The minimum width of the component. If the width is less than the specified value, the list is displayed in compact mode. Labels are placed above the items in this mode.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
