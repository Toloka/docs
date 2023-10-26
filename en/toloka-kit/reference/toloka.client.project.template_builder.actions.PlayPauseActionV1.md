# PlayPauseActionV1
`toloka.client.project.template_builder.actions.PlayPauseActionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/actions.py#L115)

```python
PlayPauseActionV1(
    self,
    view: Optional[Union[BaseComponent, RefComponent]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

The action pauses an audio or video player or resumes it.


For more information, see [action.play-pause](https://toloka.ai/docs/template-builder/reference/action.play-pause).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`view`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [RefComponent](toloka.client.project.template_builder.base.RefComponent.md)\]\]**|<p>A reference to the audio or video player.</p>
