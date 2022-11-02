# view.audio

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент воспроизводит аудио.

Поддержка форматов зависит от браузера, ОС и устройства исполнителя. Рекомендуем использовать формат MP3.

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "view.audio" | Задает тип компонента. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `loop` | _boolean_ | Автоматически повторять аудио. ||
|| `url`<span style="color: red">\*</span> | _string_ | Ссылка на аудио. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
