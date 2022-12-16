# RunState
`toloka.streaming.pipeline.Pipeline.RunState` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/streaming/pipeline.py#L255)

```python
RunState(
    self,
    pipeline_key: str,
    workers: Dict[_Worker, None] = ...,
    waiting: Dict[_Worker, Task] = ...,
    pending: Dict[_Worker, datetime] = ...
)
```

State of a single Pipeline run.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`workers`|**Dict\[[_Worker](toloka.streaming.pipeline._Worker.md), None\]**|<p>all known workers</p>
`waiting`|**Dict\[[_Worker](toloka.streaming.pipeline._Worker.md), Task\]**|<p>currently running workers</p>
`pending`|**Dict\[[_Worker](toloka.streaming.pipeline._Worker.md), datetime\]**|<p>currently not running workers</p>
## Methods Summary

| Method | Description |
| :------| :-----------|
[add_new_observers](toloka.streaming.pipeline.Pipeline.RunState.add_new_observers.md)| None
