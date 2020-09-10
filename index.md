---
layout: default
title: Home
nav_order: 1
description: "Breadwinner QuickBooks Online API is hosted on GitHub Pages."
permalink: /
---

# Breadwinner API for QuickBooks Online
{: .fs-9 }


---

## Introduction


Breadwinner for NetSuite Global API is part of the Breadwinner for Netsuite managed package. A Global class is exposed as an API to allow our Breadwinner for NetSuite customers to make calls to NetSuite via Breadwinner, in addition to the Breadwinner’s functionality.

## BreadwinnerQBOAPI Class 
BreadwinnerQBOAPI is a global class that can be used to make requests to QuickBooks via Breadwinner. As it is a part of the managed package, you must prepend the namespace "qboapi_g1"


## Methods

A method call(Map<String, Object> request) is a static global method within the BreadwinnerQBOAPI class, which can be used to make an API request.

```yaml

qboapi_g1.BreadwinnerQBOAPI.call(Map<String, Object> request);

```

Breadwinner accepts the request data in the form of Map<String, Object>, and even returns the response data as a  Map<String, Object>, thus making the requests and responses dynamic.

For more information, please refer to the Sample [Requests](https://dev-qbo.breadwinner.com/docs/configuration/) and [Responses](https://dev-qbo.breadwinner.com/docs/response/) section.

Note: This is a synchronous method, it will make http callouts. So, to access "BreadwinnerQBOAPI.Call()" method please enable callouts by annotating the future method, or use Queueable Apex.<br/>
eg: @Future(callout=true) 
### Signature
BreadwinnerQBOAPI.ResponseObject call(String Action, BreadwinnerQBOAPI.RequestObject request)

### BreadwinnerQBOAPI inner classes

> - RequestObject - Class
> - ResponseObject - Class





---
