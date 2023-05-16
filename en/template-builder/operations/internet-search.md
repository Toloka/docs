# Inserting links

In this section, you will learn how to add a link or a search engine query and how to check whether a Toloker has clicked on them. Links can be opened when a certain event occurs. You can also group links together and set shortcuts for them to allow Tolokers to work faster.

## Insert a normal link {#view.link}

If you want to insert a link without additional formatting, use the [view.link](../reference/view.link.md) component. The link is underlined and changes color after clicking on it.

```json
{
  "type": "view.link",
  "content": "Link text",
  "url": "url"
}
```

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/CmLK2rOB3vw46E)

## Create a search query {#helper.search-query}

For some tasks, you may need to create a link that opens the entered query in the search engine you selected. To do this, use the [helper.search-query](../reference/helper.search-query.md) component. You can see the list of available search engines in the `engine` property.

```json
{
  "type": "view.link",
  "content": "Link text",
  "url": {
    "type": "helper.search-query",
    "query": "search query",
    "engine": "google"
  }
}
```

{% note tip %}

If you need to insert links to several search engines with the same query, then you can take out `query` in the input data, and refer to them in the code via `"path": "query"` in order not to duplicate the request.

{% endnote %}

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/Vv1wqNP13vw4gc)

If the search engine you need is not available in the `engine` property, leave this field empty and enter the search query in `query` using the [helper.join](../reference/helper.join.md) component.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/sQLrwr193ttF3h)

## Group links together {#view.link-group}

To group multiple links together, use the [view.link-group](../reference/view.link-group.md) component. Links will be underlined. For emphasis, you can add a border around one of the links and remove the underline. To do this, set the `theme` property to `primary` for this link.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/l6Y5VpjQ3vvKhM)

## Create a button link {#action.open-link}

You can create a link in the form of a button using the [action.open-link](../reference/action.open-link.md) component. The button is added using the [view.action-button](../reference/view.action-button.md) component. In the `payload` property, specify the address or the [helper.search-query](../reference/helper.search-query.md) component with the search query.

```json
{
  "type": "view.action-button",
  "label": "Text on the button",
  "action": {
    "type": "action.open-link",
    "payload": "url"
  }
}
```

{% note tip %}

To make sure the button looks nice and doesn't stretch to the entire screen width, set [view.action-button](../reference/view.action-button.md) as an element of the `items` array for the [view.list](../reference/view.list.md) component.

{% endnote %}

When adding multiple buttons, you can arrange them horizontally (instead of vertically) in the `direction` property.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/hX0vfOLQ3vw5Xd)

To assign a [shortcut](../best-practices/hotkeys.md) to a button, use the [plugin.hotkeys](../reference/plugin.hotkeys.md) component.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/XYwqil9X3xP6Jt)

## Check if the link was clicked on {#condition.link-opened}

To check if the Toloker clicked on the link, use the [condition.link-opened](../reference/condition.link-opened.md) component by specifying it in the `validation` property.

Remember that the condition only works if a Toloker clicks the link in the interface. If the link is opened via the address bar, the condition doesn't work.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/6JZC_mNn3vw6Dp)

## Add keyboard shortcuts {#hotkeys}

You can add keyboard shortcuts for links. Shortcuts allow Tolokers to open links by pressing a keyboard key, which helps them work faster.

To add a shortcut, use the [plugin.hotkeys](../reference/plugin.hotkeys.md) plugin. Select a key and assign it to open the link, using the [action.open-link](../reference/action.open-link.md) component.

```json
{
  "type": "plugin.hotkeys",
  "y": {
    "type": "action.open-link",
    "payload": "url"
  }
}
```

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/LNClzO8H3vw76R)

Learn more about shortcuts in [Configure keyboard shortcuts](../best-practices/hotkeys.md).

## Use event-driven links {#plugin.trigger}

You can set a link to open when a certain event occurs. For example, when a Toloker chooses an option, this can open a specific search query. To do this, use the [plugin.trigger](../reference/plugin.trigger.md) plugin.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ALiH0zIV3ttF8Z)

## Reuse the code {#vars}

Just like any piece of the code, the code for opening the link and its address can be reused using the `{"$ref": "path.to.element"}` structure. This is useful when adding keyboard shortcuts. To avoid duplicating the code for the link display and for [plugin.hotkeys](../reference/plugin.hotkeys.md), just enter the code once in `vars`.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/UwBOfm8d3vw7uu)

Learn more about reusing the code in [Reuse code](../best-practices/reuse.md).

{% include [contact-support](../_includes/contact-support.md) %}