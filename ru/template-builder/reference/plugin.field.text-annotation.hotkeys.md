# plugin.field.text-annotation.hotkeys

{% include [deprecate](../../_includes/deprecate.md) %}

Позволяет задавать горячие клавиши для компонента [field.text-annotation](field.text-annotation.md).

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/NqjWqemP3twgex)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "plugin.field.text-annotation.hotkeys" | Задает тип компонента. ||
|| `labels` | _array_ | Горячие клавиши для выбора категорий. Клавиши добавляются на кнопки с категориями в порядке их отображения. ||
|| `labels[]` | _string_ | Горячая клавиша. ||
|| `remove` | _string_ | Используйте свойство, чтобы дать исполнителю возможность отменить выбор всей строки или ее части. Клавиша, которую вы назначите на это свойство, будет отменять выбор. ||
|#
