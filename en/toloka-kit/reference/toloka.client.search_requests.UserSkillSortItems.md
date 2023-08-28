# UserSkillSortItems
`toloka.client.search_requests.UserSkillSortItems`

```python
UserSkillSortItems(self, items=None)
```

Keys for sorting skills in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.UserSkillSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — The ID of a skill.</li> <li>`'created'` — The date when a skill was created.</li> <li>`'modified'` — The date when a skill was modified.</li> </ul>

**Examples:**

The example shows how to find Tolokers' skills sorted by creation date in the descending order. Skills with equal creation dates are sorted by IDs in the ascending order.

```python
sort = toloka.client.search_requests.UserSkillSortItems(['-created', 'id'])
result = toloka_client.find_user_skills(skill_id='11294', sort=sort, limit=10)
```
