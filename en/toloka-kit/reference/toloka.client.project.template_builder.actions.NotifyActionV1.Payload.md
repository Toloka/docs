# Payload
`toloka.client.project.template_builder.actions.NotifyActionV1.Payload` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/actions.py#L54)

```python
Payload(
    self,
    content: Optional[Any] = None,
    theme: Optional[Union[BaseComponent, Theme]] = None,
    *,
    delay: Optional[Union[BaseComponent, float]] = None,
    duration: Optional[Union[BaseComponent, float]] = None
)
```

Popup parameters.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[Any\]**|<p>Popup content. You can assign text or other components to the `content`.</p>
`theme`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Theme](toloka.client.project.template_builder.actions.NotifyActionV1.Payload.Theme.md)\]\]**|<p>A background color.</p>
`delay`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>A delay in milliseconds before showing the popup.</p>
`duration`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>A duration in milliseconds of showing the popup. It includes the delay.</p>
