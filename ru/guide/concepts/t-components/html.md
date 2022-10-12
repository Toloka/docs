# Отформатированный текст в HTML

{% include [toloka-requester-source-html-editor-tb](../../_includes/toloka-requester-source/id-toloka-requester-source/html-editor-tb.md) %}

Чтобы загрузить задание с отформатированным текстом (HTML-тегами и стилями):

1. В описании [входных данных](../incoming.md) добавьте поле с типом `string`. Например:

    ```plaintext
    {
        "html": {
            "type": "string",
            "required": true
        }
    }
    ```

1. В [интерфейсе задания](../spec.md) название поля входных данных заключите в тройные фигурные скобки. Например: `{not_var{{html}}}`.

Перед загрузкой задания проверьте, что в отформатированном тексте все кавычки [экранированы](../pool_csv.md#string).

{% include [contact-support](../../_includes/contact-support-help.md) %}