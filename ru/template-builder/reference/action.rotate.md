# action.rotate

{% include [deprecate](../../_includes/deprecate.md) %}

Поворачивает указанный компонент на 90 градусов.

По умолчанию — вправо, но можно указать направление в свойстве `payload`.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/CB77h-lv3tyxhh)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "action.rotate" | Задает тип компонента. ||
|| `payload` | _string_ | Задает направление вращения:

- `right` (по умолчанию) — вправо;
- `left` — влево. ||
  || `view` | _ref_ | Указатель на компонент, с которым надо выполнить действие. ||
  |#
