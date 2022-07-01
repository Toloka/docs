# Создать навык

Создает навык.

{% note alert %}

Можно отправить не более 10 таких запросов в минуту и не более 100 в день.

{% endnote %}


## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  POST https://toloka.yandex.com/api/v1/skills
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Песочница

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/skills
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Тело запроса {#body}

```json
{
    "name": "Determining the color of an elephant",
    "private_comment": "Skill for my pool",
    "hidden": true,
    "skill_ttl_hours": 240
}
```

#|
||**Параметр**| **Описание**||
||**name** | **string \| обязательный**

Название навыка.||
||**private_comment** | **string**

Комментарий к навыку (доступен только заказчику).||
||**hidden** | **boolean**

Доступ к сведениям о навыке (название и значение) для исполнителей:
- `true` — закрыт;
- `false` — открыт.
По умолчанию значение `true`.||
||**skill_ttl_hours** | **integer**

Время жизни навыка после последнего обновления (в часах). Навык будет удален у исполнителя, если его значение не обновлялось в течение указанного срока.||
|#


## Ответ {#response}

Свойства и идентификатор навыка.

```json
{
    "id": "9238",
    "name": "Determining the color of an elephant",
    "private_comment": "Skill for my pool",
    "hidden": true,
    "skill_ttl_hours": 240,
    "deprecated": false,
    "owner": {
        "id": "c3a50f44cd3e1b8202465569ced289eb",
        "myself": true
    },
    "created": "2021-12-01T08:37:03.387",
    "global": false
}
```

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор навыка.||
||**name** | **string**

Название навыка.||
||**private_comment** | **string**

Комментарий к навыку (доступен только заказчику).||
||**hidden** | **boolean**

Доступ к сведениям о навыке (название и значение) для исполнителей:
- `true` — закрыт;
- `false` — открыт.
По умолчанию значение `true`.||
||**skill_ttl_hours** | **integer**

Время жизни навыка после последнего обновления (в часах). Навык будет удален у исполнителя, если его значение не обновлялось в течение указанного срока.||
||**deprecated** | **boolean**

Прекращение поддержки навыка его создателем:
- `true` — поддержка прекращена, навык требует замены;
- `false` — поддержка ведется, навык актуальный.||
||**owner** | **object**

Параметры заказчика, который создал проект.||
||**owner.id** | **string**

Идентификатор заказчика.||
||**owner.myself** | **boolean**

Проверяет, кому принадлежит объект:
- `true` — исполнителю, чей OAuth-токен указан в запросе;
- `false` — другому аккаунту (сотруднику или владельцу).||
||**training** | **boolean**

Связь навыка с обучающим пулом:
- `true` — навык подсчитывается по заданиям обучающего пула;
- `false` — навык не связан с обучающим пулом.||
||**created** | **string**

Дата и время создания навыка по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
||**global** | **boolean**

Признак глобального навыка:
- `true` — навык [глобальный]({{ requester-skills-global }}), показывает общие компетенции исполнителей, доступен всем исполнителям;
- `false` — навык создан заказчиком, может быть [назначен]({{ requester-assign-skills }}) исполнителям как вручную, так и автоматически: с помощью правил контроля качества или после прохождения обучения.||
|#
