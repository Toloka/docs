{% include [image-styles](../../../_includes/image-styles.md) %}

# Доступ к API

{% include [announce](../_includes/announce.md) %}

В запросах к API Толоки нужно указать URL ресурса и OAuth-токен.

#### Пример запроса

```bash
GET https://sandbox.toloka.dev/api/v1/assignments?pool_id=12345
Authorization: OAuth <OAuth token>
```

## URL ресурса {#urls}

- Для запросов к песочнице: `https://sandbox.toloka.dev/api/v1/<путь к ресурсу>`.

- Для запросов к боевой версии: `https://toloka.dev/api/v1/<путь к ресурсу>`.

## Получение OAuth-токена {#token}

Для работы с API Толоки нужно получить OAuth-токен. [Зарегистрируйтесь]({{ requester-access }}) в Толоке и получите OAuth-токен в кабинете заказчика:

- В песочнице для отладки заданий: [https://sandbox.toloka.yandex.com/ru/requester/profile/integration]({{ sandbox-requester-profile-integration }}).

- В боевой версии Толоки: [https://platform.toloka.ai/ru/requester/profile/integration]({{ requester-profile-integration }}).

<a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/ru/api/get-oauth-token.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/ru/api/get-oauth-token.png" alt="Доступ к API" style="box-shadow: 1px 1px 15px rgba(30,33,38,.12);border-radius:6px;cursor:zoom-in;width:700px;" /></a>
