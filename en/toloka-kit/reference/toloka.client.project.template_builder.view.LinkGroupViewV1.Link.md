# Link
`toloka.client.project.template_builder.view.LinkGroupViewV1.Link` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/view.py#L343)

```python
Link(
    self,
    url: Optional[Union[BaseComponent, str]] = None,
    content: Optional[Union[BaseComponent, str]] = None,
    *,
    theme: Optional[Union[BaseComponent, str]] = None
)
```

A link for the `LinkGroupViewV1`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`url`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A URL.</p>
`content`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A link text.</p>
`theme`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The appearance of the link. If `theme` is omitted, the link is displayed as an underlined text. If `theme` is set to `primary`, a button is displayed.</p>
