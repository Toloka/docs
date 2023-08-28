# ProjectSortItems
`toloka.client.search_requests.ProjectSortItems`

```python
ProjectSortItems(self, items=None)
```

Keys for sorting projects in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.ProjectSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — A project ID.</li> <li>`'created'` — A project creation date.</li> <li>`'public_name'` — A project name.</li> <li>`'private_comment'` — A project private comment.</li> </ul>

**Examples:**

The example shows how to find active projects sorted by names in the descending order. Projects with equal names are sorted by IDs in the ascending order.

```python
sort = toloka.client.search_requests.ProjectSortItems(['-public_name', 'id'])
result = toloka_client.find_projects(status='ACTIVE', sort=sort, limit=50)
```
