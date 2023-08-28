# AppBatchSortItems
`toloka.client.search_requests.AppBatchSortItems`

```python
AppBatchSortItems(self, items=None)
```

Keys for sorting App batches in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.AppBatchSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — A batch ID.</li> <li>`'name'` — A batch name.</li> <li>`'created'` — A batch creation date.</li> <li>`'status'` — The item status.</li> </ul>
