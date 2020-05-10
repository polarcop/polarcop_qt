![](https://github.com/polarcop/polarcop_qt/blob/master/polarcop_qt.png)

## Usage
This version of quick tasks supports builds from `1.0.16` onwards and supports both `QT`(Quick Tasks) and `PT` (Premade Tasks)

Polar Cop quick tasks allows anyone to quickly create and start tasks for Polar Cop's iOS platform. 

### Supported Sites
- [Yeezy Supply](#yeezysupply)
- [Solebox](#solebox)
- [Wood Wood](#woodwood)
- [Footpatrol](#footpatrol)
- [Size](#size)


## Format
Polar Cop `QT`& `PT` requests must be passed as url query parameters to the `qt.polarcop.com`domain.
*(URL chaining is supported)*
```http
https://qt.polarcop.com?<parameters_here>
```
**Points:**
 - If you wish to use the `random` value for optional parameters **do not** provide them.
 - To use `PT` append `start=true` as the parameter 

| Parameter |  Description              | Required?              | Default              |
|-----------|---------------------------|------------------------|----------------------|
| `key`     |  Keyword/URL              | Required without `pid` |                      |
| `pid`     |  Product ID               | Required without `key` |                      |
| `size`    |  Product Size             | Optional               | `random`             |
| `colour`  |  Product Colour           | Optional               | `random`             |
| `category`|  Product Category         | Optional               |  *site dependant*    |
| `mode`    |  Task mode                | Optional               |  *site dependant*    |
| `start`   |  Should Tasks Auto Start  | Optional               |  `true`              |

## YeezySupply
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ✅      | `pid`     | PID Only
| ✅      | `size`    | e.g 11
| ❌      | `colour`  | 
| ❌      | `category`| 

```
[PATH]: ==> https://qt.polarcop.com/yeezysupply

e.g https://www.yeezysupply.com/product/FW6345 

[PID]: ==> https://qt.polarcop.com/yeezysupply?pid={{product_id}}
       ==> https://qt.polarcop.com/yeezysupply?pid=FW6345

[URL]: ==> https://qt.polarcop.com/yeezysupply?key={{product_url}}
       ==> https://qt.polarcop.com/yeezysupply?key=https://www.yeezysupply.com/product/FW6345
```

## Solebox
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ✅      | `pid`     | PID Only
| ✅      | `size`    | e.g 11
| ❌      | `colour`  | 
| ❌      | `category`| 


```
[PATH]: ==> https://qt.polarcop.com/solebox

e.g https://www.solebox.com/en_GB/p/adidas_consortium-424_pro_model-bntora-01808119.html

[PID]: ==> https://qt.polarcop.com/solebox?pid={{product_id}}
       ==> https://qt.polarcop.com/solebox?pid=01808119

[URL]: ==> https://qt.polarcop.com/solebox?key={{product_url}}
       ==> https://qt.polarcop.com/solebox?key=https://www.solebox.com/en_GB/p/adidas_consortium-424_pro_model-bntora-01808119.html
```

**N.B.** When providing a link for solebox, the region within the url is stripped and replaced according to the profile region. Therefore, providing region specific links is not required.

## WoodWood
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ❌      | `pid`     | 
| ✅      | `size`    | e.g 11
| ❌      | `colour`  | 
| ❌      | `category`| 


```
[PATH]: ==> https://qt.polarcop.com/woodwood

e.g https://www.woodwood.com/commodity/10274-new-balance-m1300cls

[URL]: ==> https://qt.polarcop.com/woodwood?key={{product_url}}
       ==> https://qt.polarcop.com/woodwood?key=https://www.woodwood.com/commodity/10274-new-balance-m1300cls
```

**N.B.** For woodwood, if you do not have the full url you may also provide the url as follows: `https://www.woodwood.com/commodity/{{product_id}}` but you will still need to use the `key` parameter


## Footpatrol
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | PID / URL
| ✅      | `pid`     | Variant ID Only
| ✅      | `size`    | e.g 11
| ❌      | `colour`  | 
| ❌      | `category`| 


```
[PATH]: ==> https://qt.polarcop.com/footpatrol

e.g https://www.footpatrol.com/product/white-adidas-originals-x-424-sc-premiere/346956_footpatrolcom/

[SID]: ==> https://qt.polarcop.com/footpatrol?key={{product_variant_id}}
       ==> https://qt.polarcop.com/footpatrol?key=346951_footpatrolcom.001469792

[PID]: ==> https://qt.polarcop.com/footpatrol?key={{product_id}}
       ==> https://qt.polarcop.com/footpatrol?key=346956_footpatrolcom

[URL]: ==> https://qt.polarcop.com/footpatrol?key={{product_url}}
       ==> https://qt.polarcop.com/footpatrol?key=https://www.footpatrol.com/product/white-adidas-originals-x-424-sc-premiere/346956_footpatrolcom
```

**N.B.** 
 - For footpatrol, if you do not have the full url you may also provide the url as follows: ` https://qt.polarcop.com/footpatrol?key=https://www.footpatrol.com/product/polarcop_com/{{product_id}}`
 - Footp 

## Size
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | PID / URL
| ✅      | `pid`     | Variant ID Only
| ✅      | `size`    | e.g 11
| ❌      | `colour`  | 
| ❌      | `category`| 


```
[PATH]: ==> https://qt.polarcop.com/size

e.g https://www.sizeofficial.de/product/nike-daybreak-type/356900_sizede/

[PID]: ==> https://qt.polarcop.com/size?pid={{product_variant_id}}
       ==> https://qt.polarcop.com/size?pid=356900_sizede.001556915

[PID]: ==> https://qt.polarcop.com/size?key={{product_id}}
       ==> https://qt.polarcop.com/size?key=356900_sized

[URL]: ==> https://qt.polarcop.com/size?key={{product_url}}
       ==> https://qt.polarcop.com/size?key=https://www.sizeofficial.de/product/nike-daybreak-type/356900_sizede/
```


## Notice
The documentation is accurate as of `May 10th 2020`, for further details please join our faq discord: https://discord.gg/3VNH4AE for more details, alternatively you can email our support email: support{@}polarcop.com
