# Попарное сравнение аудио

Посмотрите пример — он состоит из двух аудио и кнопок выбора ответа. В нем уже настроена валидация, горячие клавиши и внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/8yWU6Tq-3TYPx8)

{% cut "Из каких компонентов состоит этот пример" %}

- [view.audio](../reference/view.audio.md) — аудиоплеер;

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.audio",
    "url": {
      "type": "data.input",
      "path": "url_1"
    },
    "label": "Audio 1",
      "validation": {
      "type": "condition.played",
      "hint": "Listen to the audio recording"
    }
  }
  ```

  {% endcut %}

- [layout.columns](../reference/layout.columns.md) — размещает аудиодорожки справа и слева друг от друга;

  {% cut "Показать код" %}

  ```json
  {
    "type": "layout.columns",
    "items": []
  }
  ```

  {% endcut %}

- [condition.played](../reference/condition.played.md) — проверяет, что исполнитель начал слушать аудио;

  {% cut "Показать код" %}

  ```json
  {
    "type": "condition.played",
    "hint": "Listen to the audio recording"
  }
  ```

  {% endcut %}

- [field.button-radio-group](../reference/field.button-radio-group.md) — кнопки вариантов ответа;

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.button-radio-group",
    "label": "Whose voice sounds more natural?",
    "options": [],
    "validation": {
      "type": "condition.required",
      "hint": "Choose an answer."
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
    "hint": "Choose an answer."
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
      "payload": "audio_1"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "audio_2"
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

- Добавьте [проверку](../best-practices/conditions.md), что аудио прослушали до конца — замените компонент [condition.played](../reference/condition.played.md) на [condition.played-fully](../reference/condition.played-fully.md).

  {% cut "Показать код" %}

  ```json
  {
    "type": "condition.played-fully",
    "hint": "Listen to the audio recording"
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/Op9Pu3r_3TYSNY)

- Пригодится для коротких аудио — поставьте их на повтор, добавив в свойства компонента [view.audio](../reference/view.audio.md) `loop: true`.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.audio",
    "url": {
      "type": "data.input",
      "path": "url_1"
    },
    "label": "Audio 1",
    "loop": true,
    "validation": {
      "type": "condition.played",
      "hint": "Listen to the audio recording"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/cHq9Xtli3TYTic)

- Добавьте [горячие клавиши](../best-practices/hotkeys.md) с помощью плагина [plugin.hotkeys](../reference/plugin.hotkeys.md) для воспроизведения или остановки аудиозаписи.

  {% cut "Показать код" %}

  ```json
  {
    "q": {
      "type": "action.play-pause",
      "view": {
        "$ref": "view.items.0.items.0"
      }
    },
    "w": {
      "type": "action.play-pause",
      "view": {
        "$ref": "view.items.0.items.1"
      }
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/cQixkxxh3TYX5u)

Если вам не подходит этот шаблон, посмотрите другие примеры в этом разделе.

## Добавить поле для ввода ответа {#add-text-area}

Если вам нужны комментарии от исполнителя, то добавьте поле для ввода текста с помощью [field.textarea](../reference/field.textarea.md). В этом примере настроена дополнительная валидация, которая обязывает написать текст, если выбрано одно из двух аудио.

  {% cut "Показать код" %}

  ```json
  {
    "type": "field.textarea",
    "label": "Please explain why you chose it.",
    "data": {
      "type": "data.output",
      "path": "text"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Enter text."
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/aBZZXCvm3TYZCw)

## Расположить друг под другом {#top-bottom}

Аудио можно расположить друг под другом. Этот интерфейс лучше подойдет для сравнения более двух аудиозаписей.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/eqx3jrHj3TYaTy)

## Добавить исходный текст {#add-original-text}

Вы можете добавить поле с исходным текстом с помощью компонента [view.text](../reference/view.text.md). Например, если вы хотите выяснить, какая из аудиозаписей лучше подходит под описание.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.text",
    "content": "A joyful, inspiring melody.",
    "label": "Overview"
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/m1b1YPvB3TYbYi)

## Добавить оформление {#add-color}

Также вы можете цветом оформлять разные типы данных с помощью [view.alert](../reference/view.alert.md), чтобы исполнитель легче в них ориентировался. В этом примере исходный текст выделен синей рамкой, а кнопки — желтой.

  {% cut "Показать код" %}

  ```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "A joyful, inspiring melody."
    }
  },
  {
    "type": "view.alert",
    "theme": "warning",
    "content": {
      "type": "field.button-radio-group",
      "label": "Which audio recording best fits the description?",
      "options": [],
      "validation": {
        "type": "condition.required",
        "hint": "Choose an answer."
      },
      "data": {
        "type": "data.output",
        "path": "result"
      }
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/PinrwG2E3TYcTx)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)