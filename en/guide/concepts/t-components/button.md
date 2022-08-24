# Button

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button in {% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.button-radio){% endif %}.

{% endnote %}


To add a button to a task, use the `{{button}}` component. Example:
 {% if locale == "en-com" %}
```no-highlight
{{button label="Click me" href="https://yandex.ru" action=true}}
```
{% endif %}
#### Parameters


Parameter
 |
Description
 |
Required
 |
Default value

----- | ----- | ----- | -----
``` label ``` | Button label | no | empty string
``` href ``` | Link that opens when the Toloker clicks the button. The link is opened in a new browser tab. | no | —
``` action ``` | Button color:<br/><br/>- `action=true` — Yellow.<br/>    <br/>- `action=false` — White. | no | ``` false ```
``` size ``` | Size of the button (with preserved aspect ratio).<br/>- `"S"` — 24 px high.<br/>    <br/>- `"M"` — 28 px high.<br/>    <br/>- `"L"` — 32 px high.<br/>    <br/>- `"XL"` — 38 px high. | no | ``` "M" ```
``` class ``` | CSS class. | no | ``` ".button" ```

{% include [contact-support](../../_includes/contact-support-help.md) %}