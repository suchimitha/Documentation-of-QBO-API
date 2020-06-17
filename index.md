---
layout: default
title: Home
nav_order: 1
description: "Breadwinner Xero API is hosted on GitHub Pages."
permalink: /
---

# Breadwinner API for QuickBooks Online
{: .fs-9 }


---

## Introduction
Breadwinner global API used to make request to QuickBooks Online. Request & responses are defined in such a way that you can make use of them and form the required things for the request and also to handle the response.

We have created two Handlers, one is for Request and another is for Response. They are named as RequestObject and ResponseObject respectively.

Currently, we are providing API to create, update and fetch QuickBooks Online Customers, Vendors from Salesforce to QuickBooks Online.

Breadwinner Provides Apex classes and methods. Users can use these, in their own custom Apex code to perform their needs. The following are the class and methods.

## BreadwinnerQBOAPI Class 
This is a global class where you can access RequestObject and ResponseObject.

### Namespace
"qboapi_g1" : Use this namespace to access <i>BreadwinnerQBOAPI</i> class and methods. 

## BreadwinnerQBOAPI Methods
The following are instance methods for <i>BreadwinnerQBOAPI</i>.
- <b>Call()</b><br/>
This is a global method which will return a list of Customers or Invoices in the form of [BreadwinnerQBOAPI.ResponseObject]({{ site.baseurl }}{% link docs/response.md %}). It takes two parameters.

> 1. <b>Action</b>: Used to define the type of action that needs to be performed.<br/>
E.g : createContact, createVendor,… see [List of actions]({{ site.baseurl }}{% link docs/configuration.md %})

>  2. <b>Request</b>: An instance of [RequestObject]({{ site.baseurl }}{% link docs/configuration.md %}) is accepted.<br/>
E.g :  BreadwinnerQBOAPI.RequestObject request = new BreadwinnerQBOAPI.RequestObject();

Note: This is a synchronous method, it will make http callouts. So, to access "BreadwinnerQBOAPI.Call()" method please enable callouts by annotating the future method, or use Queueable Apex.<br/>
eg: @Future(callout=true) 
### Signature
BreadwinnerQBOAPI.ResponseObject call(String Action, BreadwinnerQBOAPI.RequestObject request)

### BreadwinnerQBOAPI inner classes

> - RequestObject - Class
> - ResponseObject - Class





---
