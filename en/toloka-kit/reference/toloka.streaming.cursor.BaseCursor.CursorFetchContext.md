# CursorFetchContext
`toloka.streaming.cursor.BaseCursor.CursorFetchContext` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/streaming/cursor.py#L84)

```python
CursorFetchContext(self, cursor: BaseCursor)
```

Context manager to return from `BaseCursor.try_fetch_all method`.


Commit cursor state only if no error occured.

