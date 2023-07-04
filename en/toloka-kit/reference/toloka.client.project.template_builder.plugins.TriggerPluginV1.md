# TriggerPluginV1
`toloka.client.project.template_builder.plugins.TriggerPluginV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/plugins.py#L136)

```python
TriggerPluginV1(
    self,
    *,
    action: Optional[BaseComponent] = None,
    condition: Optional[BaseComponent] = None,
    fire_immediately: Optional[Union[BaseComponent, bool]] = None,
    on_change_of: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A plugin for triggering actions when events occur.


For more information, see [plugin.trigger](https://toloka.ai/docs/template-builder/reference/plugin.trigger).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`action`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>An action to trigger.</p>
`condition`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A condition that must be met in order to trigger the action.</p>
`fire_immediately`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>If `True` then the action is triggered immediately after the task is loaded.</p>
`on_change_of`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The data change event that triggers the action.</p>

**Examples:**

How to save Toloker's coordinates.

```python
coordinates_save_plugin = tb.plugins.TriggerPluginV1(
    fire_immediately=True,
    action=tb.actions.SetActionV1(
        data=tb.data.OutputData(path='toloker_coordinates'),
        payload=tb.data.LocationData()
    ),
)
```
