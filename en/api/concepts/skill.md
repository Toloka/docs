# Overview

A skill is an assessment of some aspect of a Toloker's responses (a number from 0 to 100). You can set up skill calculation in a [quality control rule](quality_control.md), or manually set the skill level for a Toloker. You can use skills to [select Tolokers](filter-skill.md) who perform pool tasks.

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
POST | [/skills](create-skill.md) | Creates a skill.
PUT | [/skills/\<id\>](edit-skill.md) | Changes the name, comment, and access to the skill.
PUT | [/user-skills](set-skill.md) | Sets the skill value.
GET | [/user-skills](get-user-skill-list.md) | Gets а list of Tolokers who have skills.
GET | [/user-skills/\<id\>](get-user-skill.md) | Gets a Toloker's skill value.
GET | [/skills](get-skill-list.md) | Gets the list of created skills.
GET | [/skills/\<id\>](get-skill.md) | Gets the properties of a skill.
DELETE | [/user-skills/\<id\>](delete-skill.md) | Removes a skill for a Toloker.

## Learn more {#links}

- [More information about skills](../../guide/concepts/nav.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}