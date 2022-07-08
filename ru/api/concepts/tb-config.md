# Configuration for Template Builder

Если при создании проекта в параметрах Интерфейса задания (`view_spec`) вы указали Тип редактора — Конструктор шаблонов (`"type": "tb"`), то в параметре `config` нужно указать конфиг для конструктора шаблонов в формате сериализованного JSON.

## Configuration example

{% note alert %}

Перед тем, как вы передадите JSON в качестве значения для параметра `config`, его нужно сериализовать.

{% endnote %}

**Пример сериализованного JSON**

```json
"config": "{\"view\": {\"type\": \"view.list\", \"items\": [{\"type\": \"view.image\", \"ratio\": [1, 1], \"rotatable\": true, \"url\": {\"type\": \"data.input\", \"path\": \"image\"}}, {\"type\": \"field.button-radio-group\", \"label\": \"What type of shoes do you see?\", \"options\": [{\"label\": \"Boots\", \"value\": \"boots\" }, {\"label\": \"Sneakers\", \"value\": \"sneakers\"}, {\"label\": \"Other\", \"value\": \"other\"}], \"validation\": {\"type\": \"condition.required\", \"hint\": \"choose one of the options\"}, \"data\": {\"type\": \"data.output\", \"path\": \"result\"}}]}, \"plugins\": [{\"type\": \"plugin.toloka\", \"layout\": {\"kind\": \"scroll\", \"taskWidth\": 500}}, {\"1\": {\"type\": \"action.set\", \"data\": {\"type\": \"data.output\", \"path\": \"result\"}, \"payload\": \"boots\"}, \"2\": {\"type\": \"action.set\", \"data\": {\"type\": \"data.output\", \"path\": \"result\"}, \"payload\": \"sneakers\"}, \"3\": {\"type\": \"action.set\", \"data\": {\"type\": \"data.output\", \"path\": \"result\"}, \"payload\": \"other\"}, \"type\": \"plugin.hotkeys\"}]}"
```

{% cut "JSON из примера выше до сериализации" %}

```json
{
  "view": {
    "type": "view.list",
    "items": [
      {
        "type": "view.image",
        "ratio": [
          1,
          1
        ],
        "rotatable": true,
        "url": {
          "type": "data.input",
          "path": "image"
        }
      },
      {
        "type": "field.button-radio-group",
        "label": "What type of shoes do you see?",
        "options": [
          {
            "label": "Boots",
            "value": "boots"
          },
          {
            "label": "Sneakers",
            "value": "sneakers"
          },
          {
            "label": "Other",
            "value": "other"
          }
        ],
        "validation": {
          "type": "condition.required",
          "hint": "choose one of the options"
        },
        "data": {
          "type": "data.output",
          "path": "result"
        }
      }
    ]
  },
  "plugins": [
    {
      "type": "plugin.toloka",
      "layout": {
        "kind": "scroll",
        "taskWidth": 500
      }
    },
    {
      "1": {
        "type": "action.set",
        "data": {
          "type": "data.output",
          "path": "result"
        },
        "payload": "boots"
      },
      "2": {
        "type": "action.set",
        "data": {
          "type": "data.output",
          "path": "result"
        },
        "payload": "sneakers"
      },
      "3": {
        "type": "action.set",
        "data": {
          "type": "data.output",
          "path": "result"
        },
        "payload": "other"
      },
      "type": "plugin.hotkeys"
    }
  ]
}
```

{% endcut %}