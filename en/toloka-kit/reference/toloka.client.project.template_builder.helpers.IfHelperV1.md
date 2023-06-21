# IfHelperV1
`toloka.client.project.template_builder.helpers.IfHelperV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/helpers.py#L62)

```python
IfHelperV1(
    self,
    condition: Optional[BaseComponent] = None,
    then: Optional[Any] = None,
    *,
    else_: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

The `if then else` operator.


For more information, see [helper.if](https://toloka.ai/docs/template-builder/reference/helper.if).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`condition`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A condition to check.</p>
`then`|**Optional\[Any\]**|<p>A component that is returned if the condition is `True`.</p>
`else_`|**Optional\[Any\]**|<p>A component that is returned if the condition is `False`.</p>

**Examples:**

How to conditionally show a part of the interface.

```python
hidden_ui = tb.helpers.IfHelperV1(
    condition=tb.conditions.EqualsConditionV1(tb.data.OutputData('show_me'), 'show'),
    then=tb.view.ListViewV1([header, buttons, images]),
)
```
