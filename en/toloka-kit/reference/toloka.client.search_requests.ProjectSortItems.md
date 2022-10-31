# ProjectSortItems
`toloka.client.search_requests.ProjectSortItems`

```python
ProjectSortItems(self, items=None)
```

Keys for sorting projects in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.ProjectSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — A project ID.</li> <li>`&#x27;created&#x27;` — A project creation date.</li> <li>`&#x27;public_name&#x27;` — A project name.</li> <li>`&#x27;private_comment&#x27;` — A project private comment.</li> </ul>

**Examples:**

The example shows how to find active projects sorted by names in descending order. Projects with equal names are sorted by IDs in ascending order.

```python
sort = toloka.client.search_requests.ProjectSortItems(['-public_name', 'id'])
result = toloka_client.find_projects(status='ACTIVE', sort=sort, limit=50)
```
