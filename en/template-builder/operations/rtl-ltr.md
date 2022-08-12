# Writing direction settings

To set the writing direction for content in blocks, use the `rtl` setting.

```json
{
  "type": "view.text",
  "content": "котики",
  "rtl": {
    "mode": "ltr"
  }
}
```

The direction of writing is set in the `mode` property:

- `ltr` — left to right.

- `rtl` — right to left.


The setting is available in the following blocks: `view.text`, `field.button-radio-group`, `field.text`, and `field.textarea`.

[![image](../_images/buttons/view-example.svg)](https://clck.ru/amHA8)

{% include [contact-support](../_includes/contact-support.md) %}