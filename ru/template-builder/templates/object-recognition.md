# Распознавание объектов и выделение областей

Для такого проекта в Толоке есть пресет **Распознавание объектов и выделение областей**.

Пресет позволяет выделять объекты на изображениях с целью тренировки компьютерного зрения для их обнаружения.

Посмотрите пример — интерфейс разметки включает изображение с ограничивающими рамками, полигонами или ключевыми точками. В нем уже настроена валидация, горячие клавиши и внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/Bv2ocvkf3Vbvhr)

{% cut "Из каких компонентов состоит этот пример" %}

- [field.image-annotation](../reference/field.image-annotation.md) — позволяет выделять области точками, прямоугольниками и полигонами (многоугольниками).

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.image-annotation",
    "image": {
      "type": "data.input",
      "path": "image"
    },
    "fullHeight": true,
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Please select an area"
    }
  }
  ```
  {% endcut %}

- [condition.required](../reference/condition.required.md) — проверяет, что выбрана хотя бы одна область.

  {% cut "Показать код" %}

  ```json
  {
    "type": "condition.required",
    "hint": "Please select an area"
  }
  ```

  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания.

  {% cut "Показать код" %}

  ```json
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "pager"
    }
  }  
  ```

  {% endcut %}
  
- [plugin.field.image-annotation.hotkeys](../reference/plugin.field.image-annotation.hotkeys.md) — позволяет задавать горячие клавиши для выбора типов областей, выбора режимов разметки и подтверждения или отмены создания области.

  {% cut "Показать код" %}

  ```json
  {
    "type": "plugin.field.image-annotation.hotkeys",
    "labels": [
      "1",
      "2",
      "3",
      "4",
      "5"
    ],
    "modes": {
      "select": "q",
      "point": "w",
      "rectangle": "e",
      "polygon": "r"
    },
    "confirm": "a",
    "cancel": "s"
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

Если вам не подходит этот пресет, посмотрите другие примеры в этом разделе.

## Добавить описание {#add-description}

Чтобы добавить подробное описание к заданию, используйте свойство `label` компонента [field.image-annotation](../reference/field.image-annotation.md).

{% cut "Показать код" %}

```json
{
  "type": "field.image-annotation",
  "image": {
    "type": "data.input",
    "path": "image"
  },
  "fullHeight": true,
  "label": "Look at the picture and outine the road signs",
  "data": {
    "type": "data.output",
    "path": "result"
  },
  "validation": {
    "type": "condition.required",
    "hint": "Please select an area"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/hrSYz9hX3VorDF)

## Добавить поле для ввода ответа {#add-text-area}

Если вам нужны комментарии от исполнителя, то добавьте поле для ввода текста с помощью компонента [field.textarea](../reference/field.textarea.md). Вы можете разместить его в компоненте [view.list](../reference/view.list.md) вместе с `field.image-annotation`.

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/izf2rY-d3VoZgc)

## Добавить оформление {#add-layout}

Чтобы исполнитель легче ориентировался в задании, вы можете оформлять цветом разные типы данных с помощью компонента [view.alert](../reference/view.alert.md). Вы можете разместить его в компоненте [view.list](../reference/view.list.md) вместе с `field.image-annotation`.

В этом примере текст выделен желтой рамкой.

{% cut "Показать код" %}

```json
{
  "type": "view.alert",
  "theme": "warning",
  "content": {
    "type": "view.text",
    "content": "Look at the picture and outline the road signs"
  }
}
```

{% endcut %}  

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/eLCcS7Tz3VvzPT)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)