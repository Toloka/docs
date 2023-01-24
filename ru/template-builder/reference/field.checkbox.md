# field.checkbox

{% include [deprecate](../../_includes/deprecate.md) %}

Переключатель в виде галочки.

Если вам нужно добавить группу переключателей, используйте [field.checkbox-group](field.checkbox-group.md).

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/MQjYPS093tz759)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.checkbox" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `disabled` | _boolean_ | Свойство, которое отключает компонент. При `true` компонент будет недоступен. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `preserveFalse` | _boolean_ | Свойство указывающее, надо ли возвращать значения `false` в результатах. По умолчанию, если компонент возвращает `false`, то в выходные данные этот результат не будет добавлен. Чтобы в результаты добавлялись значения `false`, укажите `"preserveFalse": true`. ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|#
