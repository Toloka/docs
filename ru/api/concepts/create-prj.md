# Создать проект

Создает проект.

{% note alert %}

Вы можете отправить не более 20 таких запросов в минуту и не более 100 в день.

{% endnote %}


## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  POST https://toloka.yandex.com/api/v1/projects
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON

  {<project parameters>}
  ```

- Песочница

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/projects
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON

  {<project parameters>}
  ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Тело запроса {#body}

```json
{
  "public_name": "Elephant color",
  "public_description": "What color is the elephant in the picture?",
  "public_instructions": "<p>Look at the picture and decide what color the elephant is.</p> You can zoom in or out using the buttons:</p> <img src=\"disc/img1.png>\"",
  "private_comment": "My first project",
  "task_spec": {
    "input_spec": {
      "image": {
        "type": "URL",
        "required": true,
        "hidden": false
      }
    },
    "output_spec": {
      "result": {
        "type": "string",
        "required": true,
        "hidden": false
      }
    },
    "view_spec": {
      "assets": {
        "script_urls": ["library1.js", "library2.js"]
      },
      "markup": "<task interface code>",
      "script": "<JavaScript code>",
      "styles": "<CSS code>",
      "settings": {
        "showSkip": true,
        "showTimer": true,
        "showTitle": true,
        "showSubmit": true,
        "showFullscreen": true,
        "showInstructions": true,
        "showFinish": true,
        "showMessage": true,
        "showReward": true
      }
    }
  },
  "assignments_issuing_type": "AUTOMATED",
  "assignments_automerge_enabled": false,
  "max_active_assignments_count": 15,
  "quality_control": {
    "configs": [{
      "collector_config": {
        "type": "SKIPPED_IN_ROW_ASSIGNMENTS"
      },
      "rules": [{
        "conditions": [{
          "key": "skipped_in_row_count",
          "operator": "GTE",
          "value": 10
        }],
        "action": {
          "type": "REJECT_ALL_ASSIGNMENTS",
          "parameters": {
            "public_comment": "Skipped more than 10 task suites in a row"
          }
        }
      }]
    }]
  },
  "localization_config": {
    "default_language": "EN",
    "additional_languages": [
      {
        "language": "RU",
        "public_name": {
          "value": "Цвет слона",
          "source": "REQUESTER"
        },
        "public_description": {
          "value": "Какого цвета слон на картинке?",
          "source": "REQUESTER"
        },
        "public_instructions": {
          "value": "<p>Рассмотрите изображение и определите цвет слона.</p> Картинку можно увеличить или уменьшить при помощи кнопок:</p> <img src=\"disc/img1.png>\"",
          "source": "REQUESTER"
        }
      }
    ]
  }
}
```
#|
||Параметр | Описание||
||**public_name** | **string \| обязательный**

Название проекта. Его увидят исполнители.||
||**public_description** | **string \| обязательный**

Описание проекта. Его увидят исполнители.||
||**task_spec** | **object \| обязательный**

Параметры входных и выходных данных, интерфейса заданий.||
||**task_spec.input_spec** | **object \| обязательный**

Параметры входных данных заданий. Полный список параметров приведен в таблице [Входные и выходные данные](#in-out).||
||**task_spec.output_spec** | **object \| обязательный**

Параметры выходных данных — полей ввода. Полный список параметров приведен в таблице [Входные и выходные данные](#in-out).||
||**task_spec.view_spec** | **object**

Описание интерфейса задания. Полный список параметров приведен в таблице [Интерфес задания](#view-spec-section).||
||**assignments_issuing_view_ config** | **string \| обязательный при условии**

Обязателен, если `assignments_issuing_type=MAP_SELECTOR`.

Настройки отображения пешеходных заданий. Полный список параметров приведен в таблице [Настройки отображения пешеходных заданий](#assignments-issuing-view-config-section).||
||**public_instructions** | **string**

Инструкция по выполнению заданий. В инструкции можно использовать любую HTML-разметку.||
||**private_comment** | **string**
Комментарий, доступный только заказчику.||
||**assignments_issuing_type** | **string**

Способ выдачи заданий:

- `AUTOMATED` — исполнителю выдается страница заданий из пула. Вы можете [настроить](create-pool.md#issue_task_suites_in_creation_order), в каком порядке выдаются страницы заданий.
- `MAP_SELECTOR` — исполнитель выбирает страницу заданий на карте. При выборе способа `MAP_SELECTOR` укажите текст для отображения в названии и описании карты в ключе `assignments_issuing_view_config`:

  ```json
  "assignments_issuing_view_config": {
      "title_template": "<task name>",
      "description_template": "<brief description of the task>",
      "map_provider": "YANDEX"}
  ```

  По умолчанию значение `AUTOMATED`.||
||**assignments_issuing_view_config.map_provider** | **string**

Параметр можно использовать, если в проекте `"assignments_issuing_type": "MAP_SELECTOR"`.

Провайдер карт для выполнения задач:

- `GOOGLE` — Карты Google.

- `YANDEX` — Яндекс Карты.

Если параметр не задан, то выбор карты определяется исполнителем.||
||**assignments_automerge_ enabled** | **boolean**

Разрешить [слияние идентичных заданий](tasks.md#task-merge) в проекте. По умолчанию значение `false`.||
||**max_active_assignments_ count** | **integer**

Количество страниц, которые исполнитель может одновременно выполнять (статус «Активно»).||
||**quality_control** | **object**

Блок контроля качества.||
||**quality_control.configs[]** | **array of objects**

[Наборы правил](quality_control.md)||
||**localization_config** | **object**

Блок перевода на другие языки. Полный список параметров приведен в таблице [Переводы на другие языки](#localization-config).

Подробнее о переводе см. в документе [Перевод на другие языки]({{ requester-project-languages }}).||
|#


## Входные и выходные данные (input_spec и output_spec) {#in-out}

Параметры `input_spec` и `output_spec` содержат JSON со свойствами входных данных и параметрами для валидации ответов. В них нужно определить тип данных (строка, число, url и т.д.) и указать параметры для валидации (например, длина строки).

#|
||Параметр | Описание||
||**<идентификатор>** | **object \| обязательный**

- Для входных данных — идентификатор объекта для отображения в задании и его свойства.
- Для выходных данных — идентификатор поля ввода ответа и параметры для валидации ответа.||
||**type** | **string \| обязательный**

Тип данных:
- `url` — URL картинки, страницы и т. д.;
- `boolean` — логический тип данных (`true`/`false`);
- `integer` — целое число;
- `string` — строка;
- `float` — число с плавающей точкой;
- `json` — объект JSON;
- `file` — файл (только для выходных данных);
- `coordinates` — географические координаты (например, «53.910236, 27.531110»).||
||**required** | **boolean**

Обязательность объекта или поля ввода. По умолчанию значение `true`.||
||**hidden** | **boolean**

Скрыть ли от исполнителя поле с входным значением. По умолчанию значение `false`.
Для выходных данных всегда `false`.||
||**min_value** | **float**

Минимальное значение числа.||
||**max_value** | **float**

Максимальное значение числа.||
||**allowed_values[]** | **array of strings, array of integers, array of floats**

Допустимые значения.
Задание допустимых значений повышает качество [агрегации результатов](aggregated-solutions.md).||
||**min_length** | **integer**

Минимальная длина строки.||
||**max_length** | **integer**

Максимальная длина строки.||
||**current_location** | **string**

Только в выходных данных типа `coordinates`: заполнение поля текущими координатами исполнителя (`true`/`false`). Используется в заданиях для мобильного приложения.||
|#


## Интерфейс задания (view_spec) {#view-spec-section}

#|
||Параметр | Описание||
||**markup** | **string \| обязательный**

Подробнее см. в документе [Руководство заказчика]({{ requester }}).||
||**script** | **string \| обязательный**

JavaScript-интерфейс задания.

Подробнее см. в документе [Руководство заказчика]({{ requester }}).||
||**styles** | **string \| обязательный**

CSS-интерфейс задания.

Подробнее см. в документе [Руководство заказчика]({{ requester }}).||
||**settings** | **object \| обязательный**

Необходимость отображения стандартных элементов интерфейса в задании.||
||**assets** | **object**
Подключенные файлы:
- CSS-стили;
- JavaScript-библиотеки;
- ресурсы Толоки с префиксом `$TOLOKA_ASSETS`.

 Добавляйте элементы в том порядке, в котором они должны подключаться при запуске интерфейса задания.||
||**assets.script_urls[]** | **array of strings**
Ссылки на JavaScript-библиотеки и ресурсы Толоки.
Ресурсы Толоки:
- `$TOLOKA_ASSETS/js/toloka-handlebars-templates.js` — хелперы Handlebars (см. [описание на сайте шаблонизатора]({{ handlebarsjs-com }}));
- `$TOLOKA_ASSETS/js/image-annotation.js` — интерфейс разметки картинок (см. в разделе [Картинка с возможностью выделения областей]({{ requester-image-annotation }}) Руководства заказчика).

Интерфейс разметки картинок нужно подключать только вместе с хелперами Handlebars. Порядок подключения важен:
```
 "script_urls": ["$TOLOKA_ASSETS/js/toloka-handlebars-templates.js",
 "$TOLOKA_ASSETS/js/image-annotation.js"]
```
||
||**assets.style_urls[]** | **array of strings**

Ссылки на CSS-библиотеки.||
||**type** | **string**

Тип редактора:
- `tb` — конструктор шаблонов.||
||**localizationConfig** | **object**

Конфигурация редактора.
В конструкторе шаблонов добавьте в это поле ключи для свойств текстовых компонентов, которые вам нужно перевести на другие языки.
Подробнее см. в разделе [Перевод интерфейса задания]({{ requester-interface-translate }}).||
||**localizationConfig.keys** | **string**

Ключи на исходном языке.

{% include [create-prj-requester-interface-translate](../_includes/concepts/create-prj/id-create-prj/requester-interface-translate.md) %}||
||**settings.showTimer** | **boolean**

Показывать таймер. По умолчанию значение `true`.||
||**settings.showTitle** | **boolean**

Показывать название проекта в заголовке заданий. По умолчанию значение `true`.||
||**settings.showInstructions** | **boolean**

Показывать кнопку **Инструкция**. По умолчанию значение `true`.||
||**settings.showFullscreen** | **boolean**

Показывать кнопку **Развернуть задание на всю страницу**. По умолчанию значение `true`.||
||**settings.showSubmit** | **boolean**

Показывать кнопку **Дальше**. По умолчанию значение `true`.||
||**settings.showSkip** | **boolean**

Показывать кнопку **Пропустить**. По умолчанию значение `true`.||
||**settings.showFinish** | **boolean**

Показывать кнопку **На главную**. По умолчанию значение `true`.||
||**settings.showMessage** | **boolean**

Показывать кнопку **Написать заказчику**. По умолчанию значение `true`.||
||**settings.showReward** | **boolean**

Показывать цену за страницу. По умолчанию значение `true`.||
|#

## Настройки отображения пешеходных заданий (assignments_issuing_view_ config) {#assignments-issuing-view-config-section}

#|
||Параметр | Описание||
||**title_template** | **string \| обязательный при условии**

Обязателен, если `assignments_issuing_type=MAP_SELECTOR`.
Название задания. Исполнители увидят его в режиме предпросмотра задания.||
||**description_template** | **string \| обязательный при условии**

Обязателен, если `assignments_issuing_type=MAP_SELECTOR`.

Описание задания. Исполнители увидят его в режиме предпросмотра задания.||
||**map_provider** | **string**

Параметр можно использовать, если в проекте `"assignments_issuing_type": "MAP_SELECTOR"`.

Провайдер карт для выполнения задач:
- `GOOGLE` — Карты Google.
- `YANDEX` — Яндекс Карты.

Если параметр не задан, то выбор карты определяется исполнителем.||
|#


## Переводы на другие языки (localization_config) {#localization-config-section}

#|
||Параметр | Описание||
||**default_ language** | **string**

Исходный язык, на котором заполнены:
- **public_name** (**string \| обязательный** — название проекта. Его увидят исполнители)
- **public_description** (**string \| обязательный** — описание проекта. Его увидят исполнители)
- **public_instructions** (**string** — инструкция по выполнению заданий. В инструкции можно использовать любую HTML-разметку)||
||**additional_languages[]** | **array of objects**

Массив языков перевода.||
||**additional_languages[]. language** | **string**

Язык перевода.||
||**additional_languages[]. public_name** | **object**

Перевод названия проекта.

Источник перевода:
- `REQUESTER` — заказчик сам установил значение.||
||**additional_languages[]. public_description** | **object**

Перевод описания проекта.

{% include [create-prj-translate-json](../_includes/concepts/create-prj/id-create-prj/translate-json.md) %}

{% include [create-prj-translate-source](../_includes/concepts/create-prj/id-create-prj/translate-source.md) %}

- `REQUESTER` — заказчик сам установил значение.||
||**additional_languages[]. public_instructions** | **object**

Перевод инструкции по выполнению заданий.

{% include [create-prj-translate-json](../_includes/concepts/create-prj/id-create-prj/translate-json.md) %}

{% include [create-prj-translate-source](../_includes/concepts/create-prj/id-create-prj/translate-source.md) %}

- `REQUESTER` — заказчик сам установил значение.||
||**additional_languages[]. tb_view_spec** | **object**

Перевод интерфейса задания.||
||**additional_languages[]. tb_view_spec.keys[]** | **array of objects**

Ключи с переводом элементов интерфейса задания.

{% include [create-prj-translate-json](../_includes/concepts/create-prj/id-create-prj/translate-json.md) %}

{% include [create-prj-translate-source](../_includes/concepts/create-prj/id-create-prj/translate-source.md) %}

- `REQUESTER` — заказчик сам установил значение.||
|#


## Ответ {#response}

Содержит информацию о загруженном проекте в формате JSON. Проекту автоматически присваивается идентификатор.

Включает:

- [параметры, которые используются при создании проекта](#prj-param);
- параметры, которые присваиваются автоматически:

#|
||Параметр | Описание||
||**owner** | **object**

Параметры заказчика, который создал проект.||
||**owner.id** | **string**

Параметры для сортировки:||
||**owner.myself** | **boolean**

Проверяет, кому принадлежит объект:
- `true` — пользователю, чей OAuth token указан в запросе;
- `false` — другому аккаунту (сотруднику или владельцу).||
||**id** | **string**
Идентификатор проекта (присваивается автоматически).||
||**status** | **string**
Статус проекта:
- `ACTIVE` — активный;
- `ARCHIVED` — архивный.||
||**created** | **string**

Дата и время создания проекта по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
|#
