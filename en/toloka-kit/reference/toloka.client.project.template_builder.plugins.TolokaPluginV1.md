# TolokaPluginV1
`toloka.client.project.template_builder.plugins.TolokaPluginV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/plugins.py#L168)

```python
TolokaPluginV1(
    self,
    kind: Optional[TolokaPluginLayout.Kind] = None,
    *,
    task_width: Optional[Union[BaseComponent, float]] = None,
    notifications: Optional[Union[BaseComponent, List[BaseComponent]]] = None,
    version: Optional[str] = '1.0.0'
)
```

A plugin with extra settings for tasks in Toloka.


For more information, see [plugin.toloka](https://toloka.ai/docs/template-builder/reference/plugin.toloka).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`layout`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [TolokaPluginLayout](toloka.client.project.template_builder.plugins.TolokaPluginV1.TolokaPluginLayout.md)\]\]**|<p>Settings for the task appearance in Toloka.</p>
`notifications`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]\]\]**|<p>Notifications shown at the top of the page.</p>

**Examples:**

Setting the width of the task block on a page.

```python
import toloka.client.project.template_builder as tb
task_width_plugin = tb.plugins.TolokaPluginV1(
    kind='scroll',
    task_width=400,
)
```
