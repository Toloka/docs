# update_charts
`toloka.metrics.jupyter_dashboard.DashBoard.update_charts` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/metrics/jupyter_dashboard.py#L302)

```python
update_charts(self, n_intervals: int)
```

Redraws all charts on each iteration

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`n_intervals`|**int**|<p>inner parameter that don't used right now</p>

* **Returns:**

  all new Figure's.
Must have the same length on each iteration.

* **Return type:**

  Union\[Figure, List\[Figure\]\]
