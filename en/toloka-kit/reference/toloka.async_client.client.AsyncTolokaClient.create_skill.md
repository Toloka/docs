# create_skill
`toloka.async_client.client.AsyncTolokaClient.create_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L0)

Creates a new skill.


You can send a maximum of 10 requests of this kind per minute and 100 requests per day.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**Optional\[str\]**|<p>The skill name.</p>
`public_name`|**Optional\[Dict\[str, str\]\]**|<p>The skill name visible to Tolokers. The name can be provided in several languages.</p>
`public_requester_description`|**Optional\[Dict\[str, str\]\]**|<p>The skill description visible to Tolokers. The description can be provided in several languages.</p>
`private_comment`|**Optional\[str\]**|<p>Comments visible to a requester.</p>
`hidden`|**Optional\[bool\]**|<p>Visibility of the skill values to Tolokers:</p> <ul> <li>`True` — Tolokers don't see the information about the skill.</li> <li>`False` — Tolokers see the name and the value of the assigned skill.</li> </ul> <p>Default value: `True`.</p>
`skill_ttl_hours`|**Optional\[int\]**|<p>A lifetime in hours. If the skill value assigned to a Toloker is not updated for `skill_ttl_hours`, the skill is removed from a Toloker's profile.</p>
`training`|**Optional\[bool\]**|<p>Whether the skill is related to a training pool:</p> <ul> <li>`True` — The skill value is set after completing a training pool.</li> <li>`False` — The skill isn't related to a training pool.</li> </ul>
`owner`|**Optional\[[Owner](toloka.client.owner.Owner.md)\]**|<p>The skill owner.</p>
`id`|**-**|<p>The skill ID. Read-only field.</p>
`created`|**-**|<p>The UTC date and time when the skill was created. Read-only field.</p>

* **Returns:**

  The skill with updated read-only fields.

* **Return type:**

  [Skill](toloka.client.skill.Skill.md)

**Examples:**


```python
new_skill = toloka_client.create_skill(
    name='Area selection of road signs',
    public_requester_description={
        'EN': 'Tolokers annotate road signs',
        'FR': "Les Tolokers annotent les signaux routier",
    },
)
print(new_skill.id)
```
