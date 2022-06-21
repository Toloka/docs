# Попарное сравнение видео

Посмотрите пример — он состоит из двух видео и кнопок выбора ответа. В нем уже настроена валидация, горячие клавиши и внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/vSBnRFLf3TXf7r)

{% cut "Из каких компонентов состоит этот пример" %}

- [view.video](../reference/view.video.md) — видеоплеер;

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.video",
    "validation": {
      "type": "condition.played",
      "hint": "Please, watch the video"
    },
    "url": {
      "type": "data.input",
      "path": "video_1"
    }
  }
  ```

  {% endcut %}

- [layout.columns](../reference/layout.columns.md) — размещает видео справа и слева друг от друга;

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
    "label": "Are the videos the same or different?",
    "options": [],
    "validation": {
      "type": "condition.required",
      "hint": "Choose one of the options"
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
    "type": "condition.required",
    "hint": "Choose one of the options"
  }
  ```

  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания;

  {% cut "Показать код" %}

  ```json
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "pager",
      "taskWidth": 1200
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
    "3": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "error"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## Что еще можно настроить {#add-more}

- Добавьте [проверку](../best-practices/conditions.md), что видео просмотрели до конца — замените компонент [condition.played](../reference/condition.played.md) на [condition.played-fully](../reference/condition.played-fully.md).

  {% cut "Показать код" %}

  ```json
  {
    "type": "condition.played-fully",
    "hint": "Please, watch the video"
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/Agy26p4z3TXfRe)

- Чтобы добавить подробное описание к заданию, используйте компонент [view.text](../reference/view.text.md).

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.text",
    "content": "Watch the videos and tell if they are the same."
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/50mce2VJ3TXtHN)

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

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/X_bdCg0m3TXkwV)

Если вам не подходит этот шаблон, посмотрите другие примеры в этом разделе.

## Добавить оформление {#add-color}

Также вы можете цветом оформлять разные типы данных с помощью [view.alert](../reference/view.alert.md), чтобы исполнитель легче в них ориентировался. В этом примере исходный текст выделен синей рамкой, а кнопки — желтой.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "Watch the videos and tell if they are the same."
    }
  },
  {
    "type": "view.alert",
    "theme": "warning",
    "content": {
      "type": "field.radio-group",
      "label": "Are the videos the same or different?",
      "options": [],
      "validation": {
        "type": "condition.required",
        "hint": "Choose one of the options"
      },
      "data": {
        "type": "data.output",
        "path": "result"
      }
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/Wpdfy4mY3TXtue)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)