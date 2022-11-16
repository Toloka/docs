# field.audio

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент для записи аудио. Работает в приложении [Толока для мобильных](https://toloka.ai/tolokers/docs/mobile/?lang=ru). В браузере открывает окно для загрузки аудиофайла.

[![](../_images/buttons/view-example.svg)](https://clck.ru/Sbxas)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.audio" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `multiple` | _boolean_ | Определяет, разрешено ли записывать (или загружать) несколько аудио:

- `false` (по умолчанию) — запрещено;
- `true` — разрешено. ||
  || `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
  |#
