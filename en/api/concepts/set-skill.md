# Set the skill value

Sets the skill value.

{% note alert %}

You can send a maximum of 100,000 requests of this kind per day.

{% endnote %}


## Request {#request}

{% list tabs %}

- Production version

  ```json
  PUT https://toloka.yandex.com/api/v1/user-skills
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Sandbox

  ```json
  PUT https://sandbox.toloka.yandex.com/api/v1/user-skills
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
  "skill_id": 32,
  "user_id": "566ec2b0ff0deeaae5f9d500",
  "value": 59.7,
  "reason": "High-quality performance of tasks"
}
```

#|
|| Parameter | Overview ||
|| **skill_id** | **string \| required**

Skill ID. ||
|| **user_id** | **string \| required**

Toloker ID. ||
|| **value** | **float \| required**

Fractional value of the skill. Minimum — 0, maximum — 100. ||
|| **Reason** | **string** 

The reason for changing or assigning a skill. ||
|#

## Response {#response}

Updated skill value.

```json
{
  "id": "43",
  "skill_id": "32",
  "user_id": "566ec2b0ff0deeaae5f9d500",
  "value": 60,
  "exact_value": 59.7,
  "created": "2021-06-17T09:30:11.681",
  "modified": "2021-05-19T10:52:22.130"
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

ID of the Toloker's skill, assigned to the "skill-user" pair. ||
|| **skill_id** | **string**

Skill ID. ||
|| **user_id** | **string**

Toloker ID. ||
|| **value** | **integer**

The integer value of that skill (`exact_value`, rounded to the nearest integer). Minimum — 0, maximum — 100. ||
|| **exact_value** | **float**

Fractional value of the skill. Minimum — 0, maximum — 100. ||
|| **created** | **string**

The date and time in UTC when the Toloker was first assigned the skill with the specified value. It uses ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **modified** | **string**

The date and time in UTC when the Toloker's skill level changed. It uses ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|#

