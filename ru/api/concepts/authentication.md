# Аутентификация событий

{% include [deprecate](../../_includes/deprecate.md) %}

API Toloka отправляет уведомления о событиях, которые могут содержать конфиденциальные данные. Важно защитить данные от возможной утечки и обеспечить им надежную защиту. Для этого необходимо убедиться, что запросы были отправлены с помощью API Toloka.

Для подтверждения того, что источником уведомлений является API Toloka, используется дополнительный заголовок **Toloka-Signature**. Он формируется из параметров, указанных в запросе. При создании подписи используется алгоритм хеширования **HMAC Sha256**.

## Как создать защищенную подписку {#secure-subscription}

При [создании подписки](put-webhook-subscriptions.md) в тело запроса добавьте параметр **secret_key**. Он позволяет проверить, что входящие запросы были отправлены с помощью API Toloka. Если параметр добавлен, то в уведомлении о событии появится дополнительный заголовок **Toloka-Signature**.

## Валидация отправителя уведомлений {#validation}

Заголовок **Toloka-Signature** состоит из 3 полей:

- **ts** — время генерации ключа в формате Unix (миллисекунды);
- **v** — версия ключа;
- **sign** — подпись, сгенерированная с использованием алгоритма HMAC Sha256.

Чтобы проверить, что запросы были отправлены с помощью API Toloka:

1. Проверьте, что в заголовке указаны все необходимые поля. Например:

    ```bash
    Toloka-Signature : {v=1, ts=946728000000, sign=d3...ab}
    ```

1. Объедините значения **ts**, **v** и строки полезной нагрузки запроса. В качестве разделителя используйте точку.

    ```bash
    946728000000.1.{"events":...}
    ```

1. С помощью алгоритма HMAC Sha256 сгенерируйте подпись из объединенной строки и вашего секретного ключа.

    ```bash
    hmac_sha256(secret_key, '946728000000.1.{"events":...}')
    ```

1. Сравните сгенерированную подпись и подпись из заголовка **Toloka-Signature**. Если они совпадают, запросы были отправлены с помощью API Toloka.

## Пример валидации {#example-validation}

В качестве примера рассмотрим уведомление о событии, отправленное API Toloka:

```bash
POST /webhook_endpoint HTTP/1.1
Host: client_api
Toloka-Signature: {v=1, ts=946728000000, sign=609af3eefd4c12b6afad30ab456efcd21fe82f4247d3340151a3ca0c97a6cbcb}
Content-Type: application/json
Content-Length: 355

{
  "events": [
    {
      "event_time": "2000-01-01T12:00:00",
      "project_id": "project-1",
      "pool_id": "pool-1",
      "uuid": "00000000-0000-0000-0000-000000000000",
      "task_suite_id": "task-suite-1",
      "assignment_id": "assignment-1",
      "webhook_subscription_id": "subscription-1",
      "type": "ASSIGNMENT_APPROVED"
    }
  ]
}
```

Валидация этого входящего запроса осуществляется следующим образом:

```python
import hmac
import hashlib

def is_valid_signature(secret_key, request_payload, toloka_header_ts,
    toloka_header_v, toloka_header_sign):
    data = str(toloka_header_ts) + '.' + str(toloka_header_v) + '.'
    + request_payload signature = hmac.new(bytearray(secret_key.encode()),
    bytearray(data.encode()), hashlib.sha256)
    return signature.hexdigest() == toloka_header_sign

# секретный ключ, которые используется при создании подписки
secret_key = '12345'

# тело запроса, приходящего от Toloka API
request_payload = "{\"events\":[{\"event_time\":
    \"2000-01-01T12:00:00\",
    \"project_id\":\"project-1\",
    \"pool_id\":\"pool-1\",
    \"uuid\":\"00000000-0000-0000-0000-000000000000\",
    \"task_suite_id\":\"task-suite-1\",
    \"assignment_id\":\"assignment-1\",
    \"webhook_subscription_id\":\"subscription-1\",
    \"type\":\"ASSIGNMENT_APPROVED\"}]}"

# значение поля "ts", из входящего заголовка Toloka-Signature
toloka_header_ts = 946728000000

# значение поля "v", из входящего заголовка Toloka-Signature
toloka_header_v = 1

# значение поля "sign", из входящего заголовка Toloka-Signature
toloka_header_sign = '609af3eefd4c12b6afad30ab456efcd21fe82f4247d3340151a3ca0c97a6cbcb'

if (is_valid_signature(secret_key, request_payload, toloka_header_ts,
    toloka_header_v, toloka_header_sign)):
    print('Valid signature')
else:
    print('Invalid signature')
```