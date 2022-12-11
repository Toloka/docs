# Button

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a button in {% if locale == "en-com" %}[Template Builder](../../../template-builder/reference/field.button-radio.md){% endif %}.

{% endnote %}

To add a button to a task, use the `not_var{{button}}` component. Example:

{% if locale == "en-com" %}

```plaintext
{{button label="Click me" href="https://yandex.ru" action=true}}
```

{% endif %}

#### Parameters

#|
||**Parameter**|**Description**|**Required**|**Default value**||
||`label`| Button label | no | empty string||
||`href`| Link that opens when the Toloker clicks the button. The link is opened in a new browser tab. | no | —||
||`action`| Button color:

- `action=true` — Yellow.

- `action=false` — White. | no | `false`||
||`size`| Size of the button (with preserved aspect ratio).

- `"S"` — 24 px high.

- `"M"` — 28 px high.

- `"L"` — 32 px high.

- `"XL"` — 38 px high. | no | `"M"`||
||`class`| CSS class. | no | `".button"`||
|#

{% include [contact-support](../../_includes/contact-support.md) %}