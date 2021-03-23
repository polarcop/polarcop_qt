![](https://github.com/polarcop/polarcop_qt/blob/master/polarcop_qt.png)

## Usage
This version of quick tasks supports builds from `1.0.33` onwards and supports both `QT`(Quick Tasks) and `PT` (Premade Tasks).

Polar Cop QT allows anyone to quickly create and start tasks for Polar Cop's iOS platform. 

**For integration help, please contact us via email support@polarcop.com or live chat: https://polarcop.com**

### Supported Sites
- [Asos](#asos)
- [Footlocker](#footlockereu)
- [Mesh Frontend](#meshfe)
- [Mesh Backend](#meshbe)
- [Solebox](#solebox)
- [Supreme](#supreme)
- [Sivasdescalzo](#svd)
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
| KEY                  | Sites Supported?                                               |
|----------------------|----------------------------------------------------------------|
| `Request`            | `supreme`, `svd`, `footlocker`                                 |
| `Safe_Request`       | `supreme`                                                      |
| `Fast_Safe`          | `supreme`                                                      |
| `Browser`            | `yeezysupply`                                                  |
| `Safe_PayPal`        | `solebox`                                                      |
| `Safe_Backend`       | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Safe_Backend_PayPal`| `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Backend`            | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Backend_PayPal`     | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Backend_2`          | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Backend_2_PayPal`   | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Frontend`           | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Frontend_PayPal`    | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Frontend_2`         | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Frontend_2_PayPal`  | `footpatrol`, `size`, `jdsports`, `thehipstore`                |
| `Cart`               |  `asos`                                                        |
| `Fast_Cart`          |  `asos`                                                        |

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

[URL]: ==> https://qt.polarcop.com/asos?key={{product_url}}
       ==> https://qt.polarcop.com/asos?key=https://www.asos.com/polar/cop/prd/20291607
       ==> https://qt.polarcop.com/asos?key=https://www.asos.com/dk/fred-perry/fred-perry-embroidered-logo-t-shirt-in-black/prd/20291607
```
**N.B** Where possible specify the region in URL, see third url example (`?key=https://www.asos.com/dk/....`)

## FootlockerEU
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ✅      | `pid`     | PID Only
| ✅      | `size`    | e.g `35`(OLD) or `US 5` (NEW)
| ❌      | `colour`  | 
| ❌      | `category`| 

```
[PATH]: ==> https://qt.polarcop.com/footlockereu

e.g https://www.footlocker.co.uk/en/p/nike-tuned-1-men-shoes-104419?v=314206086804

[PID]: ==> https://qt.polarcop.com/footlockereu?pid={{product_id}}
       ==> https://qt.polarcop.com/footlockereu?pid=314206086804

[URL]: ==> https://qt.polarcop.com/footlockereu?key={{product_url}}
       ==> https://qt.polarcop.com/footlockereu?key=https://www.footlocker.co.uk/en/p/nike-tuned-1-men-shoes-104419?v=314206086804
```
**N.B** Region is inferred by profile, so does not required to be set. Also ensure you **provide a SKU** and **not the size PID**

## MeshFE
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | PID / URL
| ✅      | `pid`     | Variant ID Only
| ✅      | `size`    | e.g `11`
| ❌      | `colour`  | 
| ❌      | `category`| 
| ✅      | `mode`    | `Frontend`, `Frontend_PayPal`, `Frontend_2`, `Frontend_2_PayPal`

**STORES**:
`footpatrol`, `size`, `jdsports` and `thehipstore`
```
[PATH]: ==> https://qt.polarcop.com/footpatrol
        ==> https://qt.polarcop.com/size
        ==> https://qt.polarcop.com/jdsports
        ==> https://qt.polarcop.com/thehipstore

e.g https://www.footpatrol.com/product/white-adidas-originals-x-424-sc-premiere/346956_footpatrolcom/

[SID]: ==> https://qt.polarcop.com/footpatrol?pid={{product_variant_id}}&mode=Frontend
       ==> https://qt.polarcop.com/footpatrol?pid=346951_footpatrolcom.001469792&mode=Frontend

[PID]: ==> https://qt.polarcop.com/footpatrol?key={{product_id}}&mode=Frontend
       ==> https://qt.polarcop.com/footpatrol?key=346956_footpatrolcom&mode=Frontend

[URL]: ==> https://qt.polarcop.com/footpatrol?key={{product_url}}&mode=Frontend
       ==> https://qt.polarcop.com/footpatrol?key=https://www.footpatrol.com/product/white-adidas-originals-x-424-sc-premiere/346956_footpatrolcom&mode=Frontend
```

**N.B.** 
 - If you do not have the full url you may also provide the url as follows: ` https://qt.polarcop.com/footpatrol?key=https://www.footpatrol.com/product/polarcop_com/{{product_id}}`
 - Supplying either `pid` or `key` is permitted at this time, for best practise we suggest following the guidelines as above.
 - Ensure you pass a frontend mode e.g `&mode=Frontend`
 
 ## MeshBE
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | PID / URL
| ✅      | `pid`     | Variant ID Only
| ✅      | `size`    | e.g `11`
| ❌      | `colour`  | 
| ❌      | `category`| 
| ✅      | `mode`    | `Safe_Backend`, `Safe_Backend_PayPal`, `Backend`, `Backend_PayPal`, `Backend_2`, `Backend_2_PayPal`

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
| ❌      | `key`     | 
| ✅      | `pid`     | STYLE ID ONLY
| ✅      | `size`    | e.g `small`, `UK 5` or `US 5`
| ✅      | `colour`  | 
| ✅       | `category`| 


```
[PATH]: ==> https://qt.polarcop.com/supreme

e.g https://www.supremenewyork.com/mobile#products/305798

[URL]: ==> https://qt.polarcop.com/supreme?key=305798
       ==> https://qt.polarcop.com/supreme?key=305798&size=medium
       ==> https://qt.polarcop.com/supreme?key=305798&colour=navy
       ==> https://qt.polarcop.com/supreme?key=305798&size=medium&colour=navy

[KEY]: ==> https://qt.polarcop.com/supreme?key=tagless&category=Accessories
       ==> https://qt.polarcop.com/supreme?key=tagless&category=Accessories&size=medium
       ==> https://qt.polarcop.com/supreme?key=tagless&category=Accessories&colour=white
       ==> https://qt.polarcop.com/supreme?key=tagless&category=Accessories&size=medium&colour=white
```

## SVD
| Allowed | Parameter | Notes
|---------|-----------|-----------
| ✅      | `key`     | URL Only
| ❌      | `pid`     | 
| ✅      | `size`    | e.g `M`, `US 5`
| ❌      | `colour`  | 
| ❌      | `category`| 


```
[PATH]: ==> https://qt.polarcop.com/svd

e.g https://www.sivasdescalzo.com/en/stance-crew-sock-x-billie-eilish-u558b19gri-ye2

[URL]: ==> https://qt.polarcop.com/svd?key={{product_url}}
       ==> https://qt.polarcop.com/svd?key=https://www.sivasdescalzo.com/en/stance-crew-sock-x-billie-eilish-u558b19gri-ye2
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
The documentation is accurate as of `Mar 23rd 2021`, for further details please join our faq discord: https://discord.gg/3VNH4AE for more details, alternatively you can email our support email: support{@}polarcop.com
