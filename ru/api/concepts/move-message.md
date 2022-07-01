# Переместить цепочку сообщений

Добавляет или удаляет цепочку сообщений из папки.

Цепочки сообщений, которые находятся в папке `UNREAD`, в интерфейсе отмечены как непрочитанные.

Цепочки сообщений, находящиеся в папке `IMPORTANT`, в интерфейсе отмечены как важные.

## Запрос {#request}

#### Добавить в папку

Добавляет цепочку сообщений в папку.

{% list tabs %}

- Боевая версия

  ```bash
  POST https://toloka.yandex.com/api/v1/message-threads/<thread_id>/add-to-folders
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Песочница

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/message-threads/<thread_id>/add-to-folders
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```
{% endlist %}

#### Удалить из папки

Удаляет цепочку сообщений из папки.

{% list tabs %}

- Боевая версия

  ```bash
  POST https://toloka.yandex.com/api/v1/message-threads/<thread_id>/remove-from-folders
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Песочница

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/message-threads/<thread_id>/remove-from-folders
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```
{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**thread_id** | Идентификатор цепочки сообщений.


## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Тело запроса {#body}

```json
{
  "folders": ["UNREAD", "IMPORTANT"]
}
```


#|
||**Параметр**| **Описание**||
||**folders** | **array of strings**

Папки, в которые нужно добавить или из которых надо удалить цепочку сообщений.||
|#
