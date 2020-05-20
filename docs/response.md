---
layout: default
title: Response
nav_order: 2
---

# Response
{: .no_toc }

This method allows users to retrieve the data of a Quickbooks online Contact/Vendor/Invoice/Bill/PurchaseOrder.


### ResponseObject - Class
When we call “BreadwinnerQBOAPI.call()” method, User would get the response in the form of BreadwinnerQBOAPI.ResponseObject. It consists of the following variables.<br/>

### Status: 
It is of type String, which represents the Response/Status code of the request returned by QuickBooks Online. <br/>
E.g: ‘200’ - OK (Successful API call) <br/>
Click [here](https://developer.qbo.com/documentation/api/http-response-codes) for more Status codes, and it's descriptions.

### Contacts
It is of type List<AccountWrapper>, which contains the created QuickBooks Online Contact(s) data along with QuickBooks Online unique record Id.<br/> 
```yaml
List<qboapi_g1.AccountWrapper> qboContactsList = Response.Contacts
```

### Invoices
It is of type List<Invoice>, which contains the created QuickBooks Online Invoice(s) data along with QuickBooks Online unique record Id.<br/>
```yaml
List<qboapi_g1.Invoice> qboInvoices = Response.Invoices
```

### Errors
It is of type “BreadwinnerQBOAPI.Error” class. All the Errors that are reported by QuickBooks Online or by Salesforce.

Error class contains the following variables:
<ul>
<li><b>type</b>: The type of error returned. One of api_connection_error, api_error, authentication_error, idempotency_error, invalid_request_error, rate_limit_error, validation_exception. e.t.c.,</li>
<li><b>message</b>: Represents the Error.</li>
<li><b>code</b>: For some errors that could be handled programmatically, a short string indicating the error code reported.</li>
<li><b>Detail</b>: Represents the extra info regarding the error or exception.</li>
</ul>

```yaml
message=REQUIRED_FIELD_MISSING: name, message=Enter the QuickBooks Online customer name. param=qboContacts[0].name
```