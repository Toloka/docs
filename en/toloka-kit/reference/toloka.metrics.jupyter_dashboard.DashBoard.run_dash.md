# run_dash
`toloka.metrics.jupyter_dashboard.DashBoard.run_dash` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/metrics/jupyter_dashboard.py#L332)

```python
run_dash(
    self,
    mode: str = 'inline',
    height: int = None,
    host: str = '127.0.0.1',
    port: str = '8050'
)
```

Starts dashboard. Starts server for online updating charts.


You can stop it, by calling 'stop_dash()' for the same dashboard instance.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`mode`|**str**|<p>Same as 'mode' in jupyter_dash.JupyterDash().run_server(). Defaults to 'inline'.</p>
`height`|**int**|<p>If you don't want auto-computed height. Defaults to None - auto-compute.</p>
`host`|**str**|<p>Host for server. Defaults to '127.0.0.1'.</p>
`port`|**str**|<p>Port fo server. Defaults to '8050'.</p>
