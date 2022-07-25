# Product search relevance

For this type of project, you can use the **Product search relevance** preset.

This preset helps you improve ecommerce search page results by rating how relevant products are to specific search queries.

Take a look at the example: the labeling interface includes an image, a box for the search query, and radio buttons for evaluating relevance. Note that validation and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/ajV9o-mE3UGqbd)

{% cut "Components used in the example" %}

- [layout.sidebar](../reference/layout.sidebar.md): Lets you place the main content block and an adjacent panel with controls on a page.

  {% cut "Show code" %}

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

- [view.image](../reference/view.image.md): Displays an image.

  {% cut "Show code" %}

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

- [view.markdown](../reference/view.markdown.md): A block for displaying text in Markdown.

  {% cut "Show code" %}

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

- [view.alert](../reference/view.alert.md): The component creates a color block to highlight important information. You can use both plain text and other visual components inside it.

  {% cut "Show code" %}

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

- [view.action-button](../reference/view.action-button.md): A button that calls an action. When clicking the button, an action specified in the `action` property is called.

  {% cut "Show code" %}

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

- [view.divider](../reference/view.divider.md): A horizontal delimiter. You can place extra elements in the center of the delimiter, like a popup `hint` and `label`.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.divider"
  }
  ```

  {% endcut %}

- [field.radio-group](../reference/field.radio-group.md): A component for selecting one value out of several options. It is designed as a group of circles arranged vertically. The minimum number of buttons is one. Any type of data can be returned.

  {% cut "Show code" %}

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

- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.required"
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
      "taskWidth": 600
    }
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

If this preset doesn't meet your needs, see other examples in this section.

## Add a response field {#add-text-area}

If you need comments from the Toloker, add a text field using [field.textarea](../reference/field.textarea.md). In this example, additional validation is set up that requires you to enter text if one of two audio tracks is selected.

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/Ryo07JaT3UYB9k)

{% include [contact-support](../_includes/contact-support.md) %}