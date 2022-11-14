# action.open-close

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент меняет режим отображения у другого компонента — открывает или закрывает его. То, что происходит с этим компонентом, зависит от типа компонента:

- [view.image](view.image.md) — разворачивает картинку на весь экран.
- [view.collapse](view.collapse.md) — показывает или скрывает контент под катом.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/IgNgEoHR3YCrj7)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "action.open-close" | Задает тип компонента. ||
|| `view` | _ref_ | Указатель на компонент, с которым надо выполнить действие. ||
|#
