# find_projects
`toloka.client.TolokaClient.find_projects` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L1074)

Finds projects that match certain criteria.


The number of returned projects is limited. To find remaining projects call `find_projects` with updated search criteria.

To iterate over all matching projects you may use the [get_projects](toloka.client.TolokaClient.get_projects.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`status`|**Optional\[[Project.ProjectStatus](toloka.client.project.Project.ProjectStatus.md)\]**|<p>Project status. Refer to the [ProjectStatus](toloka.client.project.Project.ProjectStatus.md) page for more information on the available `status` values.</p>
`id_lt`|**Optional\[str\]**|<p>Projects with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Projects with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Projects with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Projects with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Projects created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Projects created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Projects created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Projects created after or on the specified date.</p>
`sort`|**Union\[List\[str\], [ProjectSortItems](toloka.client.search_requests.ProjectSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned projects limit. The default limit is 20. The maximum allowed limit is 300.</p>

* **Returns:**

  Found projects and a flag showing whether there are more matching projects exceeding the limit.

* **Return type:**

  [ProjectSearchResult](toloka.client.search_results.ProjectSearchResult.md)

**Examples:**

The example shows how to find projects created before a specific date.

```python
projects = toloka_client.find_projects(created_lt='2021-06-01T00:00:00')
```

If there are projects exceeding the `limit`, then `projects.has_more` is set to `True`.
