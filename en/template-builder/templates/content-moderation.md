# Sentiment analysis & Content moderation

For this type of project, you can use the **Sentiment analysis & Content moderation** preset.

This preset helps you classify text content by specified categories.

Take a look at the example: the labeling interface includes a text and radio buttons. When the **Yes, there are** option is selected, an additional question with checkboxes appears. Note that validation, keyboard shortcuts, and task layout are already configured in this Template Builder sample code.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/JHPP6j1c3ttCmb)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.text](../reference/view.text.md): Adds the text that you want to check.

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

- [view.alert](../reference/view.alert.md): Highlights important information to enhance Toloker's experience. In this example, the text content is highlighted with a blue border.

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

- [view.markdown](../reference/view.markdown.md): Displays a text in Markdown.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.markdown",
    "content": "**Are there any infringements of publication guidelines in the text?**"
  }
  ```

  {% endcut %}

  Note that the `view.markdown` component is resource-intensive and might overload weak Toloker devices. Do not use this component to display plain text. If you need to display text without formatting, use the [view.text](../reference/view.text.md) component.


- [field.radio-group](../reference/field.radio-group.md): Adds radio buttons for selecting an answer option.

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
      "hint": "Choose one of the options"
    }
  }
  ```

  {% endcut %}

- [field.checkbox-group](../reference/field.checkbox-group.md): Adds checkboxes for selecting one or more answer option from the given list of choices.

  {% cut "Show code" %}

  ```json
  {
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

- [helper.if](../reference/helper.if.md): Displays an interface element after a specific response is selected.

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

- [plugin.hotkeys](../reference/plugin.hotkeys.md): Adds [keyboard shortcuts](../best-practices/hotkeys.md).

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

If this template doesn't meet your needs, see other examples in the **Text** section.

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/egPvc7yT3ttCok)

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/pPSkmH_U3ttCqT)

## See also {#see-also}

- [Tutorials — sentiment analysis and content moderation](../../guide/tutorials/content-moderation.md)

{% include [contact-support](../_includes/contact-support.md) %}