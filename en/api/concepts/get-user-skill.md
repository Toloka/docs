# Get a Toloker's skill value

Gets a Toloker's skill value.

## Request {#request}

{% list tabs %}

- Production version

  ```json
  GET https://toloka.yandex.com/api/v1/user-skills/<id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```json
  GET ihttps://sandbox.toloka.yandex.com/api/v1/user-skills/<id>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | ----- 
**id** | The ID of a Toloker's skill that is assigned to the "skill-Toloker" pair.


## Headers {#headers}

Title | Overview
----- | ----- 
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

Contains skill properties in JSON format.

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

ID of the Toloker's skill, assigned to the "skill-Toloker" pair. ||
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

