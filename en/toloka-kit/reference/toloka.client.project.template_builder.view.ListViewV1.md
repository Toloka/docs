# ListViewV1
`toloka.client.project.template_builder.view.ListViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/view.py#L360)

```python
ListViewV1(
    self,
    items: Optional[Union[BaseComponent, List[BaseComponent]]] = None,
    *,
    direction: Optional[Union[BaseComponent, ListDirection]] = None,
    size: Optional[Union[BaseComponent, ListSize]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A list of components.


For more information, see [view.list](https://toloka.ai/docs/template-builder/reference/view.list).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]\]\]**|<p>List items.</p>
`direction`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [ListDirection](toloka.client.project.template_builder.base.ListDirection.md)\]\]**|<p>The direction of the list:</p> <ul> <li>`vertical`</li> <li>`horizontal`</li> </ul> <p>Default value: `vertical`.</p>
`size`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [ListSize](toloka.client.project.template_builder.base.ListSize.md)\]\]**|<p>A spacing between list items: `m` — The default spacing. `s` — Narrower spacing.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
