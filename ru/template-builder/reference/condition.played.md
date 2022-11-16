# condition.played

{% include [deprecate](../../_includes/deprecate.md) %}

Проверяет начало воспроизведения. Валидация пройдет, если воспроизведение начато. Для воспроизведения медиа с проверкой `condition.played` можно использовать [view.audio](view.audio.md) и [view.video](view.video.md). `condition.played` работает только в свойстве `validation` плеера.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/q-xebK5N3TskNA)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "condition.played" | Задает тип компонента. ||
|| `hint` | _string_ | Сообщение об ошибке валидации, которое увидит исполнитель ||
|#
