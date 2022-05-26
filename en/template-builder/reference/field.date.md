# field.date

A component for entering the date and time in the desired format and range.

You can set a list of dates that the user cannot select.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.date" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `blockList` | _array_ | List of dates that the user cannot select. ||
|| `blockList[]` | _string_ | Date that the user cannot select. ||
|| `format`<span style="color: red">\*</span> | _string_ | Format of the date entered by the user:

- `date-time` — date and time.
- `date` — date only.
  ||
  || `hint` | _string_ | Hint text. ||
  || `max` | _string_ | The latest date and time in the YYYY-MM-DD hh:mm format that the user can select. Where:

- YYYY is the year.
- MM is the month.
- DD is the day.
- hh is the time in hours.
- mm is the time in minutes.
  ||
  || `min` | _string_ | The earliest date and time in the YYYY-MM-DD hh:mm format that the user can select. Where:

- YYYY is the year.
- MM is the month.
- DD is the day.
- hh is the time in hours.
- mm is the time in minutes.
  ||
  || `placeholder` | _string_ | A semi-transparent label that is shown in the box when it is empty. ||
  || `validation` | _condition_ | Validation based on condition. ||
  |#
