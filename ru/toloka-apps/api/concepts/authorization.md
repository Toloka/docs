# Доступ к API

При запросах к API для авторизации вам потребуется OAuth-токен.

**Пример запроса**

```http
GET /api/app/v0/apps
Host: https://toloka.dev
Authorization: OAuth <OAuth token>
```

## Получение OAuth-токена

- [Зарегистрируйтесь](https://toloka.ai/ru/docs/guide/concepts/access.html) в Толоке.

- Получите OAuth-токен в [кабинете заказчика](https://platform.toloka.ai/ru/requester/profile/integration).

<a target="_blank" href="https://yastatic.net/s3/doc-binary/src/support/toloka/ru/api/get-oauth-token.png"><img src="https://yastatic.net/s3/doc-binary/src/support/toloka/ru/api/get-oauth-token.png" alt="Доступ к API" style="border:1px solid #ccc;border-radius:6px;cursor:zoom-in;width:700px;" /></a>

{% include [contact-support](../../_includes/contact-support.md) %}