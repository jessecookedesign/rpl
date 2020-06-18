# Responsys errors

# Table of contents:
- [Expected hash](https://github.com/jessecookedesign/rpl/blob/master/responsys_errors#expected-hash)

---

# Expected hash
A hash may be referring to data from a `<#data>` tag and `<#field>` tag.

Check to make sure that you are calling a hash inside the `<#data>` tags. If you close your `</#data>` tag before using the hash, Responsys won't know what to do.

### Example that throws error:
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

### Example that works:
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
