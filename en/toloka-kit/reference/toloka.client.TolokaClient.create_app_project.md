# create_app_project
`toloka.client.TolokaClient.create_app_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3835)

```python
create_app_project(self, app_project: AppProject)
```

Creates an App project in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project`|**[AppProject](toloka.client.app.AppProject.md)**|<p>The project with parameters.</p>

* **Returns:**

  Created App project with updated parameters.

* **Return type:**

  [AppProject](toloka.client.app.AppProject.md)

**Examples:**


```python
app_project = toloka.client.AppProject(
    app_id='9lZaMl363jahzra1rrYq',
    name='Example project (product relevance)',
    parameters={
        "default_language": "en",
        "name": "Product relevance project",
        "instruction_classes": [
            {
                "description": "The product is relevant to the query.",
                "label": "Relevant",
                "value": "relevant"
            },
            {
                "description": "The product is not completely relevant to the query.",
                "label": "Irrelevant",
                "value": "irrelevant"
            }
        ],
        "instruction_examples": [
            {
                "description": "The product exactly matches the query.",
                "label": "relevant",
                "query": "some search query",
                "screenshot_url": "https://example.com/1"
            },
            {
                "description": "The product shape matches but the product color does not.",
                "label": "irrelevant",
                "query": "other search query",
                "screenshot_url": "https://example.com/2"
            }
        ]
    }
)
app_project = toloka_client.create_app_project(app_project)
print(app_project.created, app_project.status)
```
