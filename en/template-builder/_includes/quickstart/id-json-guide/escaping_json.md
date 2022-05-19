
To add a quotation mark `"` or a backslash `\` to a string, add another backslash `\` to it. Don't escape quotation marks `« »` and `/`.


{% cut "Examples" %}


**Input data**|**Result**
--|--
`"\"Before you pour your heart out, make sure that the \"vessel\" doesn't leak\". \\George Bernard Shaw"`|`"Before you pour your heart out, make sure that the "vessel" doesn't leak". \George Bernard Shaw`
`"«Before you pour your heart out, make sure that the «vessel» doesn't leak». /George Bernard Shaw"`|`«Before you pour your heart out, make sure that the «vessel» doesn't leak». /George Bernard Shaw`


{% endcut %}

