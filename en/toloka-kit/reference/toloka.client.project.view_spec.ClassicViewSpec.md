# ClassicViewSpec
`toloka.client.project.view_spec.ClassicViewSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/view_spec.py#L72)

```python
ClassicViewSpec(
    self,
    *,
    settings: Optional[ViewSpec.Settings] = None,
    script: Optional[str] = None,
    markup: Optional[str] = None,
    styles: Optional[str] = None,
    assets: Optional[Assets] = None
)
```

A task interface defined with HTML, CSS and JS.


For more information, see the [guide](https://toloka.ai/docs/guide/spec).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`markup`|**Optional\[str\]**|<p>HTML markup of the task interface.</p>
`styles`|**Optional\[str\]**|<p>CSS for the task interface.</p>
`script`|**Optional\[str\]**|<p>JavaScript code for the task interface.</p>
`assets`|**Optional\[[Assets](toloka.client.project.view_spec.ClassicViewSpec.Assets.md)\]**|<p>Links to external files.</p>
