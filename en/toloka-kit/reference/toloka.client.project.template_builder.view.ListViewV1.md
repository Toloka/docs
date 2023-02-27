# ListViewV1
`toloka.client.project.template_builder.view.ListViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/project/template_builder/view.py#L343)

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

Block for displaying data in a list.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]\]\]**|<p>Array of list items.</p>
`direction`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [ListDirection](toloka.client.project.template_builder.base.ListDirection.md)\]\]**|<p>Determines the direction of the list.</p>
`size`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [ListSize](toloka.client.project.template_builder.base.ListSize.md)\]\]**|<p>Specifies the size of the margins between elements. Acceptable values in ascending order: s, m (default value).</p>
`hint`|**Optional\[Any\]**|<p>Hint text.</p>
`label`|**Optional\[Any\]**|<p>Label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation based on condition.</p>
