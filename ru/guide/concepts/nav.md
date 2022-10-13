# Навыки исполнителей

Навык — произвольная характеристика исполнителя. Описывается числом от 0 до 100. Например, в навык можно записывать процент правильных ответов исполнителя.

Помимо навыков, создаваемых заказчиком, в Толоке есть [глобальные навыки](nav-cross-project.md).

## Как пользоваться навыками {#what-next}

1. [Создайте навык](nav-create.md). Навыки вы создаете сами.

1. [Назначьте навык](nav-assign.md) вручную или автоматически.

1. [Используйте навык](nav-use.md), например для отбора исполнителей, управления перекрытием или ценой.

При необходимости вы можете:

- [изменить](nav-edit.md) значение навыка вручную;
- [удалить](nav-delete.md) навык для конкретного исполнителя;
- [просмотреть историю](nav-history.md) изменений навыка.

{% if locale == "ru-ru" %}

## См. также {#see-also}

Узнайте больше об использовании навыков в [блоге Толоки]({{ toloka-blog-skill }}).

{% endif %}
## Решение проблем {#troubleshooting}

{% cut "Нужно ли создавать навык для каждого пула?" %}

Лучше использовать один [навык](../../glossary.md#skill) в проекте. Можно выбрать способ подсчета навыка:

- Подсчет навыка для каждого пула отдельно. Текущее значение навыка — это значение навыка в пуле, который выполнялся последним. Такой вариант удобен, если:

    - Пулы предназначены для разных групп исполнителей (например, настроены фильтры по городам, странам).

    - Пулы запускаются последовательно, и вы не хотите учитывать качество ответов в предыдущих пулах при подсчете навыка в выполняемом пуле.

    Этот способ подсчета действует по умолчанию при добавлении блока контроля качества в пул. Для блока по контрольным заданиям оставьте пустым поле **Учитывать последних ответов на контрольные и обучающие задания**.

- Подсчет навыка по всем выполненным заданиям в проекте. Такой вариант удобен, если пулы небольшие и вам не нужно рассчитывать навык для каждого пула.

    Этот способ подсчета доступен только для навыков по контрольным заданиям. Чтобы использовать его, заполните поле **Учитывать последних ответов на контрольные и обучающие задания** в блоках контроля качества в пулах.

{% endcut %}

{% cut "Можно ли использовать навык не только в пуле или в одном проекте, но и в разных проектах?" %}

Да, конечно, один и тот же навык можно назначать и использовать на различных проектах. Но чаще всего один навык используется в рамках одного проекта. Если исполнитель хорошо выполняет одно задание, это не значит, что он так же успешно справится с другим. Кроме того, используя фильтры по давно настроенным навыкам, вы ограничиваете количество доступных исполнителей.

{% endcut %}

{% cut "Обучение прошли более 500 исполнителей, но в тренировочном навыке отображается только 30" %}

В пуле отображается общее число исполнителей, которые выполнили там хотя бы одну страницу заданий. Тренировочный навык может со временем теряться из-за настройки повторного прохождения. Она позволяет заново выполнить тренировку по истечении указанного срока, если исполнитель так и не приступил к заданиям в привязанных пулах или сделал слишком большой перерыв в выполнении заданий (например, из-за [блокировки](../../glossary.md#banned-worker)). Поэтому в тренировочном навыке отображаются те исполнители, которые либо недавно завершили обучение, либо регулярно выполняют ваше задание и не дают навыку исчезнуть.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}