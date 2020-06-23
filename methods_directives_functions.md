# Methods, Directives, and Functions

# Table of Contents
- [if else](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#if-else)
- [skip](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#skip)
- [list](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#list)
- [assign](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#assign)

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
#### Syntax:
```html
<!-- String -->
<#assign name = "value">
    
<!-- Number -->
<#assign name = 10>
    
<!-- Math -->
<#assign name = 1 + 1>
    
<!-- Boolean -->
<#assign name = true>
    
<!-- Built-in -->
<#assign name = .built-in-name>
```
#### Example:
```html
<!-- String -->
<#assign state = "Minnesota">
<h1>Find a place to stay in ${state}.</h1>
    
<!-- Number -->
<#assign age = 24>
<h1>The best cars for ${age} year olds!</h1>
    
<!-- Math -->
<#assign age = 24>
<#assign newAge = age + 10>
<h1>In ten years, when you're ${newAge}...</h1>
    
<!-- Boolean -->
<#assign member = false>
<#if member == false>Sign up today!</#if>
    
<!-- Built-in -->
<#assign today = .today>
<h1>Today's date: ${today}</h1>
```

---
