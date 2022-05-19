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

[View example in the sandbox](https://clck.ru/amHA8).

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
