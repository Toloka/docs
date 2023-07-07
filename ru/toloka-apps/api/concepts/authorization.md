# Доступ к API

{% include [deprecate](../../../_includes/deprecate.md) %}

При запросах к API для авторизации вам потребуется OAuth-токен.

**Пример запроса**

```http
GET /api/app/v0/apps
Host: https://toloka.dev
Authorization: OAuth PlaceYourRealOAuthToken_Here
```

## Получение OAuth-токена

- [Зарегистрируйтесь](../../../guide/concepts/access.md) в Толоке.

- Получите OAuth-токен в [кабинете заказчика](https://platform.toloka.ai/ru/requester/profile/integration).

![Доступ к API](../../../api/_images/get-oauth-token.png =700x)

{% include [contact-support](../../_includes/contact-support.md) %}

{% include [image-styles](../../../../_includes/image-styles-internal.md) %}