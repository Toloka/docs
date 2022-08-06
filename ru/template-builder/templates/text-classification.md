# Классификация текстов

Для такого проекта в Толоке есть пресет **Кликбейт или нет?**

Пресет помогает классифицировать любой тип текста для обучения классификаторов и NLP-моделей.

Посмотрите пример — интерфейс разметки включает блок текста и радиокнопки для разных категорий. В нем уже настроена валидация, горячие клавиши и внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/GCr6AzRu3Wk6so)

{% cut "Из каких компонентов состоит этот пример" %}

- [view.text](../reference/view.text.md) — текст, который вы хотите классифицировать.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.text",
    "label": "Headline",
    "content": {
      "type": "data.input",
      "path": "headline"
    }
  }
  ```

  {% endcut %}

- [field.button-radio-group](../reference/field.button-radio-group.md) — добавляет кнопки для выбора варианта ответа.

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.button-radio-group",
    "validation": {
      "type": "condition.required"
    },
    "label": "Is this headline clickbait?",
    "options": [
      {
        "label": "Clickbait",
        "value": "yes"
      },
      {
        "value": "no",
        "label": "Not clickbait"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "result"
    }
  }
  ```

  {% endcut %}

- [condition.required](../reference/condition.required.md) — проверяет, что выбран хотя бы один вариант.

  {% cut "Показать код" %}

  ```json
  {
    "type": "condition.required",
    "hint": "Select an option"
  }
  ```

  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания.

  {% cut "Показать код" %}

  ```json
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "scroll",
      "taskWidth": 500
    }
  }
  ```

  {% endcut %}

- [plugin.hotkeys](../reference/plugin.hotkeys.md): [горячие клавиши](../best-practices/hotkeys.md).

  {% cut "Показать код" %}

  ```json
  {
    "1": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "yes"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "no"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

Если вам не подходит этот пресет, посмотрите другие примеры в этом разделе.

## Добавить описание {#add-description}

Чтобы добавить подробное описание к заданию, используйте компонент [view.text](../reference/view.text.md).

{% cut "Показать код" %}

```json
{
  "type": "view.text",
  "content": "Read the headline and tell if it is clickbait."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/5GdOsaHz3XFSUH)

## Добавить поле для ввода ответа {#add-text-area}

Если вам нужны комментарии от исполнителя, то добавьте поле для ввода текста с помощью компонента [field.textarea](../reference/field.textarea.md).

{% cut "Показать код" %}

```json
{
  "type": "field.textarea",
  "label": "Comments",
  "placeholder": "Enter text",
  "data": {
    "type": "data.output",
    "path": "comment"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/tqcXy_dh3Wk7XR)

## Добавить оформление {#add-layout}

Чтобы исполнитель легче ориентировался в задании, вы можете оформлять цветом разные типы данных с помощью компонента [view.alert](../reference/view.alert.md). В этом примере описание выделено синей рамкой, а кнопки — желтой.

{% cut "Показать код" %}

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
    "type": "view.text",
    "content": "Look at the text and tell if it is clickbait."
  }
},
{
  "type": "view.text",
  "label": "Headline",
  "content": {
    "type": "data.input",
    "path": "headline"
  }
},
{
  "type": "view.alert",
  "theme": "warning",
  "content": {
    "type": "field.button-radio-group",
    "validation": {
      "type": "condition.required",
      "hint": "Select an option"
    },
    "label": "Is this headline clickbait?",
    "options": [
      {
        "label": "Clickbait",
        "value": "yes"
      },
      {
        "label": "Not clickbait",
        "value": "no"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "result"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/1d9wVk0A3Wk7hq)

## Другие варианты кнопок {#mult-ans-options}

Определите, может ли исполнитель выбрать несколько вариантов ответа или только один:

{% list tabs %}

- Несколько (чекбокс)

  Если ответов на вопрос может быть несколько — настройте чекбоксы [field.checkbox-group](../reference/field.checkbox-group.md).

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.checkbox-group",
    "label": "This headline is:",
    "options": [
      {
        "label": "Clickbate",
        "value": "clickbate"
      },
      {
        "label": "Too long",
        "value": "long"
      },
      {
        "label": "Gramatically incorrect",
        "value": "bad-grammar"
      },
      {
        "label": "None of this",
        "value": "none"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "input_data"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select at least one option"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/WqUYAVJ_3Wk87q)

- Один (радиокнопка)

  Компонент [field.button-radio-group](../reference/field.button-radio-group.md) отображается в виде цельных кнопок. Такие кнопки лучше подходят, когда в вопросе 2–4 варианта с короткими названиями.

  Если вариантов ответа много или названия длинные, то лучше использовать переключатель [field.radio-group](../reference/field.radio-group.md), как в примере.

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "This headline is:",
    "options": [
      {
        "label": "Clickbate",
        "value": "clickbate"
      },
      {
        "label": "Too long",
        "value": "long"
      },
      {
        "label": "Grammatically incorrect",
        "value": "bad-grammar"
      },
      {
        "label": "None of this",
        "value": "none"
      },
      {
        "label": "The text hasn't loaded",
        "value": "404"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "input_data"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select an option"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/772Lk77T3Wk8bu)

{% endlist %}

## Добавить условия {#dependencies}

С помощью [helper.if](../reference/helper.if.md) можно показывать любой элемент интерфейса только при выборе определенного ответа.

{% cut "Показать код" %}

```json
{
  "type": "helper.if",
  "condition": {
    "type": "condition.equals",
    "data": {
      "type": "data.output",
      "path": "first-q"
    },
    "to": "no"
  },
  "then": {
    "type": "field.checkbox-group",
    "label": "2. Why don't you like it?",
    "options": [
      {
        "label": "It's clickbate",
        "value": "clickbate"
      },
      {
        "label": "It's too long",
        "value": "long"
      },
      {
        "label": "It's grammarly incorrect",
        "value": "bad-grammar"
      },
      {
        "label": "Other",
        "value": "other"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "input_data"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select an option"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/FwDPOVZ_3Wk8zy)

## Сравнение текста и поискового запроса {#search}

#### Подходит ли текст под поисковый запрос

Добавьте кнопку, по которой исполнители будут открывать результаты поиска, и сформируйте ссылку поискового запроса с помощью компонента [helper.search-query](../reference/helper.search-query.md). Чтобы убедиться, что исполнитель перешел по ссылке и проверил ее содержимое, настройте валидацию, как в примере.

{% cut "Показать код" %}

```json
{
  "type": "condition.link-opened",
  "hint": "Follow the link",
  "url": {
    "type": "helper.search-query",
    "query": {
      "type": "data.input",
      "path": "link"
    },
    "engine": "bing"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/XjJKrKAq3Wk2gG)

#### Попарное сравнение с веб-страницей

С помощью компонента [view.iframe](../reference/view.iframe.md) вы можете отобразить веб-страницу во встроенном окне. Расположите рядом текст, используя [layout.side-by-side](../reference/layout.side-by-side.md).

{% cut "Показать код" %}

```json
{
  "type": "view.iframe",
  "maxWidth": 400,
  "fullHeight": true,
  "url": {
    "type": "helper.search-query",
    "query": {
      "type": "data.input",
      "path": "link"
    },
    "engine": "bing"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/IV7KDhXz3Wjv6u)

#### Попарное сравнение с веб-страницей в рамке мобильного устройства

Это более сложный пример, который сравнивает текст с результатами поискового запроса. В нем используются компоненты:

- [view.iframe](../reference/view.iframe.md) — отображает веб-страницу во встроенном окне;
- [view.device-frame](../reference/view.device-frame.md) — оборачивает окно в рамку смартфона;
- [layout.side-by-side](../reference/layout.side-by-side.md) — располагает картинку и окно с результатами запроса рядом друг с другом.

{% cut "Показать код" %}

```json
{
  "type": "layout.side-by-side",
  "items": [
    {
      "type": "view.text",
      "content": {
        "type": "data.input",
        "path": "text"
      }
    },
    {
      "type": "view.device-frame",
      "maxWidth": 400,
      "content": {
        "type": "view.iframe",
        "maxWidth": 400,
        "fullHeight": true,
        "url": {
          "type": "helper.search-query",
          "query": {
            "type": "data.input",
            "path": "link"
          },
          "engine": "bing"
        }
      }
    }
  ]
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/09flUkZu3WjxyP)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)