# Create a skill

{% include [announce](../_includes/announce.md) %}

Creates a skill.

{% note alert "Restriction" %}

You can send a maximum of 10 requests of this kind per minute and a maximum of 100 requests per day.

{% endnote %}

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/skills
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/skills
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
{
  "name": "Determining the color of an elephant",
  "private_comment": "Skill for my pool",
  "hidden": true,
  "skill_ttl_hours": 240
}
```

#|
|| Parameter | Overview ||
|| **name** | **string \| required**

Skill name. ||
|| **private_comment** | **string**

Comments on the skill (only visible to the requester). ||
|| **hidden** | **boolean**

Access to information about the skill (the name and value) for Tolokers:

- `true` — Hidden (access closed).
- `false` — Not hidden (access open).

The default value is `true`. ||
|| **skill_ttl_hours** | **integer**

The skill's "time to live" after the last update (in hours). The skill is removed from the Toloker's profile if the skill level hasn't been updated for the specified length of time. ||
|#

## Response {#response}

Skill properties and ID.

```json
{
  "id": "9238",
  "name": "Determining the color of an elephant",
  "private_comment": "Skill for my pool",
  "hidden": true,
  "skill_ttl_hours": 240,
  "deprecated": false,
  "owner": {
    "id": "c3a50f44cd3e1b8202465569ced289eb",
    "myself": true
  },
  "created": "2021-12-01T08:37:03.387",
  "global": false
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

Skill ID. ||
|| **name** | **string**

Skill name. ||
|| **private_comment** | **string**

Comments on the skill (only visible to the requester). ||
|| **hidden** | **boolean**

Access to information about the skill (the name and value) for Tolokers:

- `true` — Hidden (access closed).
- `false` — Not hidden (access open).

The default value is `true`. ||
|| **skill_ttl_hours** | **integer**

The skill's "time to live" after the last update (in hours). The skill is removed from the Toloker's profile if the skill level hasn't been updated for the specified length of time. ||
|| **deprecated** | **boolean**

Terminating skill support by its creator:

- `true`— The skill is no longer supported and needs to be replaced.
- `false` — The skill is supported and up-to-date. ||
|| **owner** | **object**

Parameters of the requester that created the project ||
|| **owner.id** | **string**

Requester ID. ||
|| **owner.myself** | **boolean**

Checks who the object belongs to:

- `true` — The Toloker whose OAuth token is specified in the request.
- `false` — Another account (employee or owner).||
|| **training** | **boolean**

Whether the skill is related to a training pool:

- `true` — The skill level is calculated from training pool tasks.
- `false` — The skill isn't related to a training pool. ||
|| **created** | **string**

The UTC date and time when the skill was created, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **global** | **boolean**

An indicator of a global skill:

- `true` — The skill is global, shows general competencies of Tolokers, and is available to all Tolokers.
- `false` — The skill is created by the requester and can be assigned to Tolokers both manually and automatically: using quality control rules or after training. ||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/nav-create.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}