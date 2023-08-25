# RequiredConditionV1
`toloka.client.project.template_builder.conditions.RequiredConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/conditions.py#L191)

```python
RequiredConditionV1(
    self,
    data: Optional[Any] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Checks that a data field is present in a response.


For more information, see [condition.required](https://toloka.ai/docs/template-builder/reference/condition.required).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[Any\]**|<p>The data field. If it is not specified, the data of the parent component is used.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>

**Examples:**

How to check that image is uploaded.

```python
import toloka.client.project.template_builder as tb
image = tb.fields.MediaFileFieldV1(
    tb.data.OutputData('image'),
    tb.fields.MediaFileFieldV1.Accept(photo=True, gallery=True),
    validation=tb.conditions.RequiredConditionV1(hint='You must upload a photo.'),
)
```
