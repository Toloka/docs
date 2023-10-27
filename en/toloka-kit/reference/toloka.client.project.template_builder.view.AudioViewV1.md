# AudioViewV1
`toloka.client.project.template_builder.view.AudioViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/view.py#L109)

```python
AudioViewV1(
    self,
    url: Optional[Any] = None,
    *,
    loop: Optional[Union[BaseComponent, bool]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

An audio player.


For more information, see [view.audio](https://toloka.ai/docs/template-builder/reference/view.audio).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`url`|**Optional\[Any\]**|<p>A link to the audio.</p>
`loop`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<ul> <li>`True` — Play audio in a loop.</li> <li>`False` — Play once.</li> </ul>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
