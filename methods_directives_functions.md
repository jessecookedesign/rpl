# Methods, Directives, and Functions

# Table of Contents
- [if else](https://www.github.com/jessecookedesign/rpl/methods_directives_functions#if-else)
- [skip](https://www.github.com/jessecookedesign/rpl/methods_directives_functions#skip)
- [list](https://www.github.com/jessecookedesign/rpl/methods_directives_functions#list)
- [assign](https://www.github.com/jessecookedesign/rpl/methods_directives_functions#assign)

---

# if else
#### Syntax:
```html
<#if condition>
    <!-- do something -->
<#elseif condition>
    <!-- do something -->
<#else>
    <!-- do something -->
<#/if>
```
#### Example:
```html
<#if FIRST_NAME?has_content && LAST_NAME?has_content>
    Hi there, ${FIRST_NAME}, ${LAST_NAME}!
<#elseif FIRST_NAME?has_content && LAST_NAME?isnull>
    Hi there, ${FIRST_NAME}!
<#else>
    Hi there!
<#/if>
```

Notes:

`<#if>` must be closed.

`<#if>` can be used alone with out `<#else>` or `<#elseif>`

`<#else>` and `<#elseif>` do not need to be closed.

---

# skip
#### Syntax:
```html
<#skip "message">
```
#### Example:
```html
<#skip "Customer didn't have rewards">
```

Notes:

`<#skip>` does not need to be closed.

They are typically placed inside an if-else statement.

They can also be placed in a subject line or preheader to skip an entire campaign (effectively pausing it)

---

# list
Description here

---

# assign
Description here

---
