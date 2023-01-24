# Настройка направления написания

{% include [deprecate](../../_includes/deprecate.md) %}

Чтобы задать направление написания контента в блоках, используйте настройку `rtl`.

```json
{
  "type": "view.text",
  "content": "котики",
  "rtl": {
    "mode": "ltr"
  }
}
```

Направление написания задается в свойстве `mode`:

- `ltr` — слева направо;

- `rtl` — справa налево.

Настройка доступна в блоках `view.text`, `field.button-radio-group`, `field.text` и `field.textarea`.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/sUglWRS43tvxMt)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)