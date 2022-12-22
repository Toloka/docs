# Cooldown
`toloka.util.async_utils.Cooldown` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/util/async_utils.py#L192)

```python
Cooldown(self, cooldown_time)
```

Сontext manager that implements a delay between calls occurring inside the context

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`cooldown_time`|**-**|<p>seconds between calls</p>

**Examples:**


```python
coldown = toloka.util.Cooldown(5)
while True:
    async with coldown:
        await do_it()  # will be called no more than once every 5 seconds
```
