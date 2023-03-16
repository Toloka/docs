# view.alert

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент создает цветной блок для выделения важной информации.

Внутрь можно поместить не только обычный текст, но и другие визуальные компоненты.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/nKo0PzBo3tyxxn)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "view.alert" | Задает тип компонента. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `content` | _view_ | Содержимое блока с важной информацией. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `theme` | _string_ | Определяет расцветку блока:

- `info` (по умолчанию) — голубая;
- `success` — зеленая;
- `warning` — желтая;
- `danger` — красная.
  ||
  || `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
  |#
