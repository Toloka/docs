# Релевантность поиска товаров

Улучшайте системы поиска в электронной коммерции, оценивая соответствие изображений товаров конкретным поисковым запросам. Интерфейс разметки включает изображение, поле для поискового запроса и радио кнопки для оценки релевантности.

Этот шаблон поможет вам улучшить систему поиска в электронной коммерции, оценивая соответствие изображений товаров конкретным поисковым запросам.

Посмотрите пример — он состоит из изображения, поля для поискового запроса и радиокнопки для оценки релевантности. В нем уже настроена валидация и внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/ajV9o-mE3UGqbd)

{% cut "Из каких компонентов состоит этот пример" %}

- [layout.sidebar](../reference/layout.sidebar.md) — позволяет разместить на странице блок с основным содержимым и примыкающую к нему панель с элементами управления.

  {% cut "Показать код" %}

  ```json
  {
    "type": "layout.sidebar",
    "minWidth": 400,
    "content": {
      "type": "view.list",
      "size": "m",
      "direction": "vertical",
      "items": []
    },
    "controls": {
      "type": "view.list",
      "direction": "vertical",
      "items": []
    }
  }
  ```

  {% endcut %}

- [view.image](../reference/view.image.md) — отображает картинку.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.image",
    "maxWidth": 350,
    "url": {
      "type": "data.input",
      "path": "imagepath"
    }
  }
  ```

  {% endcut %}

- [view.markdown](../reference/view.markdown.md) — блок для отображения текста в разметке Markdown.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.markdown",
    "label": "Product title:",
    "content": {
      "type": "data.input",
      "path": "title"
    }
  }
  ```

  {% endcut %}

- [view.alert](../reference/view.alert.md) — компонент создает цветной блок для выделения важной информации. Внутрь можно поместить не только обычный текст, но и другие визуальные компоненты.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.alert",
    "theme": "info",
    "label": "Search query",
    "content": {
      "type": "view.text",
      "content": {
        "type": "data.input",
        "path": "query"
      }
    }
  }
  ```

  {% endcut %}

- [view.action-button](../reference/view.action-button.md) — кнопка, вызывающая действие. При нажатии кнопки вызовется действие, указанное в свойстве `action`.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.action-button",
    "label": "Search query in Google",
    "action": {
      "type": "action.open-link",
      "payload": {
        "type": "data.input",
        "path": "search_url"
      }
    }
  }
  ```

  {% endcut %}

- [view.divider](../reference/view.divider.md) — горизонтальный разделитель. В центре разделителя можно разместить вспомогательные элементы: всплывающую подсказку (`hint`) и надпись (`label`).

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.divider"
  }
  ```

  {% endcut %}

- [field.radio-group](../reference/field.radio-group.md) — компонент, позволяющий выбрать одно из нескольких значений. Оформляется в виде группы переключателей (кружочков), располагающихся вертикально. Минимальное количество кнопок — одна. Тип возвращаемых данных — любой.

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "Choose relevance class",
    "options": [
      {
        "label": "Relevant",
        "value": "relevant"
      },
      {
        "label": "Irrelevant",
        "value": "irrelevant"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "validation": {
      "type": "condition.required"
    }
  }
  ```

  {% endcut %}

- [condition.required](../reference/condition.required.md) — проверяет, что выбран хотя бы один вариант.

  {% cut "Показать код" %}

  ```json
  {
    "type": "condition.required"
  }
  ```

  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания.

  {% cut "Показать код" %}

  ```json
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "scroll",
      "taskWidth": 600
    }
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

Если вам не подходит этот шаблон, посмотрите другие примеры в этом разделе.

## Добавить поле для ввода ответа {#add-text-area}

Если вам нужны комментарии от исполнителя, то добавьте поле для ввода текста с помощью [field.textarea](../reference/field.textarea.md).

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/Ryo07JaT3UYB9k)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)