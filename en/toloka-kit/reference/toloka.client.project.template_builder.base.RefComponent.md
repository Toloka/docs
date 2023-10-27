# RefComponent
`toloka.client.project.template_builder.base.RefComponent` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/base.py#L191)

```python
RefComponent(self, ref: Optional[str] = None)
```

A reference to a component.


Pass to the `RefComponent` constructor a path in the Template Builder component hierarchy.

For more information, see [Reuse code](https://toloka.ai/docs/template-builder/best-practices/reuse).


**Examples:**


```python
from toloka.client.project.template_builder import *

tb_config = TemplateBuilder(
    vars = {
        '0' : InputData('question'),
        '1' : OutputData('answer')
    },
    view = TextFieldV1(
        data = RefComponent('vars.1'),
        label = RefComponent('vars.0')
    )
)
```
