# Попарное сравнение текста

Пресет **Сопоставление товаров** позволяет сравнить два названия и определить, они относятся к разным товарам или одинаковым.

Посмотрите пример — он состоит из двух текстов и кнопок выбора ответа. В нем уже настроена валидация, горячие клавиши и внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/Sf4lo2yk3TaD9n)

{% cut "Из каких компонентов состоит этот пример" %}

- [view.text](../reference/view.text.md) — тексты, которые нужно сравнить;

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.text",
    "content": {
      "type": "data.input",
      "path": "text_1"
    }
  }
  ```

  {% endcut %}

- [layout.columns](../reference/layout.columns.md) — размещает тексты справа и слева друг от друга;

  {% cut "Показать код" %}

  ```json
  {
    "type": "layout.columns",
    "items": []
  }
  ```

  {% endcut %}

- [field.radio-group](../reference/field.radio-group.md) — кнопки вариантов ответа;

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "Are the product names the same or different?",
    "options": [],
    "validation": {
      "type": "condition.required"
    },
    "data": {
      "type": "data.output",
      "path": "result"
    }
  }
  ```

  {% endcut %}

- [condition.required](../reference/condition.required.md) — проверяет, что выбран хотя бы один вариант;

  {% cut "Показать код" %}

  ```json
  {
    "type": "condition.required"
  }
  ```

  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания;

  {% cut "Показать код" %}

  ```json
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "scroll",
      "taskWidth": 800
    }
  }
  ```

  {% endcut %}

- [plugin.hotkeys](../reference/plugin.hotkeys.md) — [горячие клавиши](../best-practices/hotkeys.md).

  {% cut "Показать код" %}

  ```json
  {
    "1": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "equal"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "different"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

## Что еще можно настроить {#add-more}

- Чтобы добавить подробное описание к заданию, используйте компонент [view.text](../reference/view.text.md).

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.text",
    "content": "Look at the texts and tell if they are the same or different."
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/pm2SGLdb3TaFW6)

- Чтобы исполнитель мог оставить комментарий к заданию или своему ответу, добавьте поле для ввода текста [field.textarea](../reference/field.textarea.md).

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

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/PDf1QLoJ3TaHDy)

Если вам не подходит этот пресет, посмотрите другие примеры в этом разделе.

## Добавить оформление {#add-color}

Также вы можете цветом оформлять разные типы данных с помощью [view.alert](../reference/view.alert.md), чтобы исполнитель легче в них ориентировался. В этом примере исходный текст выделен синей рамкой, а кнопки — желтой.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "Look at the texts and tell if they are the same or different."
    }
  },
  {
    "type": "view.alert",
    "theme": "warning",
    "content": {
      "type": "field.radio-group",
      "label": "Are the product names the same or different?",
      "options": [],
      "validation": {
        "type": "condition.required"
      },
      "data": {
        "type": "data.output",
        "path": "result"
      }
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/XKSNJHhg3TaGY3)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)