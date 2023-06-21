# BaseCursor
`toloka.streaming.cursor.BaseCursor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/streaming/cursor.py#L80)

```python
BaseCursor(
    self,
    toloka_client: Union[TolokaClient, AsyncTolokaClient],
    request: BaseSearchRequest,
    time_lag: timedelta = ...
)
```

Base class for all cursors.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`_time_lag`|**-**|<p>Time lag between cursor time field upper bound and real time. Default is 1 minute. This lag is required to keep cursor consistent. Lowering this value will make cursor process events faster, but raises probability of missing some events in case of concurrent operations.</p>
## Methods Summary

| Method | Description |
| :------| :-----------|
[inject](toloka.streaming.cursor.BaseCursor.inject.md)| None
[try_fetch_all](toloka.streaming.cursor.BaseCursor.try_fetch_all.md)| None
