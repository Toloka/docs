# condition.played-fully

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент проверяет окончание воспроизведения. Валидация пройдет, если воспроизведение закончено. Для воспроизведения медиа с проверкой `condition.played-fully` можно использовать [view.audio](view.audio.md) и [view.video](view.video.md). `condition.played-fully` работает только в свойстве `validation` плеера.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/AlVpjz8V3tzBiR)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "condition.played-fully" | Задает тип компонента. ||
|| `hint` | _string_ | Сообщение об ошибке валидации, которое увидит исполнитель ||
|#
