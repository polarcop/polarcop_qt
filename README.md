![](https://github.com/polarcop/polarcop_qt/blob/master/polarcop_qt.png)

## Usage
This version of quick tasks supports builds from `1.0.33` onwards and supports both `QT`(Quick Tasks) and `PT` (Premade Tasks)

Polar Cop quick tasks allows anyone to quickly create and start tasks for Polar Cop's iOS platform. 

**For integration help please dm offline#1977 on discord or dm @rish1s on twitter.**

### Supported Sites
- [Asos](#asos)
- [Mesh Frontend](#meshfe)
- [Mesh Backend](#meshbe)
- [Solebox](#solebox)
- [Supreme](#supreme)
- [Yeezy Supply](#yeezysupply)

## Format
Polar Cop `QT`& `PT` requests must be passed as url query parameters to the `qt.polarcop.com`domain.
*(URL chaining is supported)*
```http
https://qt.polarcop.com/<store_here>?<parameters_here>
```
**Points:**
 - If you wish to use the `random` value for optional parameters **do not** provide them.
 - To use `PT` append `start=false` as the parameter 

| Parameter |  Description              | Required?              | Default              |
|-----------|---------------------------|------------------------|----------------------|
| `key`     |  Keyword/URL              | Required without `pid` |                      |
| `pid`     |  Product ID               | Required without `key` |                      |
| `size`    |  Product Size             | Optional               | `random`             |
| `colour`  |  Product Colour           | Optional               | `random`             |
| `category`|  Product Category         | Optional               |  *site dependant*    |
| `mode`    |  Task mode                | Optional               |  *site dependant*    |
| `start`   |  Should Tasks Auto Start  | Optional               |  `true`              |

### Modes
Please note all modes are case sensitive.
| KEY                | Sites Supported?                                               |
|--------------------|----------------------------------------------------------------|
| `Request`          | `supreme`, `svd`                                               |
| `Browser`          | `yeezysupply`                                                  |
| `Safe_PayPal`      | `solebox`                                                      |
| `Backend`          | `footpatrol`, `size`, `jdsports`, `thehipstore:`               |
| `Backend_PayPal`   | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Fast_Frontend`    | `footpatrol`, `size`, `jdsports`, `thehipstore `               |
| `Cart`             |  `asos`                                                        |

## Asos
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ✅      | `pid`     | PID Only
| ✅      | `size`    | e.g `UK 5` or `EU 40`
| ❌      | `colour`  | 
| ❌      | `category`| 

```
[PATH]: ==> https://qt.polarcop.com/asos

e.g https://www.asos.com/fred-perry/fred-perry-embroidered-logo-t-shirt-in-black/prd/20291607

[PID]: ==> https://qt.polarcop.com/asos?pid={{product_id}}
       ==> https://qt.polarcop.com/asos?pid=20291607

[URL]: ==> https://qt.polarcop.com/yeezysupply?key={{product_url}}
       ==> https://qt.polarcop.com/yeezysupply?key=https://www.asos.com/polar/cop/prd/20291607
       ==> https://qt.polarcop.com/yeezysupply?key=https://www.asos.com/dk/fred-perry/fred-perry-embroidered-logo-t-shirt-in-black/prd/20291607
```
**N.B** Where possible specify the region in URL, see third url example (`?key=https://www.asos.com/dk/....`)

## MeshFE
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | PID / URL
| ✅      | `pid`     | Variant ID Only
| ✅      | `size`    | e.g `11`
| ❌      | `colour`  | 
| ❌      | `category`| 
| ✅      | `mode`    | `Fast_Frontend`

**STORES**:
`footpatrol`, `size`, `jdsports` and `thehipstore`
```
[PATH]: ==> https://qt.polarcop.com/footpatrol
        ==> https://qt.polarcop.com/size
        ==> https://qt.polarcop.com/jdsports
        ==> https://qt.polarcop.com/thehipstore

e.g https://www.footpatrol.com/product/white-adidas-originals-x-424-sc-premiere/346956_footpatrolcom/

[SID]: ==> https://qt.polarcop.com/footpatrol?pid={{product_variant_id}}&mode=Fast_Frontend
       ==> https://qt.polarcop.com/footpatrol?pid=346951_footpatrolcom.001469792&mode=Fast_Frontend

[PID]: ==> https://qt.polarcop.com/footpatrol?key={{product_id}}&mode=Fast_Frontend
       ==> https://qt.polarcop.com/footpatrol?key=346956_footpatrolcom&mode=Fast_Frontend

[URL]: ==> https://qt.polarcop.com/footpatrol?key={{product_url}}&mode=Fast_Frontend
       ==> https://qt.polarcop.com/footpatrol?key=https://www.footpatrol.com/product/white-adidas-originals-x-424-sc-premiere/346956_footpatrolcom&mode=Fast_Frontend
```

**N.B.** 
 - If you do not have the full url you may also provide the url as follows: ` https://qt.polarcop.com/footpatrol?key=https://www.footpatrol.com/product/polarcop_com/{{product_id}}`
 - Supplying either `pid` or `key` is permitted at this time, for best practise we suggest following the guidelines as above.
 - Ensure you pass a frontend mode e.g `&mode=Fast_Frontend`
 
 ## MeshBE
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | PID / URL
| ✅      | `pid`     | Variant ID Only
| ✅      | `size`    | e.g `11`
| ❌      | `colour`  | 
| ❌      | `category`| 
| ✅      | `mode`    | `Backend`, `Backend_PayPal`

**STORES**:
`footpatrol`, `size`, `jdsports` and `thehipstore`
```
[PATH]: ==> https://qt.polarcop.com/footpatrol
        ==> https://qt.polarcop.com/size
        ==> https://qt.polarcop.com/jdsports
        ==> https://qt.polarcop.com/thehipstore

e.g https://www.footpatrol.com/product/white-adidas-originals-x-424-sc-premiere/346956_footpatrolcom/

[SID]: ==> https://qt.polarcop.com/footpatrol?pid={{product_variant_id}}&mode=Backend_PayPal
       ==> https://qt.polarcop.com/footpatrol?pid=346951_footpatrolcom.001469792&mode=Backend_PayPal

[PID]: ==> https://qt.polarcop.com/footpatrol?key={{product_id}}&mode=Backend_PayPal
       ==> https://qt.polarcop.com/footpatrol?key=346956_footpatrolcom&mode=Backend_PayPal

[URL]: ==> https://qt.polarcop.com/footpatrol?key={{product_url}}&mode=Backend_PayPal
       ==> https://qt.polarcop.com/footpatrol?key=https://www.footpatrol.com/product/white-adidas-originals-x-424-sc-premiere/346956_footpatrolcom&mode=Backend_PayPal
```

**N.B.** 
 - If you do not have the full url you may also provide the url as follows: ` https://qt.polarcop.com/footpatrol?key=https://www.footpatrol.com/product/polarcop_com/{{product_id}}`
 - Supplying either `pid` or `key` is permitted at this time, for best practise we suggest following the guidelines as above.
 - Ensure you pass a frontend mode e.g `&mode=Backend` or `&mode=Backend_PayPal`
 
## Solebox
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ✅      | `pid`     | SID Only
| ✅      | `size`    | e.g `43` (EU Size Only)
| ❌      | `colour`  | 
| ❌      | `category`| 


```
[PATH]: ==> https://qt.polarcop.com/solebox

e.g https://www.solebox.com/en_GB/p/adidas_consortium-424_pro_model-bntora-01808119.html?chosen=size&dwvar_01808119_212=45%201%2F3

[SID]: ==> https://qt.polarcop.com/solebox?pid={{product_size_id}}
       ==> https://qt.polarcop.com/solebox?pid=dwvar_01808119_212=45%201%2F3

[URL]: ==> https://qt.polarcop.com/solebox?key={{product_id}}
       ==> https://qt.polarcop.com/solebox?key=01808119

[URL]: ==> https://qt.polarcop.com/solebox?key={{product_url}}
       ==> https://qt.polarcop.com/solebox?key=https://www.solebox.com/en_GB/p/adidas_consortium-424_pro_model-bntora-01808119.html
```

**N.B.** 
 - When providing a link for solebox, the region within the url is stripped and replaced according to the profile region. Therefore, providing region specific links is not required.
 - For sizing we will attempt to match the value from the available stock and user profile. E.g if the size `US10` restocked and the user profile is `United Kingdom` we will first check for sizes matching `UK10` if it's not available we will default to `US10`. For the safest option, please try and provide EU sizing.


## Supreme
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ❌      | `pid`     | 
| ✅      | `size`    | e.g `small`, `UK 5` or `US 5`
| ❌      | `colour`  | 
| ❌      | `category`| 


```
[PATH]: ==> https://qt.polarcop.com/supreme

e.g https://www.supremenewyork.com/shop/jackets/jji786yum/yn27h51l8

[URL]: ==> https://qt.polarcop.com/woodwood?key={{product_url}}
       ==> https://qt.polarcop.com/woodwood?key=https://www.supremenewyork.com/shop/jackets/jji786yum/yn27h51l8
```

## YeezySupply
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ✅      | `pid`     | PID Only
| ✅      | `size`    | e.g `11
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

## Notice
The documentation is accurate as of `Aug 6th 2020`, for further details please join our faq discord: https://discord.gg/3VNH4AE for more details, alternatively you can email our support email: support{@}polarcop.com
