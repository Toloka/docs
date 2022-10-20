# Добавление заданий в пул

Чтобы добавить задания в пул:

1. [Разместите файлы для заданий](cloud-storage.md).

1. [Создайте файл с заданиями](pool_csv.md).

1. [Загрузите задания в пул](task_upload.md).

    {% if locale == "ru-ru" %}

    Если не любите читать, посмотрите следующее видео: @[YouTube](https://www.youtube.com/embed/eHCHkepn-Pc?rel=0)

    {% endif %}

    {% note alert "Ограничение" %}

    Можно добавить не более одного миллиона заданий в пул. Если вам надо загрузить больше заданий, создайте новый пул.

    {% endnote %}

1. Если вы еще не разметили [контрольные](../../glossary.md#control-task) и [обучающие](../../glossary.md#training-task) задания в файле, [разметьте задания в интерфейсе](task_markup.md).

    {% note info %}

    Если вы создали проект в [песочнице](../../glossary.md#sandbox), то учтите, что при переносе проекта в [основную версию Толоки]({{ production-version }}) задания, в том числе размеченные, не переносятся.

    {% endnote %}

## Что дальше {#what_next}

- [Добавьте обучающий пул](train.md).

- {% if locale == "en-com" %}[Пополните счет](refill.md){% endif %}{% if locale == "ru-ru" %}Пополните счет:

    - [Инструкция для резидентов РФ](refill-russia.md).
    - [Инструкция для нерезидентов](refill.md).

    {% endif %}

- [Запустите пул](pool-run-and-stop.md).

{% include [contact-support](../_includes/contact-support-help.md) %}