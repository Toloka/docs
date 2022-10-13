# Статистика по пулу

Отслеживать выполнение заданий можно на странице [пула](../../glossary.md#pool) или нажав кнопку **Статистика**. Вы также можете узнавать о событии из писем на электронную почту, уведомлений в браузере или на странице {% if locale == "ru-ru" %}**Сообщения**{% endif %}{% if locale == "en-com" %}**Messages**{% endif %}. В [Профиле]({{ profile }}) откройте вкладку {% if locale == "ru-ru" %}**Уведомления**{% endif %}{% if locale == "en-com" %}**Notifications**{% endif %} и выберите, какие уведомления и каким способом вы хотите получать.

#|
||**Поле**|**Описание**||
||{% if locale == "ru-ru" %}**Приблизительное время завершения**{% endif %}{% if locale == "en-com" %}**Approximate completion time**{% endif %} | Ожидаемое время выполнения заданий в днях и часах. Рассчитывается исходя из среднего времени на одну страницу заданий.

Формула: $T_{left}={Assign_{left}}\times{T_{assign}}$,

где:

$Assign_{left}$ — число невыполненных страниц или выполненных в недостаточном [перекрытии](../../glossary.md#overlap-ru).

$T_{assign}$ — среднее время на одну страницу. Вычисляется исходя из времени, которое прошло с момента открытия пула, и числа выполненных страниц.

Это прогнозируемый показатель, который обновляется по ходу выполнения заданий исполнителями.

**Рекомендации**

- Если этот показатель большой, скорее всего в вашем проекте осталось мало исполнителей. Проверьте количество [активных исполнителей](#active-users), среднее время выполнения страницы заданий.

- Если раньше показатель был маленький, а затем большой — проверьте настройки правил контроля качества, возможно у вас слишком много забаненных исполнителей.

- Если раньше показатель был большой и сейчас остается большим, а количество [активных исполнителей](#active-users) маленькое — проверьте настройки фильтров и обучение. Возможно мало кто видит ваши задания или не могут пройти обучение.||
||{% if locale == "ru-ru" %}**Среднее время выполнения страницы заданий**{% endif %}{% if locale == "en-com" %}**Average assignment submit time**{% endif %} | Среднее время выполнения [страницы заданий в пуле](../../glossary.md#task-page-ru). Указывается в секундах.

Вычисляется по 1000 последних выполненных страниц заданий.

**Рекомендации**

Если среднее время больше, чем вы ожидали, а качество результатов низкое, перепроверьте инструкцию.

Возможно ваши задания слишком сложные. Используйте [декомпозицию](solution-architecture.md) и проверьте интерфейс задания. Затем попробуйте протестировать их на тех же исполнителях в формате обучения или опроса.

Если среднее время меньше, а качество результатов невысокое, пересмотрите [настройки контроля качества](control.md).||
||{% if locale == "ru-ru" %}**Просрочено страниц заданий**{% endif %}{% if locale == "en-com" %}**Expired task suites**{% endif %} | Число страниц заданий, у которых истек срок выполнения.

Учитываются страницы, которые исполнители не смогли выполнить вовремя или отказались от их выполнения. Время на страницу заданий указывается при [настройке пула](pool-main.md#table_n3q_vhz_jlb).

Когда исполнитель отказывается выполнять задание — нажимает кнопку **Выйти**, задание оказывается в статусе просроченного. При этом исполнитель может вернуться к выполнению задания снова, если его не выполнили другие исполнители или не удалил из пула заказчик.

**Рекомендации**

Исполнители могли отказаться выполнять страницу заданий потому что:

- Задания слишком сложные.
- Заданий на странице было много.
- Задания не работают — ответы невозможно отправить.
- Исполнители не разобрались в инструкции и в интерфейсе задания.

Если в вашем пуле много просроченных страниц заданий, мы рекомендуем ознакомиться с разделом [Советы по составлению заданий](faq.md).||
||{% if locale == "ru-ru" %}**Пропущено страниц заданий**{% endif %}{% if locale == "en-com" %}**Skipped task suites**{% endif %} | Число страниц заданий, пропущенных исполнителями. Учитываются страницы, которые исполнители не захотели выполнять, и перешли к следующим.

Когда исполнитель нажимает кнопку **Пропустить**, задание оказывается в статусе пропущенного. При этом исполнитель больше не сможет вернуться к его выполнению.

**Рекомендации**

Если в вашем пуле много пропущенных страниц заданий, мы рекомендуем ознакомиться с разделом [Советы по составлению заданий](faq.md), а также настроить правило [пропуск заданий](skipped-assignments.md).||
||{% if locale == "ru-ru" %}**Время выполнения**{% endif %}{% if locale == "en-com" %}**Submit time**{% endif %} | Интервал времени от запуска пула до его выполнения. Значение выводится, если все задания пула выполнены.||
||{% if locale == "ru-ru" %}**Дата запуска**{% endif %}{% if locale == "en-com" %}**Start date**{% endif %} | Дата запуска пула.||
||{% if locale == "ru-ru" %}**Дата завершения**{% endif %}{% if locale == "en-com" %}**Completion date**{% endif %} | Дата, когда было завершено выполнение всех заданий пула.||
||{% if locale == "ru-ru" %}**Задания**{% endif %}{% if locale == "en-com" %}**Assignments**{% endif %} | На графике показано количество заданий по типам:

- {% if locale == "ru-ru" %}**Отправлено на проверку**{% endif %}{% if locale == "en-com" %}**Submitted**{% endif %} — количество страниц заданий, отправленных на проверку.

- {% if locale == "ru-ru" %}**Принятые**{% endif %}{% if locale == "en-com" %}**Accepted**{% endif %} — количество принятых страниц заданий.

- {% if locale == "ru-ru" %}**Пропущенные**{% endif %}{% if locale == "en-com" %}**Skipped**{% endif %} — количество страниц заданий, [пропущенных исполнителями](pool_statistic-pool.md#skipped-tasks).

- {% if locale == "ru-ru" %}**Просроченные**{% endif %}{% if locale == "en-com" %}**Expired**{% endif %} — число страниц заданий, у которых истек срок выполнения. Учитываются страницы, которые исполнители не смогли выполнить вовремя или отказались от их выполнения.

**Рекомендации**

Если у вас много пропущенных или просроченных заданий, мы рекомендуем ознакомиться с разделом [Советы по составлению заданий](faq.md), а также настроить правило [пропуск заданий](skipped-assignments.md).||
||{% if locale == "ru-ru" %}**Среднее перекрытие**{% endif %}{% if locale == "en-com" %}**Average overlap**{% endif %} | Среднее количество исполнителей, выполнивших одно и то же задание в пуле.

**Рекомендации**

Если вам кажется, что это число слишком большое или маленькое, возможно, вы неверно настроили [повторное выполнение заданий после блокировки исполнителя](restore-task-overlap.md) или [обработку отклоненных и принятых заданий](reassessment-after-accepting.md) . Дополнительно стоит проверить:

- [динамическое перекрытие](dynamic-overlap.md) (incremental relabeling, IRL);

- [выборочную проверку мнением большинства](selective-mvote.md).||
||{% if locale == "ru-ru" %}**Время выполнения страницы заданий**{% endif %}{% if locale == "en-com" %}**Assignment submit time**{% endif %} | Среднее время, потраченное исполнителями на выполнение страницы заданий в пуле. Указывается в секундах.||
||{% if locale == "ru-ru" %}**Потрачено денег (+ комиссия)**{% endif %}{% if locale == "en-com" %}**Budget spent (+ fee)**{% endif %} | Сумма потраченных средств в пуле. В скобках указана сумма [комиссии](budget.md).

Если вы потратили больше, чем планировали, проверьте настройки цены в пуле и правила контроля качества. Например, [динамическое ценообразование](dynamic-pricing.md#section_ucl_3hl_vlb) и [повторное выполнение заданий после блокировки исполнителя](restore-task-overlap.md) увеличивают стоимость пула.

Обратите внимание, что минимальная комиссия составляет 0,005 $.

**Рекомендации**

В первую очередь стоит проверить [правила контроля качества](control.md), отключить правила, которые увеличивают перекрытие, а затем пересмотреть назначенную за страницу заданий цену. Возможно, ее стоит снизить. Но не делайте ее неоправданно маленькой.

Также вы можете увеличить или уменьшить количество заданий на странице и скорректировать в соответствии с этим цену.||
||{% if locale == "ru-ru" %}**Приблизительный бюджет (+ комиссия)**{% endif %}{% if locale == "en-com" %}**Approximate budget (+ fee)**{% endif %} | Сумма израсходованных средств и ожидаемых затрат (если все задания будут выполнены и все ответы будут приняты). В скобках указана сумма [комиссии](../../glossary.md#comission-fee-ru).

**Рекомендации**

Это показатель, использует имеющиеся данные для прогнозирования итоговой стоимости. Если он вас не устраивает, остановите пул и измените настройки. Подумайте, нужно ли вам [динамическое перекрытие](dynamic-overlap.md), [динамическое ценообразование](dynamic-pricing.md) и, например, [повторное выполнение заданий после блокировки исполнителя](restore-task-overlap.md).

Пересмотрите цену за страницу заданий, возможно, вы ее снизите без потери интереса исполнителей.||
||{% if locale == "ru-ru" %}**Затраты (комиссия не включена)**{% endif %}{% if locale == "en-com" %}**Spending (excluding fee)**{% endif %} | На графике показана сумма потраченных средств без учета комиссии:

- {% if locale == "ru-ru" %}**Затраты на бонусы**{% endif %}{% if locale == "en-com" %}**Spending on bonuses**{% endif %} — сумма средств, потраченных на бонусы.
- {% if locale == "ru-ru" %}**Затраты на задания**{% endif %}{% if locale == "en-com" %}**Spending on assingments**{% endif %} — сумма средств, потраченных на задания.||
||{% if locale == "ru-ru" %}**Средняя стоимость задания**{% endif %}{% if locale == "en-com" %}**Average cost per task**{% endif %} | Средняя цена разметки одного основного задания в пуле в долларах США с учетом перекрытия.

Обратите внимание, что указывается стоимость одного основного задания, а не всей страницы с учетом перекрытия.

**Рекомендации**

Если цена вам кажется завышенной, проверьте настройки цены в пуле и правила контроля качества. Например, [динамическое ценообразование](dynamic-pricing.md#section_ucl_3hl_vlb) и [повторное выполнение заданий после блокировки исполнителя](restore-task-overlap.md) увеличивают стоимость пула.||
||{% if locale == "ru-ru" %}**Заработок в час**{% endif %}{% if locale == "en-com" %}**Earnings per hour**{% endif %} | Средний заработок исполнителей за один час разметки в пуле в долларах США. Заработок включает бонусы за задания.||
||**Качество по контрольным и обучающим заданиям пула**{% if locale == "en-com" %}**Quality on control tasks and training tasks in the pool**{% endif %} | Этот график показывает процент правильных ответов на контрольные и обучающие задания.

**Рекомендации**

Если этот показатель слишком низкий, возможно ваши задания слишком сложные или инструкция написана недостаточно понятно.

Возможно в контрольных заданиях есть ошибки или они неактуальны. Если в заданиях есть ссылки, проверьте, что они работают.

Еще одна причина — неверные настройки правил контроля качества. Они недостаточно отсеивают плохих исполнителей.||
||{% if locale == "ru-ru" %}**Заблокировано по правилам**{% endif %}{% if locale == "en-com" %}**Blocked by rules**{% endif %} | Число исполнителей, заблокированных по правилам контроля качества.

Обратите внимание, что число исполнителей считается отдельно по каждому правилу.

**Рекомендации**

Если этот показатель слишком высокий или низкий, проверьте настройки правил контроля качества.||
||{% if locale == "ru-ru" %}**Заблокированные исполнители**{% endif %}{% if locale == "en-com" %}**Banned Tolokers**{% endif %} | Общее число исполнителей, заблокированных в этом пуле.

На графике изображены два показателя:

- **В пуле** — число исполнителей, заблокированных в пуле.
- **У заказчика** — число исполнителей, заблокированных у заказчика.

Обратите внимание, что это только заблокированные исполнители. Исполнители, которым приостановлен доступ к пулу не входят в этот график.

**Рекомендации**

Если их слишком много, проверьте настройки правил контроля качества, возможно, они слишком жесткие.||
||{% if locale == "ru-ru" %}**Активные исполнители, которым доступны задания**{% endif %}{% if locale == "en-com" %}**Active Tolokers with access to pool**{% endif %} | Число исполнителей, отобранных для пула с помощью [фильтров](filters.md). Учитываются только исполнители, которые просматривали и выполняли задания в Толоке в течение последнего часа.

**Рекомендации**

Если их мало, проверьте настройки фильтров и правил контроля качества.||
||{% if locale == "ru-ru" %}**Заинтересовались**{% endif %}{% if locale == "en-com" %}**Interested in pool**{% endif %} | Число исполнителей, которые начали выполнять или выполнили хотя бы одну страницу заданий.

Этот показатель включает в себя как заинтересованных, так и взявшихся исполнителей.

**Рекомендации**

Если разница между заинтересованными и взявшимися исполнителями большая, возможно, они недостаточно хорошо поняли инструкцию, задание оказалось слишком сложным, присутствуют ошибки в интерфейсе.||
||{% if locale == "ru-ru" %}**Взялись**{% endif %}{% if locale == "en-com" %}**Submitted in pool**{% endif %} | Количество исполнителей, которые выполнили хотя бы одну страницу заданий.

**Рекомендации**

Если этот показатель низкий, а количество качественно выполненных заданий вас устраивает, то вы достаточно хорошо настроили проект.||
||{% if locale == "ru-ru" %}**Выполнено страниц заданий на одного исполнителя**{% endif %}{% if locale == "en-com" %}**Submitted assignments per Toloker**{% endif %} | Среднее количество выполненных страниц заданий на одного исполнителя.

Если ваш пул большой и долго размечается, а страниц заданий на одного исполнителя мало, возможно вы неправильно настроили правила контроля качества или фильтры.

**Рекомендации**

Если количество страниц заданий на одного исполнителя близко к порогу срабатываний правил контроля качества — проверьте правила контроля качества, отвечающие за блокировку исполнителей. Дополнительно стоит проверить графики: [заблокированные исполнители](#banned-users) и [заблокировано по правилам](#blocked-rules).||
||{% if locale == "ru-ru" %}**Исполнители, выполнявшие задания в пуле**{% endif %}{% if locale == "en-com" %}**Performers completing tasks in the pool**{% endif %} | Этот график показывает общее число исполнителей, которые выполнили хотя бы одну страницу заданий в пуле.

**Рекомендации**

Если исполнителей мало, проверьте настройки правил контроля качества, фильтры.

Дополнительно стоит проверить графики: [заблокированные исполнители](#banned-users) и [заблокировано по правилам](#blocked-rules).||
|#

## Решение проблем {#troubleshooting}

{% cut "Почему упала скорость выполнения пула?" %}

Возможные причины:

- Вы остановили [обучающий пул](../../glossary.md#training-pool), и тем самым ограничили количество исполнителей имеющих доступ к заданиям. Запустите обучающий пул снова. Исполнителей, которым доступны задания, станет больше.

- Установлены слишком жесткие фильтры, например строгое ограничение по навыку, которого нет у большинства исполнителей.

- Слишком много исполнителей заблокированы. Сделайте правила контроля качества мягче.

{% endcut %}

{% cut "Как ускорить выполнение заданий пула?" %}

- Мотивируйте исполнителей, назначив [публичный навык](nav-create.md#public) и [динамическое ценообразование](dynamic-pricing.md).
- Постарайтесь [повысить рейтинг проекта](project_rating_stat.md), чтобы ваше задание оказалось выше в списке заданий у исполнителей.
- Отрегулируйте [соотношение скорости и качества](adjust.md).
- Установите более высокий [приоритет](pool_poolparams.md#priority) пула среди всех пулов проекта.

{% endcut %}

{% cut "Почему в прогресс-баре максимум выполненных заданий меньше, чем общее загруженное количество?" %}

В прогресс-баре указано количество страниц заданий с учетом перекрытия. Если перекрытие больше единицы, то количество страниц заданий будет отличаться от общего количества заданий.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}