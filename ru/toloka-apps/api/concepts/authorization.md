{% include [image-styles](../../../../_includes/image-styles.md) %}

# Доступ к API

{% include [deprecate](../../../_includes/deprecate.md) %}

При запросах к API для авторизации вам потребуется OAuth-токен.

**Пример запроса**

```http
GET /api/app/v0/apps
Host: https://toloka.dev
Authorization: OAuth <OAuth token>
```

## Получение OAuth-токена

- [Зарегистрируйтесь](../../../guide/concepts/access.md) в Толоке.

- Получите OAuth-токен в [кабинете заказчика](https://platform.toloka.ai/ru/requester/profile/integration).

[![Доступ к API](https://yastatic.net/s3/doc-binary/src/toloka/ru/api/get-oauth-token.png =700x)](https://yastatic.net/s3/doc-binary/src/toloka/ru/api/get-oauth-token.png)

{% include [contact-support](../../_includes/contact-support.md) %}