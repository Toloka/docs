# FilterCondition
`toloka.client.filter.FilterCondition` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/filter.py#L52)

```python
FilterCondition(self)
```

Filters for selecting Tolokers who can access tasks.


For example, you can select Tolokers who have some skill, speak certain languages, or use a smartphone.

Filters can be combined using the `|` and  `&` operators. Some filters support the `~` operator.


**Examples:**

Filtering by language and device category.

```python
filter = (
   (toloka.client.filter.Languages.in_('EN')) &
   (toloka.client.filter.DeviceCategory == toloka.client.filter.DeviceCategory.SMARTPHONE)
)
```
