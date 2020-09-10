---
layout: default
title: Response
nav_order: 2
---

# Response
{: .no_toc }

This method allows users to retrieve the data of a Quickbooks online Contact/Vendor/Invoice/Bill/PurchaseOrder.


### Response
As mentioned earlier, the Response will be returned in the form of Map<String, Object>.


Below are the list of Keys or Parameters returned in the Response Map:

|Key (String)|Value (Object)|Additional Detail|
|:-----------|:-------------|:----------------|
|version|1.0’ |Returns the same version sent in the Request|
|action|See the list of available actions.|Returns the same action sent in the Request.|
|timestamp|Timestamp in milliseconds (Unix).|The time at which the Response was returned, can be used to troubleshoot.|
|validRequest|Either true or false.|If the Request satisfies the Breadwinner validations, it will be returned as true.|
|apiErrors|This will be a list of Errors returned as JSON.|Errors which Breadwinner gets while validating the request and before making the request to NetSuite.|
|responseJSON|Returns the response of the record(s) as a JSON string.|This includes the records data as well as the NetSuite Errors.Click here to see the examples.|






### Errors
There can be some exceptions within Breadwinner and QuickBooks Online may throw some errors as part of our API actions and those errors are returned in separate layers in the form of JSON.

## Before requesting QuickBooks Online
Errors occurred while validating the request, or while making a request to QuickBooks Online are returned as ‘apiErrors’, when these exceptions are there validRequest key will be sent as false.

These errors are returned as ‘apiErrors’ as a key of the Response map, and apiErrors is a list of Error objects. 

## After requesting QuickBooks Online
Errors occurred within QuickBooks Online while processing the request, or while processing the data in Breadwinner are sent as ‘errors’ in the responseJSON key of the Response map.

These errors are returned as ‘errors’  in the responseJSON which is a key of the Response map, and errors is a list of Error objects. 

## Error Object
Error object contains two String parameters


|Field Name|Data Type|Description|
|:---------|:--------|:----------|
|type | String |Code is a short form or type of the Error occurred. Example: INVALID_ACTION|
|message | String |A detailed explanation of the Error occurred. Example: Breadwinner was unable to process the request as the action parameter was invalid.|
|code | String | For some errors that could be handled programmatically, a short string indicating the error code reported.|
|Detail | String | Represents the extra info regarding the error or exception.|
