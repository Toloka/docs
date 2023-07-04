# SetActionV1
`toloka.client.project.template_builder.actions.SetActionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/actions.py#L146)

```python
SetActionV1(
    self,
    data: Optional[Union[BaseComponent, RefComponent]] = None,
    payload: Optional[Any] = None,
    *,
    version: Optional[str] = '1.0.0'
)
```

The action sets the value of a data field.


For more information, see [action.set](https://toloka.ai/docs/template-builder/reference/action.set).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [RefComponent](toloka.client.project.template_builder.base.RefComponent.md)\]\]**|<p>The data field to set.</p>
`payload`|**Optional\[Any\]**|<p>The value.</p>

**Examples:**

The [hot key](toloka.client.project.template_builder.plugins.HotkeysPluginV1.md) `1`
fills a [text field](toloka.client.project.template_builder.fields.TextFieldV1.md) with a predefined text.
The [RefComponent](toloka.client.project.template_builder.base.RefComponent.md) is used to reference the output data field.

```python
from toloka.client.project.template_builder import *
from toloka.client.project.template_builder.base import RefComponent

tb_config = TemplateBuilder(
    vars={'0': OutputData('result')},
    view=TextFieldV1(
        data=RefComponent('vars.0'),
        label=InputData('question'),
    ),
    plugins=[
        HotkeysPluginV1(
            key_1=SetActionV1(
                data=RefComponent('vars.0'),
                payload='It is not a question'
            )
        )
    ]
)
```
