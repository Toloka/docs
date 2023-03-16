# Standard query parameters

#|
|| Parameter | Overview ||
|| **limit** {#limit} | **integer**

Limit on the number of results to return. By default — 50; maximum — 300. ||
|| **id_gt** {#id_gt} | **string**

Objects with an ID greater than the specified value. ||
|| **id_gte** {#id_gte} | **string**

Objects with an ID greater than or equal to the specified value. ||
|| **id_lt** {#id_lt} | **string**

Objects with an ID less than the specified value. ||
|| **id_lte** {#id_lte} | **string**

Objects with an ID less than or equal to the specified value. ||
|| **overlap_gt** {#overlap_gt} | **integer**

Objects with an overlap greater than the specified value. ||
|| **overlap_gte** {#overlap_gte} | **integer**

Objects with an overlap greater than or equal to the specified value. ||
|| **overlap_lt** {#overlap_lt} | **integer**

Objects with an overlap less than the specified value. ||
|| **overlap_lte** {#overlap_lte} | **integer**

Objects with an overlap less than or equal to the specified value. ||
|| **task_id_gt** {#task_id_gt} | **string**

Tasks with an ID greater than the specified value. ||
|| **task_id_gte** {#task_id_gte} | **string**

Tasks with an ID greater than or equal to the specified value. ||
|| **task_id_lt** {#task_id_lt} | **string**

Tasks with an ID less than the specified value. ||
|| **task_id_lte** {#task_id_lte} | **string**

Tasks with an ID less than or equal to the specified value. ||
|#

## Parameters with a date {#date-parameters}

{% note info %}

The date is specified in UTC in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`.

{% endnote %}

#|
|| Parameter | Overview ||
|| **created_gt** {#created_gt} | **string**

Objects issued or created after the specified date. ||
|| **created_gte** {#created_gte} | **string**

Objects issued or created on or after the specified date. ||
|| **created_lt** {#created_lt} | **string**

Objects issued or created before the specified date. ||
|| **created_lte** {#created_lte} | **string**

Objects issued or created on or before the specified date. ||
|| **last_started_gt** {#last_started_gt} | **string**

Objects that were last opened after the specified date. ||
|| **last_started_gte** {#last_started_gte} | **string**

Objects that were last opened on or after the specified date. ||
|| **last_started_lt** {#last_started_lt} | **string**

Objects that were last opened before the specified date. ||
|| **last_started_lte** {#last_started_lte} | **string**

Objects that were last opened on or before the specified date. ||
|| **modified_gt** {#modified_gt} | **string**

Objects modified after the specified date. ||
|| **modified_gte** {#modified_gte} | **string**

Objects modified on or after the specified date. ||
|| **modified_lt** {#modified_lt} | **string**

Objects modified before the specified date. ||
|| **modified_lte** {#modified_lte} | **string**

Objects modified on or before the specified date. ||
|| **submitted_gt** {#submitted_gt} | **string**

Objects issued or created after the specified date. ||
|| **submitted_gte** {#submitted_gte} | **string**

Objects issued or created on or after the specified date. ||
|| **submitted_lt** {#submitted_lt} | **string**

Objects issued or created before the specified date. ||
|| **submitted_lte** {#submitted_lte} | **string**

Objects issued or created on or before the specified date. ||
|| **finished_gt** | **string**

Objects completed after the specified date. ||
|| **finished_gte** | **string**

Objects completed after or on the specified date. ||
|| **finished_lt** | **string**

Objects completed before the specified date. ||
|| **finished_lte** | **string**

Objects completed on or before the specified date. ||
|| **accepted_gt** {#accepted_gt} | **string**

Objects accepted by the requester after the specified date. ||
|| **accepted_gte** {#accepted_gte} | **string**

Objects accepted by the requester after or on the specified date. ||
|| **accepted_lt** {#accepted_lt} | **string**

Objects accepted by the requester before the specified date. ||
|| **accepted_lte** {#accepted_lte} | **string**

Objects accepted by the requester before or on the specified date. ||
|| **rejected_gt** {#rejected_gt} | **string**

Objects rejected by the requester after the specified date. ||
|| **rejected_gte** {#rejected_gte} | **string**

Objects rejected by the requester after or on the specified date. ||
|| **rejected_lt** {#rejected_lt} | **string**

Objects rejected by the requester before the specified date. ||
|| **rejected_lte** {#rejected_lte} | **string**

Objects rejected by the requester before or on the specified date. ||
|| **skipped_gt** {#skipped_gt} | **string**

Objects skipped after the specified date. ||
|| **skipped_gte** {#skipped_gte} | **string**

Objects skipped after or on the specified date. ||
|| **skipped_lt** {#skipped_lt} | **string**

Objects skipped before the specified date. ||
|| **skipped_lte** {#skipped_lte} | **string**

Objects skipped before or on the specified date. ||
|| **expired_gt** {#expired_gt} | **string**

Objects that expire after the specified date. ||
|| **expired_gte** {#expired_gte} | **string**

Objects that expire after or on the specified date. ||
|| **expired_lt** {#expired_lt} | **string**

Objects that expire before the specified date. ||
|| **expired_lte** {#expired_lte} | **string**

Objects that expire before or on the specified date. ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}