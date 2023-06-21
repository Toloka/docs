# AssignmentsIssuingViewConfig
`toloka.client.project.Project.AssignmentsIssuingViewConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/__init__.py#L140)

```python
AssignmentsIssuingViewConfig(
    self,
    *,
    title_template: Optional[str] = None,
    description_template: Optional[str] = None,
    map_provider: Optional[MapProvider] = None
)
```

Task view on the map.


These parameters are used when `Project.assignments_issuing_type` is set to `MAP_SELECTOR`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`title_template`|**Optional\[str\]**|<p>The name of a task. Tolokers see it in the task preview mode.</p>
`description_template`|**Optional\[str\]**|<p>The brief description of a task. Tolokers see it in the task preview mode.</p>
`map_provider`|**Optional\[[MapProvider](toloka.client.project.Project.AssignmentsIssuingViewConfig.MapProvider.md)\]**|<p>A map provider.</p>
