# Sentiment analysis & Content moderation

For this type of project, you can use the **Sentiment analysis & Content moderation** preset. 

This preset helps you check text content against a pre-determined set of guidelines and rules.

Take a look at the example: the labeling interface includes a text and radio buttons. When the **Yes, there are** options is selected, an additional question with checkboxes appears. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/d79jOnuS3cQ5xW)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Block for displaying data in a list.

- [view.text](../reference/view.text.md): The text that you want to check.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "content": {
      "type": "data.input",
      "path": "comment"
    }
  }
  ```

  {% endcut %}

- [view.alert](../reference/view.alert.md): The color block to highlight important information to enhance Toloker's experience. In this example, the text content is highlighted with a blue border.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": {
        "type": "data.input",
        "path": "comment"
      }
    }
  }
  ```

  {% endcut %}

- [view.markdown](../reference/view.markdown.md): Block for displaying text in Markdown.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.markdown",
    "content": "**Are there any infringements of publication guidelines in the text?**"
  }
  ```

  {% endcut %}

{% note info %}

Note that the `view.markdown` component is resource-intensive and might overload weak Toloker devices. Do not use this component to display plain text.

{% endnote %}

- [field.button-radio-group](../reference/field.button-radio-group.md): Adds radio buttons for selecting an answer option.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "options": [
      {
        "label": "No, there are not",
        "value": "no"
      },
      {
        "label": "Yes, there are",
        "value": "yes"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "is_infringements"
    },
    "validation": {
      "type": "condition.required",
    }
  },
  ```

  {% endcut %}

- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.required",
    "hint": "Choose one of the options"
  }
  ```

  {% endcut %}

- [helper.if](../reference/helper.if.md): The component displays an interface element after a specific response is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "helper.if",
    "condition": {
      "type": "condition.equals",
      "data": {
        "type": "data.output",
        "path": "is_infringements"
      },
      "to": "yes"
    },
    "then": {
      "type": "field.checkbox-group",
      "label": "Which ones?",
      "options": [
        {
          "label": "Advertising or spam",
          "value": "advertising"
        },
        {
          "label": "Nonsense",
          "value": "nonsense"
        },
        {
          "label": "Insult",
          "value": "insult"
        },
        {
          "label": "Violation of the law",
          "value": "law_violation"
        },
        {
          "label": "Profanity",
          "value": "profanity"
        }
      ],
      "data": {
        "type": "data.output",
        "path": ""
      },
      "validation": {
        "type": "condition.required",
        "hint": "Select one or more infringements"
      }
    }
  }
  ```

  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.

  {% cut "Show code" %}

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

- [plugin.hotkeys](../reference/plugin.hotkeys.md): [Keyboard shortcuts](../best-practices/hotkeys.md).

  {% cut "Show code" %}

  ```json
  {
    "1": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "is_infringements"
      },
      "payload": "no"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "is_infringements"
      },
      "payload": "yes"
    },
    "w": {
      "type": "action.toggle",
      "data": {
        "type": "data.output",
        "path": "advertising"
      }
    },
    "a": {
      "type": "action.toggle",
      "data": {
        "type": "data.output",
        "path": "nonsense"
      }
    },
    "s": {
      "type": "action.toggle",
      "data": {
        "type": "data.output",
        "path": "insult"
      }
    },
    "d": {
      "type": "action.toggle",
      "data": {
        "type": "data.output",
        "path": "law_violation"
      }
    },
    "f": {
      "type": "action.toggle",
      "data": {
        "type": "data.output",
        "path": "profanity"
      }
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

If this preset doesn't meet your needs, see other examples in this section.

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Decide whether comments follow the publication guidelines."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/oStyT00s3cQ8D4)

## Add a response field {#add-text-area}

If you want that Tolokers give an extended response, add a text field using the [field.textarea](../reference/field.textarea.md) component.

{% cut "Show code" %}

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/dYOxus1h3cQ8PT)

## Other options for buttons {#mult-ans-options}

Decide whether a Toloker can select only one or multiple answer options:

{% list tabs %}

- Multiple options (checkboxes)

  If there are several possible answers to the question, add checkboxes using the [field.checkbox-group](../reference/field.checkbox-group.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.checkbox-group",
    "options": [
      {
        "label": "Advertising or spam",
        "value": "advertising"
      },
      {
        "label": "Nonsense",
        "value": "nonsense"
      },
      {
        "label": "Insult",
        "value": "insult"
      },
      {
        "label": "Violation of the law",
        "value": "law_violation"
      },
      {
        "label": "Profanity",
        "value": "profanity"
      },
      {
        "label": "None of this",
        "value": "none"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "is_infringements"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Choose one of the options"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/-x9JHPik3cQ8y7)

- One option (radio buttons)

  If  you want that Tolokers select one answer option from the given list of choices, add group of radio buttons using the [field.button-radio-group](../reference/field.button-radio-group.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "options": [
      {
        "label": "Advertising or spam",
        "value": "advertising"
      },
      {
        "label": "Nonsense",
        "value": "nonsense"
      },
      {
        "label": "Insult",
        "value": "insult"
      },
      {
        "label": "Violation of the law",
        "value": "law_violation"
      },
      {
        "label": "Profanity",
        "value": "profanity"
      },
      {
        "label": "None of this",
        "value": "none"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "is_infringements"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Choose one of the options"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/LJnqWagn3cQ8zW)

{% endlist %}

{% include [contact-support](../_includes/contact-support.md) %}