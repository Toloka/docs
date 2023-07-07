# Searching for products in an online store

For this type of project, you can use the **Searching for products in an online store** preset.

You can use this preset to make Tolokers find products in online stores.

Take a look at the example: the labeling interface includes text data, a text input area, a button containing a website link, and a checkbox Toloker can select if the product isn't on sale in the online store. Note that validation, keyboard shortcuts and task layout are already configured in this Template Builder sample code.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/dZpF0xTT4K2qE7)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.link](../reference/view.link.md): A link to the site.

  {% cut "Show code" %}
  ```json
  {
    "type": "view.link",
    "url": {
      "type": "data.input",
      "path": "url"
    },
    "content": {
      "type": "data.input",
      "path": "name"
    }
  }
  ```
  {% endcut %}

- [view.action-button](../reference/view.action-button.md): Adds a button that calls an action.

  In this example, clicking the button calls [action.open-link](../reference/action.open-link.md) component which sends the Toloker to the site where he can search for the product sited in the link.

  {% cut "Show code" %}
  ```json
  {
    "type": "view.action-button",
    "validation": {
      "type": "condition.link-opened",
      "url": {
        "type": "data.input",
        "path": "shop"
      },
      "hint": "Follow the link"
    },
    "action": {
      "type": "action.open-link",
      "payload": {
        "type": "data.input",
        "path": "shop"
      }
    },
    "label": "Go to the site"
  }
  ```
  {% endcut %}

- [field.text](../reference/field.text.md): Adds a field for entering a short text. In this example, Toloker needs to enter a link to the product's page in the online store. If Toloker doesn't find the product, he chooses **The store doesn't sell the product** checkbox and the text field disappears.

  {% cut "Show code" %}
  ```json
  {
    "type": "helper.if",
    "condition": {
      "type": "condition.equals",
      "data": {
        "type": "data.output",
        "path": "not_available"
      },
      "to": false
    },
    "then": {
      "type": "view.list",
      "items": [
        {
          "type": "field.text",
          "label": "Product page",
          "data": {
            "type": "data.output",
            "path": "link"
          },
          "placeholder": "https://",
          "validation": {
            "type": "condition.required"
          }
        }
      ]
    }
  }
  ```
  {% endcut %}

- [field.checkbox](../reference/field.checkbox.md): Adds a checkbox.

  In this example, Toloker selects **The store doesn't sell the product** checkbox if he cannot find the product in the online store.

  {% cut "Show code" %}
  ```json
  {
    "type": "field.checkbox",
    "preserveFalse": true,
    "label": "The store doesn't sell the product",
    "data": {
      "type": "data.output",
      "path": "not_available"
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

- [plugin.hotkeys](../reference/plugin.hotkeys.md): Customizes the [keyboard shortcuts](../best-practices/hotkeys.md).

  {% cut "Show code" %}
  ```json
  {
    "type": "plugin.hotkeys",
    "w": {
      "type": "action.open-link",
      "payload": {
        "type": "data.input",
        "path": "shop"
      }
    }
  },
  {
    "type": "plugin.hotkeys",
    "q": {
      "type": "action.toggle",
      "data": {
        "type": "data.output",
        "path": "not_available"
      }
    }
  }
  ```
  {% endcut %}

{% endcut %}

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Find a product in an online store and enter the link to the page with this product."
}
```
{% endcut %}


[![](../_images/buttons/view-example.svg)](https://ya.cc/t/HOtz4PAW4K5HwT)

If you need to display formatted text, use the [view.markdown](../reference/view.markdown.md) component. Note that this setting is resource-intensive and might overload Tolokers' devices that aren't powerful enough.

{% cut "Show code" %}

```json
{
  "type": "view.markdown",
  "content": "**Find a product in an online store and enter the link to the page with this product.**"
}
```
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/3V4Hyqjg4KHqaN)


## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the other components. In this example, the description is highlighted with a blue border.

{% cut "Show code" %}

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
    "type": "view.text",
    "content": "Find a product in an online store and enter the link to the page with this product."
  }
}
```
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/36mkWpAN4K5JhT)

## Add an image {#add-image}

You can add an image that matches the text data to your task using [view.image](../reference/view.image.md).

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/4IMgRws84K4uTX)

## Add a field for comments {#add-text-area}

To ask Tolokers to clarify their choice if they selected the **The store doesn't sell the product** checkbox add a text field using [field.textarea](../reference/field.textarea.md).

{% cut "Show code" %}

```json
{
  "type": "field.textarea",
  "label": "Leave your comment",
  "hint": "There is no such product in a store, the product doesn't exist, the product name is incorrect etc.",
  "placeholder": "Enter text",
  "data": {
    "type": "data.output",
    "path": "comment"
  }
}
```
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/ecWnPMnb4K6AXf)

{% include [contact-support](../_includes/contact-support.md) %}