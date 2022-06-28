# Ввод капчи

## Описание {#about}

Вы можете блокировать доступ к заданиям, если исполнитель неправильно ввел капчу несколько раз подряд. Для этого задайте значения ключей в массиве `quality_control.configs` в настройках пула.

## Тело запроса {#body}

Вы можете прекратить доступ исполнителя к проекту, при неправильном вводе 7 из 10 капч, на необходимое количество дней, часов, минут (по отдельности и в совокупности) или навсегда.

#### Блокировка на 10 дней

```json
{
   "captcha_frequency": "LOW",
   "configs":[
      {
         "collector_config": {
            "type": "CAPTCHA",
            "parameters": {
               "history_size": 10
            }
         },
         "rules": [
            {
               "conditions": [
                  {
                     "key": "stored_results_count",
                     "operator": "EQ",
                     "value": 10
                  },
                  {
                     "key": "success_rate",
                     "operator": "LTE",
                     "value": 70.0
                  }
               ],
               "action": {
                  "type": "RESTRICTION_V2",
                  "parameters": {
                     "scope": "PROJECT",
                     "duration_unit": "DAYS",
                     "duration": 10,
                     "private_comment": "Incorrect captcha input"
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
                       "private_comment": "Incorrect captcha input"
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
                       "private_comment": "Incorrect captcha input"
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
                       "private_comment": "Incorrect captcha input"
                    }
                 }
     ...
  }
  ```

{% endlist %}

#|
||**Параметр**| **Описание**||
||**configs.rules.conditions** | **object \| обязательный**

Условия (например, пропуск 10 страниц заданий подряд). Несколько условий объединяются с помощью оператора «или».||
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
||**configs.rules.conditions.key** | **string \| обязательный**

Значения, которые проверяются в условии:
- `stored_results_count` — количество вводов капчи (меньше или равно `history_size`).
- `success_rate` — доля успешных ответов (от 0 до 100).
- `fail_rate` — доля неуспешных ответов (от 0 до 100).||
||**configs.rules.conditions. value** | **integer \| обязательный**

Пороговое значение переменной, указанной в `key`.||
||**configs.rules.conditions. operator** | **string \| обязательный**

Оператор сравнения (данные `key` сравниваются с пороговым значением из `value`):
- `EQ` («Equal») — равно.
- `NE` («Not equal to») — не равно.
- `GT` («Greater than») — больше чем.
- `LT` («Less than») — меньше чем.
- `GTE` («Greater than equal to») — больше или равно.
- `LTE` («Less than equal to») — меньше или равно.||
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

Обязателен, если `type=SET_SKILL_FROM_OUTPUT_FIELD`.<br/><br/>Идентификатор навыка, который необходимо обновлять по мере выполнения заданий.||
||**configs.rules.action. parameters.from_field** | **string \| обязательный при условии**

Обязателен, если `type=SET_SKILL_FROM_OUTPUT_FIELD`.
Значение, которое нужно присвоить навыку:
- `correct_answers_rate` — доля правильных ответов;
- `wrong_answers_rate` — доля неправильных ответов.||
||**configs.rules.action. parameters.skill_value** | **integer \| обязательный при условии**

Обязателен, если `type=SET_SKILL_FROM_OUTPUT_FIELD`.
Фиксированное значение, которое нужно присвоить навыку (число от 0 до 100).||
||**configs.rules.action. parameters.delta** | **integer \| обязательный при условии**

Обязателен, если `type=CHANGE_OVERLAP`.<br/>Значение определяет, на сколько изменить перекрытие.||
||**configs.rules.action. parameters.public_comment** | **string \| обязательный при условии**

Обязателен, если `type=REJECT_ALL_ASSIGNMENTS`.
Комментарий (причина отклонения ответов). Доступен заказчику и исполнителю.||
||**captcha_frequency** | **string**

Частота показа капчи:
- `LOW` — показывать каждые 20 заданий.
- `MEDIUM`, `HIGH` — показывать каждые 10 заданий.
По умолчанию капча не показывается.||
||**configs.collector_config. parameters.history_size** | **integer**

Максимальное количество последних показов капчи в рамках проекта, которое нужно учитывать при подсчете.
 
Если поле отсутствует, в расчете учитываются все показы капчи при выполнении
 пула.||
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


