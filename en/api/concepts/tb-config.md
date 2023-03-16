# Configuration for Template Builder

If, when creating a project, you specified the Editor type — Template Builder (`"type": "tb"`) in the Task Interface parameters (`view_spec`), then specify the configuration for Template Builder in serialized JSON format in the `config` parameter.

## Configuration example

{% note alert %}

Be sure to serialize the JSON code before passing it as the `config` parameter value.

{% endnote %}

**Example of serialized JSON code**

```json
"config": "{\"view\": {\"type\": \"view.list\", \"items\": [{\"type\": \"view.image\", \"ratio\": [1, 1], \"rotatable\": true, \"url\": {\"type\": \"data.input\", \"path\": \"image\"}}, {\"type\": \"field.button-radio-group\", \"label\": \"What type of shoes do you see?\", \"options\": [{\"label\": \"Boots\", \"value\": \"boots\" }, {\"label\": \"Sneakers\", \"value\": \"sneakers\"}, {\"label\": \"Other\", \"value\": \"other\"}], \"validation\": {\"type\": \"condition.required\", \"hint\": \"choose one of the options\"}, \"data\": {\"type\": \"data.output\", \"path\": \"result\"}}]}, \"plugins\": [{\"type\": \"plugin.toloka\", \"layout\": {\"kind\": \"scroll\", \"taskWidth\": 500}}, {\"1\": {\"type\": \"action.set\", \"data\": {\"type\": \"data.output\", \"path\": \"result\"}, \"payload\": \"boots\"}, \"2\": {\"type\": \"action.set\", \"data\": {\"type\": \"data.output\", \"path\": \"result\"}, \"payload\": \"sneakers\"}, \"3\": {\"type\": \"action.set\", \"data\": {\"type\": \"data.output\", \"path\": \"result\"}, \"payload\": \"other\"}, \"type\": \"plugin.hotkeys\"}]}"
```

{% cut "JSON code from the example above before serialization" %}

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

{% include [contact-support](../../guide/_includes/contact-support.md) %}