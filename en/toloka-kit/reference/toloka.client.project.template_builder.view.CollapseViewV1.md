# CollapseViewV1
`toloka.client.project.template_builder.view.CollapseViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/view.py#L126)

```python
CollapseViewV1(
    self,
    content: Optional[BaseComponent] = None,
    *,
    label: Optional[Any] = None,
    default_opened: Optional[Union[BaseComponent, bool]] = None,
    hint: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

An expandable block.


For more information, see [view.collapse](https://toloka.ai/docs/template-builder/reference/view.collapse).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The block content.</p>
`label`|**Optional\[Any\]**|<p>The block heading.</p>
`default_opened`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Initial state of the block: `True` — Expanded `False` — Collapsed</p> <p>Default value: `False`.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
