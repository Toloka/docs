# Промежуточная статистика

{% include [deprecate](../../_includes/deprecate.md) %}

Для вашего удобства мы собрали основные показатели на главной странице пула. Если вы хотите узнать подробную статистику, советуем ознакомится с разделом [Статистика по пулу](pool_statistic-pool.md).

#|
||**Поле**|**Описание**||
||{% if locale == "ru-ru" %}**Страниц заданий**{% endif %}{% if locale == "en-com" %}**Task pages**{% endif %} | Число страниц заданий в пуле.||
||{% if locale == "ru-ru" %}**Заданий**{% endif %}{% if locale == "en-com" %}**Tasks**{% endif %} | Число заданий в пуле||
||{% if locale == "ru-ru" %}**Обучающее задание**{% endif %}{% if locale == "en-com" %}**Training task**{% endif %} | Количество обучающих заданий в пуле.||
||{% if locale == "ru-ru" %}**Контрольное задание**{% endif %}{% if locale == "en-com" %}**Control task**{% endif %} | Количество [контрольных заданий](../../glossary.md#control-task) в пуле.||
||{% if locale == "ru-ru" %}**Среднее время выполнения страницы заданий**{% endif %}{% if locale == "en-com" %}**Average assignment submit time**{% endif %} | Среднее время выполнения [страницы заданий в пуле](../../glossary.md#task-suite). Указывается в секундах.

Вычисляется по 1000 последних выполненных страниц заданий.||
||{% if locale == "ru-ru" %}**Приблизительное время завершения**{% endif %}{% if locale == "en-com" %}**Approximate finish time**{% endif %} |

{% include [pool_statistic-pool-expected_execution_time](../_includes/concepts/pool_statistic-pool/id-pool_statistic-pool/expected_execution_time.md) %}

||
||{% if locale == "ru-ru" %}**Страниц заданий**{% endif %}{% if locale == "en-com" %}**Task suites**{% endif %} | Число страниц заданий в пуле.||
||{% if locale == "ru-ru" %}**Заданий**{% endif %}{% if locale == "en-com" %}**Tasks**{% endif %} | Число заданий в пуле.||
||{% if locale == "ru-ru" %}**Обучающих заданий**{% endif %}{% if locale == "en-com" %}**Training tasks**{% endif %} | Количество обучающих заданий в пуле.||
||{% if locale == "ru-ru" %}**Контрольных заданий**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %} | Количество [контрольных заданий](../../glossary.md#control-task) в пуле.||
||{% if locale == "ru-ru" %}**Среднее время выполнения страницы заданий**{% endif %}{% if locale == "en-com" %}**Average assignment submit time**{% endif %} | Среднее время выполнения [страницы заданий в пуле](../../glossary.md#task-suite). Указывается в секундах.

Вычисляется по 1000 последних выполненных страниц заданий.||
||{% if locale == "ru-ru" %}**Приблизительное время завершения**{% endif %}{% if locale == "en-com" %}**Approximate finish time**{% endif %} | {% include [pool_statistic-pool-expected_execution_time](../_includes/concepts/pool_statistic-pool/id-pool_statistic-pool/expected_execution_time.md) %}||
||{% if locale == "ru-ru" %}**Израсходованные средства (+ комиссия)**{% endif %}{% if locale == "en-com" %}**Budget spent (+ fee)**{% endif %} | Сумма потраченных средств в пуле. В скобках указана сумма [комиссии](budget.md).

Обратите внимание, что минимальная комиссия составляет 0,001 $.||
||{% if locale == "ru-ru" %}**Приблизительный бюджет (+ комиссия)**{% endif %}{% if locale == "en-com" %}**Approximate budget (+ fee)**{% endif %} | Сумма израсходованных средств и ожидаемых затрат (если все задания будут выполнены и все ответы будут приняты). В скобках указана сумма [комиссии](../../glossary.md#fee).||
||{% if locale == "ru-ru" %}**Активные исполнители, которым доступны задания**{% endif %}{% if locale == "en-com" %}**Active Tolokers with access to pool**{% endif %} | Число исполнителей, отобранных для пула с помощью [фильтров](filters.md). Учитываются только исполнители, которые просматривали и выполняли задания в Толоке в течение последнего часа.||
||{% if locale == "ru-ru" %}**Заинтересованные исполнители**{% endif %}{% if locale == "en-com" %}**Interested in pool**{% endif %} | Число исполнителей, которые начали выполнять или выполнили хотя бы одну страницу заданий.

Этот показатель включает в себя как заинтересованных, так и взявшихся исполнителей.||
||{% if locale == "ru-ru" %}**Взявшиеся исполнители**{% endif %}{% if locale == "en-com" %}**Submitted in pool**{% endif %} | Количество исполнителей, которые выполнили хотя бы одну страницу заданий.||
||{% if locale == "ru-ru" %}**Выполнено страниц заданий на одного исполнителя**{% endif %}{% if locale == "en-com" %}**Submitted assignments per Toloker**{% endif %} | Среднее количество выполненных страниц заданий на одного исполнителя.||
||{% if locale == "ru-ru" %}**Просрочено страниц заданий**{% endif %}{% if locale == "en-com" %}**Expired task suites**{% endif %} | Число страниц заданий, у которых истек срок выполнения.

Учитываются страницы, которые исполнители не смогли выполнить вовремя или отказались от их выполнения. Время на страницу заданий указывается при [настройке пула](pool-main.md#table_n3q_vhz_jlb).

Когда исполнитель отказывается выполнять задание — нажимает кнопку **Выйти**, задание оказывается в статусе просроченного. При этом исполнитель может вернуться к выполнению задания снова, если его не выполнили другие исполнители или не удалил из пула заказчик.||
||{% if locale == "ru-ru" %}**Пропущено страниц заданий**{% endif %}{% if locale == "en-com" %}**Skipped task suites**{% endif %} | Число страниц заданий, пропущенных исполнителями. Учитываются страницы, которые исполнители не захотели выполнять, и перешли к следующим.

Когда исполнитель нажимает кнопку **Пропустить**, задание оказывается в статусе пропущенного. При этом исполнитель больше не сможет вернуться к его выполнению.||
|#

{% include [contact-support](../_includes/contact-support.md) %}