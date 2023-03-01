# CoordinatesSpec
`toloka.client.project.field_spec.CoordinatesSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/project/field_spec.py#L124)

```python
CoordinatesSpec(
    self,
    *,
    required: Optional[bool] = True,
    hidden: Optional[bool] = False,
    current_location: Optional[bool] = None
)
```

Geographical coordinates field specification.


`CoordinatesSpec` stores values like `“53.910236,27.531110`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`required`|**Optional\[bool\]**|<p>Whether a field is required. </p><p>Default value: `True`.</p>
`hidden`|**Optional\[bool\]**|<p>Whether to hide an input field from Tolokers. Output fields can&#x27;t be hidden. </p><p>Default value: `False`.</p>
`current_location`|**Optional\[bool\]**|<p>`True` — saves Toloker&#x27;s current coordinates. The attribute can be used in tasks for the mobile application.</p>
