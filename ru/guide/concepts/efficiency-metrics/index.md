# Метрики эффективности

{% include [deprecate](../../../_includes/deprecate.md) %}

{% note warning "Важно" %}

Метрики эффективности доступны ограниченному числу пользователей. Если вы хотите получить доступ, заполните [форму](https://toloka.ai/request-early-access/).

{% endnote %}

В Толоке есть набор показателей, по которым вы можете оценить, правильно ли настроен ваш проект. Вы сможете быстро принять решение об изменениях на основе метрик эффективности. Например, вы узнаете, какие настройки пула нужно изменить, чтобы повысить качество и скорость разметки.

Эта информация содержится на вкладке {% if locale == "ru-ru" %}**Эффективность**{% endif %}{% if locale == "en-com" %}**Efficiency**{% endif %} на странице пула:

- [{% if locale == "ru-ru" %}Блокировки{% endif %}{% if locale == "en-com" %}Bans{% endif %}](ban-rate.md)
- [{% if locale == "ru-ru" %}Выполнение заданий{% endif %}{% if locale == "en-com" %}Submission rate{% endif %}](submitting-tasks.md)
- [{% if locale == "ru-ru" %}Доступные исполнители{% endif %}{% if locale == "en-com" %}Project availability{% endif %}](available-performers.md)
- [{% if locale == "ru-ru" %}Качество инструкции{% endif %}{% if locale == "en-com" %}Quality of instructions{% endif %}](instruction-quality.md)<!-- - [{% if locale == "ru-ru" %}Качество интерфейса{% endif %}{% if locale == "en-com" %}Quality of interface{% endif %}](interface-quality.md) -->
- [{% if locale == "ru-ru" %}Контрольные задания{% endif %}{% if locale == "en-com" %}Control tasks{% endif %}](control-tasks-share.md)<!-- - [{% if locale == "ru-ru" %}Общение с исполнителями{% endif %}{% if locale == "en-com" %}Communication issues{% endif %}](communication.md) -->
- [{% if locale == "ru-ru" %}Отклоненные задания{% endif %}{% if locale == "en-com" %}Rejected tasks{% endif %}](rejected-tasks.md)
- [{% if locale == "ru-ru" %}Сбалансированность контрольных заданий{% endif %}{% if locale == "en-com" %}Control task balance{% endif %}](control-tasks-balance.md)

## Особенности {#features}

- Метрики эффективности пересчитываются каждые 15 минут.

- Изменения в настройках проектов и пулов не приводят к моментальному изменению показателей.

- Период, за который учитываются данные — последние 2 дня.

{% include [contact-support](../../_includes/contact-support-help.md) %}