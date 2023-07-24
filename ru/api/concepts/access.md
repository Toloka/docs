# Доступ к API

{% include [announce](../_includes/announce.md) %}

В запросах к API Толоки нужно указать URL ресурса и OAuth-токен.

#### Пример запроса

```bash
GET https://sandbox.toloka.dev/api/v1/assignments?pool_id=12345
Authorization: ApiKey PlaceYourRealApiKey_Here
```

## URL ресурса {#urls}

- Для запросов к песочнице: `https://sandbox.toloka.dev/api/v1/<путь к ресурсу>`.

- Для запросов к боевой версии: `https://toloka.dev/api/v1/<путь к ресурсу>`.

## Получение OAuth-токена {#token}

Для работы с API Толоки нужно получить OAuth-токен. [Зарегистрируйтесь](../../guide/concepts/access.md) в Толоке и получите OAuth-токен в кабинете заказчика:

- В песочнице для отладки заданий: [https://sandbox.toloka.yandex.com/ru/requester/profile/integration]({{ sandbox-requester-profile-integration }}).

- В боевой версии Толоки: [https://platform.toloka.ai/ru/requester/profile/integration]({{ requester-profile-integration }}).

![Доступ к API](../_images/get-oauth-token.png =700x)

{% include [image-styles](../../../_includes/image-styles-internal.md) %}