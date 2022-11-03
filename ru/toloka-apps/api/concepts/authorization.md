{% include [image-styles](../../../../_includes/image-styles.md) %}

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

[![Доступ к API](https://yastatic.net/s3/doc-binary/src/toloka/ru/api/get-oauth-token.png =700x)](https://yastatic.net/s3/doc-binary/src/toloka/ru/api/get-oauth-token.png)

{% include [contact-support](../../_includes/contact-support.md) %}