# Быстрые ответы

## Описание {#about}

Вы можете закрыть доступ к заданиям, если исполнитель отвечает слишком быстро. Для этого задайте значения ключей в массиве `quality_control.configs` в настройках пула.

## Тело запроса {#body}

Доступ к страницам с заданиями прекращается, если 4 из 10 ответов даны слишком быстро. Минимальная скорость ответа — 3 секунды.

Вы можете заблокировать доступ исполнителя к проекту на необходимое количество дней, часов, минут (по отдельности и в совокупности) или навсегда.

#### Блокировка на 10 дней

```json
{
   "configs": [
      {
         "collector_config": {
            "type": "ASSIGNMENT_SUBMIT_TIME",
            "parameters": {
               "history_size": 10,
               "fast_submit_threshold_seconds": 3
            }
         },
         "rules": [
            {
               "conditions": [
                  {
                     "key": "total_submitted_count",
                     "operator": "EQ",
                     "value": 10
                  },
                  {
                     "key": "fast_submitted_count",
                     "operator": "GTE",
                     "value": 4
                  }
               ],
               "action": {
                  "type": "RESTRICTION_V2",
                  "parameters": {
                     "scope": "PROJECT",
                     "duration_unit": "DAYS",
                     "duration": 10,
                     "private_comment": "More than 4 quick responses"
                  }
               }
            }
         ]
      }
   ]
}
```

Чтобы задать другой период блокировки, измените значение соответствующего [параметра](goldenset.md#configs-rules-action-parameters-duration) ключа `action`:

{% list tabs %}

- на 12 часов

  ```json
  {
     ...
                 "action": {
                    "type": "RESTRICTION_V2",
                    "parameters": {
                       "scope": "PROJECT",
                       "duration_unit": "HOURS",
                       "duration": 12,
                       "private_comment": "More than 4 quick responses"
                    }
                 }
     ...
  }
  ```

- на 30 минут

  ```json
  {
     ...
                 "action": {
                    "type": "RESTRICTION_V2",
                    "parameters": {
                       "scope": "PROJECT",
                       "duration_unit": "MINUTES",
                       "duration": 30,
                       "private_comment": "More than 4 quick responses"
                    }
                 }
     ...
  }
  ```

- навсегда

  ```json
  {
     ...
                 "action": {
                    "type": "RESTRICTION_V2",
                    "parameters": {
                       "scope": "PROJECT",
                       "duration_unit": "PERMANENT",
                       "private_comment": "More than 4 quick responses"
                    }
                 }
     ...
  }
  ```

{% endlist %}

#|
||**Параметр**| **Описание**||
||**configs[]** | **array of objects \| обязательный**

Массив настроек контроля качества.||
||**configs.collector_config** | **object \| обязательный**

Параметры для сбора статистики (например, количество пропусков заданий в пуле).||
||**configs.collector_config.type** | **string \| обязательный**

Критерий, на котором основан блок качества:
- `GOLDEN_SET` — количество правильных и неправильных ответов в контрольных заданиях.
- `MAJORITY_VOTE` — доля ответов, которые совпали с мнением большинства.
- `CAPTCHA` — количество успешно и неуспешно введенных капч.
- `INCOME` — плата за задания, выполненные исполнителем за последние 24 часа.
- `SKIPPED_IN_ROW_ASSIGNMENTS` — количество пропущенных подряд страниц заданий.
- `ANSWER_COUNT` — количество страниц заданий, выполненных исполнителем в пуле.
- `ASSIGNMENT_SUBMIT_TIME` — количество «быстрых» ответов (минимальная скорость ответа задается в параметрах).
- `ACCEPTANCE_RATE` — доля ответов исполнителя, которые были отклонены при отложенной приемке заданий.
- `ASSIGNMENTS_ASSESSMENT` — количество принятых или отклоненных заданий при включенной отложенной приемке заданий.
- `USERS_ASSESSMENT` — значение навыка исполнителя и его блокировка.||
||**configs.collector_config. parameters.fast_submit_ threshold_seconds** | **integer \| обязательный**

Минимальная приемлемая скорость ответа в секундах.||
||**configs.collector_config. parameters.history_size** | **integer \| обязательный**

Максимальное количество последних ответов исполнителя в рамках проекта, которое нужно учитывать при подсчете доли правильных ответов.
Если поле отсутствует, в расчете учитываются все ответ исполнителя в рамках пула.||
||**configs.rules.conditions** | **object \| обязательный**

Условия (например, пропуск 10 страниц заданий подряд). Несколько условий объединяются с помощью оператора «или».||
||**configs.rules.conditions.key** | **string \| обязательный**

Значения, которые проверяются в условии:
- `total_submitted_count` — количество последних ответов исполнителя (меньше либо равно `history_size`).
- `fast_submitted_count` — количество быстрых ответов (из последних).||
||**configs.rules.conditions. operator** | **string \| обязательный**
Оператор сравнения (данные `key` сравниваются с пороговым значением из `value`):
- `EQ` («Equal») — равно.
- `NE` («Not equal to») — не равно.
- `GT` («Greater than») — больше чем.
- `LT` («Less than») — меньше чем.
- `GTE` («Greater than equal to») — больше или равно.
- `LTE` («Less than equal to») — меньше или равно.||
||**configs.rules.conditions. value** | **integer \| обязательный**

Пороговое значение переменной, указанной в `key`.||
||**configs.rules.action** | **object \| обязательный**

Действие в случае выполнения условий (например, закрыть доступ к проекту).||
||**configs.rules.action.type** | **string \| обязательный**

Тип действия:
- `RESTRICTION_V2` — заблокировать доступ к проектам или пулам.
- `SET_SKILL_FROM_OUTPUT_FIELD` — присвоить навыку значение «доля правильных ответов» (используется в блоках [Контрольный набор](goldenset.md) и [Мнение большинства](mv.md)).
    Значение навыка можно использовать для отбора исполнителей.
- `CHANGE_OVERLAP` — изменить перекрытие. Например, чтобы повторно отправить страницу заданий на выполнение другим исполнителям или отменить повторное выполнение уже принятых заданий.
- `REJECT_ALL_ASSIGNMENTS` — отклонить все ответы исполнителя. Например, спустя несколько ответов исполнителя стало понятно, что он некачественно выполняет задания.
- `APPROVE_ALL_ASSIGNMENTS` — принять все ответы исполнителя. Например, если исполнитель выполняет большинство заданий качественно и вас устраивает такой результат.
- `SET_SKILL` — присвоить навыку указанное константное значение.||
||**configs.rules.action. parameters** | **object \| обязательный**

Параметры действия.||
||**configs.rules.action. parameters.scope** | **string \| обязательный**

Уровень ограничения:
- `POOL` — пул. Не влияет на рейтинг исполнителя.
- `PROJECT` — проект. Влияет на рейтинг исполнителя.
- `ALL_PROJECTS` — все проекты заказчика.||
||**configs.collector_config. parameters** | **object \| обязательный при условии**

Обязательный, если `configs.collector_config.type=``GOLDEN_SET`, `MAJORITY_VOTE`, `CAPTCHA`, `ASSIGNMENT_SUBMIT_TIME`.
Параметры для сбора данных (зависят от блока контроля качества, указанного в ключе `type`).||
||**configs.rules.action. parameters.skill_id** | **string \| обязательный при условии**

Обязателен, если `type=SET_SKILL_FROM_OUTPUT_FIELD`.
Идентификатор навыка, который необходимо обновлять по мере выполнения заданий.||
||**configs.rules.action. parameters.from_field** | **string \| обязательный при условии**

Обязателен, если `type=SET_SKILL_FROM_OUTPUT_FIELD`.
Значение, которое нужно присвоить навыку:
- `correct_answers_rate` — доля правильных ответов;
- `wrong_answers_rate` — доля неправильных ответов.||
||**configs.rules.action. parameters.skill_value** | **integer \| обязательный при условии**

Обязателен, если `type=SET_SKILL_FROM_OUTPUT_FIELD`.
Фиксированное значение, которое нужно присвоить навыку (число от 0 до 100).||
||**configs.rules.action. parameters.delta** | **integer \| обязательный при условии**

Обязателен, если `type=CHANGE_OVERLAP`.
Значение определяет, на сколько изменить перекрытие.||
||**configs.rules.action. parameters.public_comment** | **string \| обязательный при условии**

Обязателен, если `type=REJECT_ALL_ASSIGNMENTS`.
Комментарий (причина отклонения ответов). Доступен заказчику и исполнителю.||
||**configs.rules.action. parameters.duration_unit** | **string**

Единица измерения длительности блокировки:
- `MINUTES` — минуты;
- `HOURS` — часы;
- `DAYS` — дни;
- `PERMANENT` — навсегда.||
||**configs.rules.action. parameters.duration** | **integer**

Длительность блокировки.||
||**configs.rules. action.parameters. private_comment** | **string**

Комментарий (причина блокировки). Доступен только заказчику.||
||**configs.rules.action. parameters.open_pool** | **boolean**

Определяет, нужно ли открыть закрытый пул:
- `true` — открыть пул после изменения, если он закрыт.
- `false` — не открывать пул после изменения, если он закрыт.||
|#

