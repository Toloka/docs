# @yandex-toloka/data.location

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент передает координаты устройства исполнителя.

Чтобы получить координаты, добавьте в свойство нужного компонента тип `@yandex-toloka/data.location`.

Чтобы узнать, соответствуют ли переданные координаты тем, которые задали вы, используйте компонент [condition.distance](condition.distance.md). Добавляйте `@yandex-toloka/data.location` в свойства `to` или `from` в зависимости то того, как вы хотите сравнить координаты.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/1UxiHDb03y5bN3)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "@yandex-toloka/data.location" | Задает тип компонента. ||
|#
