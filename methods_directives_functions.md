# Methods, Directives, and Functions

# Table of Contents
- [if else](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#if-else)
- [skip](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#skip)
- [list](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#list)
- [data](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#data)
- [assign](https://github.com/jessecookedesign/rpl/blob/master/methods_directives_functions.md#assign)

---

# if else
Write a set of conditions and outcomes
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

#### Notes:

`<#if>` must be closed.

`<#if>` can be used alone with out `<#else>` or `<#elseif>`

`<#else>` and `<#elseif>` do not need to be closed.

---

# skip
Skip the send of an email
#### Syntax:
```html
<#skip "message">
```
#### Example:
```html
<#skip "Customer didn't have rewards">
```

#### Notes:

`<#skip>` does not need to be closed.

They are typically placed inside an if-else statement.

They can also be placed in a subject line or preheader to skip an entire campaign (effectively pausing it)

---

# list
Loop through a set of data
#### Syntax:
```html
<#list DATA as name>
    <!-- access a data point in the list -->
    ${name.FIELD_NAME}
</#list>
```

#### Example:
```html
<#list PRODUCT_TABLE as prod>
    ${prod.name}
    <br>
    ${prod.price}
    <br>
    ${prod.quantity}
</#list>
```

#### Notes:

`<#list>` must be closed.

Anything inside the opening `<#list>` and closing `</#list>` will be repeated for each item in the set of data.

<br />
<br />

### Adding a break in the loop
You can break the loop with `<#break>`

This can be paired with an `<#if>` statement if needed

#### Example:
```html
<#list PRODUCT_TABLE as prod>
    ${prod.name}
    <#if prod.name = "Shoes">
        <#break>
    </#if>
</#list>
```

<br />
<br />

### Check if there's another item after this iteration
You can check if this iteration has another one after it using `_has_next`

This is commonly used to style every iteration but the last, or only the last.

This can be paired with an `<#if>` statement if needed

#### Example:
```html
<#list PRODUCT_TABLE as prod>
    ${prod.name}
    <#if prod_has_next>
        <hr>
    </#if>
</#list>
```

<br />
<br />

### Index of iteration
Get the index (number) of the iteration using `_index`

This can be paired with an `<#if>` statement if needed

#### Example listing the index:
```html
<#list PRODUCT_TABLE as prod>
    ${prod_index}. ${prod.name}
</#list>
```

#### Example using the index with an <#if> statement:
```html
<#list PRODUCT_TABLE as prod>
    <#if prod_index = 0>
        Top seller: ${prod.name}
    <#else>
        ${prod.name}
    </#if>
</#list>
```

---

# data
Loop through a set of data in a table and filter selection.
#### Syntax:
```html
<#data DATA as name>
<#filter COLUMN_NAME = something>
<#fields FIELD_NAME ANOTHER_FIELD_NAME>
    <!— access a data point —>
    ${name.FIELD_NAME}
</#data>
```

#### Example:
```html
<#data PRODUCT_TABLE as prod>
<#filter name = “jeans”>
<#fields name price quantity>
    ${prod.name}
    <br>
    ${prod.price}
    <br>
    ${prod.quantity}
</#data>
```
<br />
> WHAT'S HAPPENING:
>
> Select PRODUCT_TABLE and name it "prod"
> Filter/select the rows where column "name" is "jeans"
> Grab the columns "name", "price", and "quantity"

<br />

#### Notes:

`<#data>` must be closed.

`<#filter>` and `<#fields>` do not need to be closed.

Anything inside the opening `<#data>` and closing `</#data>` will be repeated for each item in the set of data.

<br />
<br />

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
