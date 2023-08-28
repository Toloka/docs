# BarsLayoutV1
`toloka.client.project.template_builder.layouts.BarsLayoutV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/layouts.py#L39)

```python
BarsLayoutV1(
    self,
    content: Optional[BaseComponent] = None,
    *,
    bar_after: Optional[BaseComponent] = None,
    bar_before: Optional[BaseComponent] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A layout with top and bottom bars.


For more information, see [layout.bars](https://toloka.ai/docs/template-builder/reference/layout.bars).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The main content.</p>
`bar_after`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The bar displayed below the main content.</p>
`bar_before`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The bar displayed above the main content.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
