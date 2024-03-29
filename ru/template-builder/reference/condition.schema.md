# condition.schema

{% include [deprecate](../../_includes/deprecate.md) %}

Позволяет валидировать данные с помощью [JSON Schema](https://json-schema.org/learn/getting-started-step-by-step.html). Это специальный формат, чтобы описывать данные в формате JSON.

Например, вы можете описать тип данных, минимальное и максимальное значение, а также указать, что все значения должны быть уникальными.

Этот компонент пригодится в следующих случаях:

- если [доступных компонентов](index.md) вам недостаточно, чтобы настроить валидацию.
- если у вас уже есть готовая конфигурация JSON Schema для проверки и вы хотите использовать ее.

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "condition.schema" | Задает тип компонента. ||
|| `data` | _any_ | Данные, которые надо проверить. ||
|| `hint` | _string_ | Сообщение об ошибке валидации, которое увидит исполнитель ||
|| `schema` | _JSON Schema draft 7_ | Схема, по которой будут валидироваться данные. ||
|#
