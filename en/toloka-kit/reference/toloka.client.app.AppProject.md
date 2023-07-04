# AppProject
`toloka.client.app.AppProject` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/app/__init__.py#L45)

```python
AppProject(
    self,
    *,
    app_id: Optional[str] = None,
    parent_app_project_id: Optional[str] = None,
    name: Optional[str] = None,
    parameters: Optional[Dict] = None,
    id: Optional[str] = None,
    status: Union[Status, str, None] = None,
    created: Optional[datetime] = None,
    item_price: Optional[Decimal] = None,
    errors: Optional[List[_AppError]] = None,
    read_only: Optional[bool] = None,
    app: Optional[AppLightestResult] = None
)
```

An [App](https://toloka.ai/docs/api/apps-reference/#tag--app-project) project.


An App project is based on one of App solutions. It is created with a template interface and preconfigured data specification and quality control rules.

To get available App solutions use the [get_apps](toloka.client.TolokaClient.get_apps.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_id`|**Optional\[str\]**|<p>The ID of the App solution used to create the project.</p>
`parent_app_project_id`|**Optional\[str\]**|<p>The ID of the parent project. It is set if this project is a clone of other project. Otherwise it is empty.</p>
`name`|**Optional\[str\]**|<p>The project name.</p>
`parameters`|**Optional\[Dict\]**|<p>Parameters of the solution. The parameters should follow the schema described in the `param_spec` field of the [solution](toloka.client.app.App.md).</p>
`id`|**Optional\[str\]**|<p>The ID of the project.</p>
`status`|**Optional\[[Status](toloka.client.app.AppProject.Status.md)\]**|<p>The project status:</p> <ul> <li>`CREATING` — Toloka is checking the project.</li> <li>`READY` — The project is active.</li> <li>`ARCHIVED` — The project was archived.</li> <li>`ERROR` — Project creation failed due to errors.</li> </ul>
`created`|**Optional\[datetime\]**|<p>The date and time when the project was created.</p>
`item_price`|**Optional\[Decimal\]**|<p>The price you pay for a processed item.</p>
`errors`|**Optional\[List\[[_AppError](toloka.client.app._AppError.md)\]\]**|<p>Errors found during a project check.</p>
`read_only`|**Optional\[bool\]**|<ul> <li>`True` — The project is read-only.</li> <li>`False` — The project can be modified.</li> </ul>
`app`|**Optional\[[AppLightestResult](toloka.client.app.AppLightestResult.md)\]**|<p>Brief information about the project template.</p>
