# TemplateBuilderViewSpec
`toloka.client.project.view_spec.TemplateBuilderViewSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/project/view_spec.py#L115)

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

A template builder view specification that defines an interface with


template builder components

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`view`|**-**|
`plugins`|**-**|
`vars`|**-**|
`core_version`|**Optional\[str\]**|<p>Default template components version. Most likely you do not need to change this parameter.</p>
`infer_data_spec`|**Optional\[bool\]**|<p>You can configure the data specification automatically or manually. You can change the way the specification is configured using the infer_data_spec option:</p> <ul> <li>`True` – The specifications of input and output data are generated automatically depending on the task interface settings.</li> <li>`False` – You can configure the specification manually. In this case, automatic detection of input and output data doesn&#x27;t work.   You may need to enable this option if: <ul> <li>You don&#x27;t want the specification version to be affected by changes in the instructions or other project fields.</li> <li>You have fields that you need but they become optional or are deleted after automatic generation.</li> </ul> </li> </ul>

**Examples:**

How to declare simple interface:

```python
import toloka.client.project.template_builder as tb
project_interface = toloka.project.view_spec.TemplateBuilderViewSpec(
    view=tb.view.ListViewV1(
        items=[header, output_field, radiobuttons],
        validation=some_validation,
    ),
    plugins=[plugin1, plugin2]
)
# add 'project_interface' to 'toloka.project.Project' instance
```
