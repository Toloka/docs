# Попарное сравнение изображений

{% include [deprecate](../../_includes/deprecate.md) %}

Для такого проекта в Толоке есть пресет **Сравнение изображений (Side-by-side)**.

Посмотрите пример — он состоит из двух изображений и кнопок выбора ответа. В нем уже настроена валидация, горячие клавиши и внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/25Fr4UGS3ttDEV)

{% cut "Из каких компонентов состоит этот пример" %}

- [view.image](../reference/view.image.md) — изображение;

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.image",
    "url": "https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_dandelion_icon.png"
  }
  ```

  {% endcut %}

- [layout.side-by-side](../reference/layout.side-by-side.md) — размещает изображения справа и слева друг от друга;

  {% cut "Показать код" %}

  ```json
  {
    "type": "layout.side-by-side",
    "items": [],
    "controls": {
      "type": "view.list",
      "items": []
    }
  }
  ```

  {% endcut %}

- [field.radio-group](../reference/field.radio-group.md) — кнопки вариантов ответа;

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "Which icon do you like more?",
    "options": [],
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

- [condition.required](../reference/condition.required.md) — проверяет, что выбран хотя бы один вариант;

  {% cut "Показать код" %}

  ```json
  {
    "type": "condition.required"
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
      "payload": "LEFT"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "RIGHT"
    },
    "3": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "404"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## Что еще можно настроить {#add-more}

- Чтобы добавить подробное описание к заданию, используйте компонент [view.text](../reference/view.text.md).

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.text",
    "content": "Look at the pictures and choose the one you like more."
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/unvVAF-93ttDFe)

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

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/xCvJnVvg3ttDGy)

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
      "content": "Look at the pictures and choose the one you like more."
    }
  },
  {
    "type": "layout.side-by-side",
    "items": [],
    "controls": {
      "type": "view.alert",
      "theme": "warning",
      "content": {
        "type": "field.radio-group",
        "label": "Which icon do you like more?",
        "options": [],
        "data": {
          "type": "data.output",
          "path": "result"
        },
        "validation": {
          "type": "condition.required"
        }
      }
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/UKFF2Obp3ttDJb)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)