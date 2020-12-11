# Built-ins
| Built-in name | Description | Example Gist |
| :--- | :--- | :--- |
| **Basic conversions** |||
| `?string` | Convert to a string ||
| `?number` | Convert to a number ||
| `?int` | Pull integer from a number `(-1.9?int = 1)` ||
| **Checking values** |||
| `?has_content` | Check if the field has content (a value) ||
| `?isnull` | Check if the field value is null (empty string ““) ||
| `?contains("example")` | Check if the string contains specified content ||
| `?length` | Returns number of characters in the string ||
| `?starts_with` | Check if the string starts with specified content ||
| `?is_string` | Check if value is a string ||
| `?is_number` | Check if value is a number ||
| `?is_boolean` | Check if value is a boolean ||
| `?is_date` | Check if value is a date ||
| **Modifying strings** |||
| `?lower_case` | Convert string to lowercase ||
| `?upper_case` | Convert string to uppercase ||
| `?cap_first` | Capitalize first letter of the string ||
| `?uncap_first` | Un-capitalizes first letter of the string ||
| `?capitalize` | Capitalize first letter of every word ||
| `?date("MM/DD/YYYY")` | Convert string to “date” format, specify format as parameter ||
| `?time("HH:MM:SS")` | Convert string to “time” format, specify format as parameter ||
| `?datetime("YYYY-MM-DD HH:MM a")` | Convert string to “date and time” format, specify format as parameter ||
| `?url` | Modifies the string with URL escaping ||
| `?replace("param1", "param2")` | Replace any instance of first parameter with second parameter |* [Gist here](https://gist.github.com/jessecookedesign/beda85404fab6d68622b5c8df0543798)|
| **Working with numbers** |||
| `?round` | Rounds to the nearest whole number ||
| `?floor` | Rounds the number down ||
| `?ceiling` | Rounds the number up ||
| `?sort` | Sort the numbers low to high | * [Gist here](https://gist.github.com/jessecookedesign/a22c28fc65a967d7721d90eeb9763a07) |
| **Escaping code** |||
| `?html` | Escapes HTML characters (`>` is converted to `&gt;` etc) ||
| `?json_string` | Escapes the string with the escaping rules of JSON language ||
| `?xml` | Escapes XML characters ||
| **Doing math** |||
| `?eval` | Evaluates the string in the expression ( `“1+2”?eval` = 3 ) ||
| **Encoding** |||
| `?hex` | Converts a string into a hex-encoded string  ||
| `?base64` | Converts a string to base64 format ||
| **Other** |||
| `?skip` | Shorthand way to skip if the field is empty ( `${FNAME?skip}`  is just like writing `<#if FNAME?isnull><#skip></#if>`) |
