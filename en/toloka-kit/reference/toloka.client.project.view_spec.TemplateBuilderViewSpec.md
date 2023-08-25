# TemplateBuilderViewSpec
`toloka.client.project.view_spec.TemplateBuilderViewSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/view_spec.py#L122)

```python
TemplateBuilderViewSpec(
    self,
    *,
    settings: Optional[ViewSpec.Settings] = None,
    view: Optional[BaseComponent] = None,
    plugins: Optional[List[BaseComponent]] = None,
    vars: Optional[Dict[str, Any]] = None,
    core_version: Optional[str] = '1.0.0',
    infer_data_spec: Optional[bool] = False
)
```

A task interface defined with the [TemplateBuilder](toloka.client.project.template_builder.TemplateBuilder.md).


See also [Template Builder](https://toloka.ai/docs/template-builder/) in the guide.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`view`|**-**|<p>A top level component like [SideBySideLayoutV1](toloka.client.project.template_builder.layouts.SideBySideLayoutV1.md).</p>
`plugins`|**-**|<p>An array of plugins.</p>
`vars`|**-**|<p>Reusable data. It is referenced with the [RefComponent](toloka.client.project.template_builder.base.RefComponent.md).</p>
`core_version`|**Optional\[str\]**|<p>The default template components version. Most likely, you do not need to change this parameter.</p>
`infer_data_spec`|**Optional\[bool\]**|<ul> <li>`True` – The specifications of input and output data are generated automatically depending on the task interface settings.</li> <li>`False` – You configure the specifications manually, if: <ul> <li>You don&#x27;t want the specification to be affected by changes in instructions or other project parameters.</li> <li>You have to change automatically generated specifications to suite your needs.</li> </ul> </li> </ul>

**Examples:**

Creating a simple interface based on [ListViewV1](toloka.client.project.template_builder.view.ListViewV1.md):

```python
import toloka.client.project.template_builder as tb
project_interface = toloka.client.project.view_spec.TemplateBuilderViewSpec(
    view=tb.view.ListViewV1(
        items=[header, output_field, radiobuttons],
        validation=some_validation,
    ),
    plugins=[plugin1, plugin2]
)
# add 'project_interface' to 'toloka.project.Project' instance
```
