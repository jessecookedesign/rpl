---
# Basics
## What is RPL?
RPL stands for Responsys Personalization Language.

At its core, RPL is designed to generate HTML and Text for emails built in Responsys Interact. Although Responsys documentation says it's "not a full-blown programming language", it does have a lot of programming capabilties.


## How does RPL work?
Generally, RPL is added to HTML to pull data from various data sources inside Responsys before the email ships.

It can also be used to do a number of things like:
- if-else statements
- reference links in a link table
- pass data to a link table
- assign variables
- parse XML or JSON data
- do math
- check values
- etc


---
# Table of Contents
- [Built-ins](https://github.com/jessecookedesign/rpl#built-ins)
- [Methods, directives, and functions](https://github.com/jessecookedesign/rpl#methods-directives-and-functions)
- [Responsys errors](https://github.com/jessecookedesign/rpl#responsys-errors)


---
# Built-ins
| Built-in name | Description |
| :--- | :--- |
| **Basic conversions** ||
| `?string` | Convert to a string |
| `?number` | Convert to a number |
| `?int` | Pull integer from a number `(-1.9?int = 1)` |
| **Checking values** ||
| `?has_content` | Check if the field has content (a value) |
| `?isnull` | Check if the field value is null (empty string ““) |
| `?contains("example")` | Check if the string contains specified content |
| `?length` | Returns number of characters in the string |
| `?starts_with` | Check if the string starts with specified content |
| `?is_string` | Check if value is a string |
| `?is_number` | Check if value is a number |
| `?is_boolean` | Check if value is a boolean |
| `?is_date` | Check if value is a date |
| **Modifying strings** ||
| `?lower_case` | Convert string to lowercase |
| `?upper_case` | Convert string to uppercase |
| `?cap_first` | Capitalize first letter of the string |
| `?uncap_first` | Un-capitalizes first letter of the string |
| `?capitalize` | Capitalize first letter of every word |
| `?date("MM/DD/YYYY")` | Convert string to “date” format, specify format as parameter |
| `?time("HH:MM:SS")` | Convert string to “time” format, specify format as parameter |
| `?datetime("YYYY-MM-DD HH:MM a")` | Convert string to “date and time” format, specify format as parameter |
| `?url` | Modifies the string with URL escaping |
| **Working with numbers** ||
| `?round` | Rounds to the nearest whole number |
| `?floor` | Rounds the number down |
| `?ceiling` | Rounds the number up |
| **Escaping code** ||
| `?html` | Escapes HTML characters (`>` is converted to `&gt;` etc) |
| `?json_string` | Escapes the string with the escaping rules of JSON language |
| `?xml` | Escapes XML characters |
| **Doing math** ||
| `?eval` | Evaluates the string in the expression ( `“1+2”?eval` = 3 ) |
| **Encoding** ||
| `?hex` | Converts a string into a hex-encoded string  |
| `?base64` | Converts a string to base64 format |
| **Other** ||
| `?skip` | Shorthand way to skip if the field is empty ( `${FNAME?skip}`  is just like writing `<#if FNAME?isnull><#skip></#if>`) |

---
# Methods, Directives, and Functions

## Most common

### if else
Description here

### skip
Description here

### list
Description here

### assign
Description here

---
# Responsys errors

### "Expected hash"
A hash may be referring to data from a `<#data>` tag and `<#field>` tag.

Check to make sure that you are calling a hash inside the `<#data>` tags. If you close your `</#data>` tag before using the hash, Responsys won't know what to do.

#### Example that throws error:
```html
<#data STORE_DATA as mystore>
    <#fields ADDRESS LOCATION_NAME>
</#data>
<table>
    <tr>
        <td>
            <p>${mystore.LOCATION_NAME}</p>
        </td>
    </tr>
</table>
```

#### Example that works:
```html
<#data STORE_DATA as mystore>
    <#fields ADDRESS LOCATION_NAME>
    <table>
        <tr>
            <td>
                <p>${mystore.LOCATION_NAME}</p>
            </td>
        </tr>
    </table>
</#data>
```
