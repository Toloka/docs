# _Worker
`toloka.streaming.pipeline._Worker` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/streaming/pipeline.py#L28)

```python
_Worker(
    self,
    name: str,
    observer: BaseObserver,
    should_resume: bool = False
)
```

_Worker object that run observer's __call__() and should_resume() methods.


Keep track of the observer's should_resume state.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**str**|<p>Unique key to be identified by.</p>
`observer`|**[BaseObserver](toloka.streaming.observer.BaseObserver.md)**|<p>BaseObserver object to run.</p>
`should_resume`|**bool**|<p>Current observer&#x27;s should_resume state.</p>
