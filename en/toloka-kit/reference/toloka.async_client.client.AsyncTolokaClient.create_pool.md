# create_pool
`toloka.async_client.client.AsyncTolokaClient.create_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async create_pool(
    self,
    pool: Pool,
    tier: str = None
)
```

Creates a new pool in Toloka.


You can send a maximum of 20 requests of this kind per minute and 100 requests per day.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool`|**[Pool](toloka.client.pool.Pool.md)**|<p>The pool to be created.</p>
`tier`|**str**|<p>Identificator of the pool data storage tier. By default, only &#x27;default&#x27; tier is available. If no tier is specified, the pool is created in the &#x27;default&#x27; tier.</p>

* **Returns:**

  The pool with updated read-only fields.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**

Creating a new pool.

```python
import datetime
new_pool = toloka.client.Pool(
    project_id='92694',
    private_name='Pool 1',
    may_contain_adult_content=False,
    will_expire=datetime.datetime.now(datetime.timezone.utc) + datetime.timedelta(days=365),
    reward_per_assignment=0.01,
    assignment_max_duration_seconds=60*20,
    defaults=toloka.client.Pool.Defaults(default_overlap_for_new_task_suites=3),
    filter=toloka.client.filter.Languages.in_('EN'),
)
new_pool.set_mixer_config(real_tasks_count=10, golden_tasks_count=0, training_tasks_count=0)
# To configure quality control rules call new_pool.quality_control.add_action()
new_pool = toloka_client.create_pool(new_pool)
print(new_pool.id)
```
