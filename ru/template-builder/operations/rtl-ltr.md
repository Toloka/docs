# Настройка направления написания

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

[Посмотреть пример в песочнице](https://clck.ru/g54Xz).

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
