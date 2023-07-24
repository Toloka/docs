# Получить метаданные пользователей

{% include [announce](../_includes/announce.md) %}

Получает данные пользователя через `user_id`.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-metadata/<user_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-metadata/<user_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**user_id** | Идентификатор пользователя.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Содержит метаданные пользователя в формате JSON.

```json
{
  "id": "123cdfggh",
  "country": "EN",
  "languages": [
    "EN",
    "FR"
    ],
  "adult_allowed": true,
  "attributes": {
    "country_by_phone": "EN",
    "country_by_ip": "EN",
    "client_type": "TOLOKA_APP",
    "user_agent_type": "OTHER",
    "device_category": "SMARTPHONE",
    "os_family": "IOS",
    "os_version": 15,
    "os_version_major": 15,
    "os_version_minor": 0,
    "os_version_bugfix": 0
  }
}
```