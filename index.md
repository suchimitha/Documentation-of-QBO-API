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
Breadwinner global API is used to communicate with QuickBooks Online via Breadwinner/Salesforce. Requests & Responses are defined in such a way that you can make use of them and form the required things as per the request and get the response.

We have created two Handlers, one is for Request, and another is for Response. They are named as RequestObject and ResponseObject respectively, which are inner classes of BreadwinnerQBOAPI.

Currently, we are providing API to create, update, and fetch operations for QuickBooks Online Contacts, Invoices, Bills, and Purchase Orders from Salesforce to QuickBooks Online.

Breadwinner exposes their global apex classes and methods, which can be used in the custom Apex code and design your flow. 

The following are the class and methods.

## BreadwinnerQBOAPI Class 
This is a global class where you can access RequestObject and ResponseObject.

### Namespace
"bw_qbo_api02": Use this namespace to access <i>BreadwinnerQBOAPI's</i> classes and methods. All methods are static.

## BreadwinnerQBOAPI Methods
The following are methods for <i>BreadwinnerQBOAPI</i>.
- <b>call(action, request)</b><br/>
This is a global method which will return list of Customers or Invoices in the form of [BreadwinnerQBOAPI.ResponseObject](https://dev-QuickBooksOnline.breadwinner.com/docs/response/).

### Signature
BreadwinnerQBOAPI.ResponseObject call(String action, BreadwinnerQBOAPI.RequestObject request)

### Parameters
>  - <b>Action</b>: Used to define the type of action that needs to be performed.<br/>
Type: String<br/>
E.g: createCustomer, createInvoice,… see [List of available actions](https://dev-QuickBooksOnline.breadwinner.com/docs/configuration/).

>  - <b>Request</b>: An instance of [RequestObject](https://dev-QuickBooksOnline.breadwinner.com/docs/configuration/).<br/>
Type: BreadwinnerQBOAPI.RequestObject<br/>
E.g:  BreadwinnerQBOAPI.RequestObject request = new BreadwinnerQBOAPI.RequestObject();

### Return Value
Type: [BreadwinnerQBOAPI.ResponseObject](https://dev-QuickBooksOnline.breadwinner.com/docs/response/)

### Usage
This is an synchronous method, it will make Http callouts. So, while invoking this method from a Future method, please set callout to True in the Future Annotation.<br/>
E.g: @Future(callout=true)

### BreadwinnerQBOAPI inner classes

> - RequestObject - Class
> - ResponseObject - Class





---
