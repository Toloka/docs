# TextTransformHelperV1
`toloka.client.project.template_builder.helpers.TextTransformHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/helpers.py#L188)

```python
TextTransformHelperV1(
    self,
    data: Optional[Any] = None,
    transformation: Optional[Union[BaseComponent, Transformation]] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

Converts a text to uppercase, lowercase, or capitalize it.


For more information, see [helper.text-transform](https://toloka.ai/docs/template-builder/reference/helper.text-transform).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[Any\]**|<p>A text to convert.</p>
`transformation`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Transformation](toloka.client.project.template_builder.helpers.TextTransformHelperV1.Transformation.md)\]\]**|<p>A conversion mode:</p> <ul> <li>`uppercase` — Makes all letters uppercase.</li> <li>`lowercase` — Makes all letters lowercase.</li> <li>`capitalize` — Capitalizes the first letter in the text, and leaves the rest lowercase. Note, that if there are several sentences, the rest of them are not capitalized.</li> </ul>
