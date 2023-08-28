# LinkGroupViewV1
`toloka.client.project.template_builder.view.LinkGroupViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/view.py#L317)

```python
LinkGroupViewV1(
    self,
    links: Optional[Union[BaseComponent, List[Union[BaseComponent, Link]]]] = None,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A group of links.


For more information, see [view.link-group](https://toloka.ai/docs/template-builder/reference/view.link-group).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`links`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Link](toloka.client.project.template_builder.view.LinkGroupViewV1.Link.md)\]\]\]\]**|<p>A list of links.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>

**Examples:**


```python
import toloka.client.project.template_builder as tb
links = tb.view.LinkGroupViewV1(
    [
        tb.view.LinkGroupViewV1.Link(
            'https://any.com/useful/url/1',
            'Example1',
        ),
        tb.view.LinkGroupViewV1.Link(
            'https://any.com/useful/url/2',
            'Example2',
        ),
    ]
)
```
