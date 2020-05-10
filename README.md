![](https://github.com/polarcop/polarcop_qt/blob/master/polarcop_qt.png)

## Usage
This version of quick tasks supports builds from `1.0.16` onwards and supports both `QT`(Quick Tasks) and `PT` (Premade Tasks)

Polar Cop quick tasks allows anyone to quickly create and start tasks for Polar Cop's iOS platform. 

### Supported Sites
- [Yeezy Supply](#yeezysupply)

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

**QT:**
```
[FORMAT]: ==> https://qt.polarcop.com/yeezysupply?pid={{product_id}}

e.g https://www.yeezysupply.com/product/FW6345 

[PID]: ==> https://qt.polarcop.com/yeezysupply?pid={{product_id}}
       ==> https://qt.polarcop.com/yeezysupply?pid=FW6345

[URL]: ==> https://qt.polarcop.com/yeezysupply?key={{product_url}}
       ==> https://qt.polarcop.com/yeezysupply?key=https://www.yeezysupply.com/product/FW6345
```

### Notice
The documentation is accurate as of `May 10th 2020`, for further details please join our faq discord: https://discord.gg/3VNH4AE for more details, alternatively you can email our support email: support{@}polarcop.com
