# AssignmentSortItems
`toloka.client.search_requests.AssignmentSortItems`

```python
AssignmentSortItems(self, items=None)
```

Keys for sorting assignments in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.AssignmentSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — An assignment ID.</li> <li>`'created'` — The assigning date of a task suite.</li> <li>`'submitted'` — The completion date of a task suite.</li> <li>`'accepted'` — The acceptance date of a task suite.</li> <li>`'rejected'` — The rejection date a task suite.</li> <li>`'skipped'` — The date when a task suite was skipped.</li> <li>`'expired'` — The expiration date of a task suite.</li> </ul>

**Examples:**

The example shows how to find assignments sorted by the completion date in the descending order. Assignments with equal completion dates are sorted by IDs in the descending order.

```python
sort = toloka.client.search_requests.AssignmentSortItems(['-submitted', '-id'])
result = toloka_client.find_assignments(pool_id='1080020', status='SUBMITTED', sort=sort, limit=10)
```
