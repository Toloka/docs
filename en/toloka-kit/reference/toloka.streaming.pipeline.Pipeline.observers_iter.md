# observers_iter
`toloka.streaming.pipeline.Pipeline.observers_iter` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/streaming/pipeline.py#L214)

```python
observers_iter(self)
```

Iterate over registered observers.


* **Returns:**

  An iterator over all registered observers except deleted ones.
Might contain observers scheduled for deletion and not deleted yet.

* **Return type:**

  Iterator\[[BaseObserver](toloka.streaming.observer.BaseObserver.md)\]
