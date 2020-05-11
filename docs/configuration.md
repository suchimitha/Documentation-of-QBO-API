---
layout: default
title: Request
nav_order: 2
---

# Request
{: .no_toc }


## Actions
It is a type of string used to define the type of action that needs to be performed. It generally accepts the following types of actions.

<ul>

<li><b>createContact</b>: Creates a QuickBooks Online Contact.</li>
<li><b>updateContact</b>: Updates a QuickBooks Online Contact.</li>
<li><b>fetchContacts</b>: Fetches a single QuickBooks Online Contact or a list of QuickBooks Online Contacts from QuickBooks Online.</li>
<li><b>createVendor</b>: Creates a QuickBooks Online Vendor.</li>
<li><b>updateVendort</b>: Updates a QuickBooks Online Vendor.</li>
<li><b>fetchVendor</b>: Fetches a single QuickBooks Online Vendor or a list of QuickBooks Online Vendors from QuickBooks Online.</li>
<li><b>createInvoice</b>: Creates an Invoice in QuickBooks Online.</li>
<li><b>updateInvoice</b>: Updates in Invoice in QuickBooks Online.</li>
<li><b>fetchInvoices</b>: Fetches either a single Invoice or list of Invoices from QuickBooks Online.</li>
<li><b>createBill</b>: Creates a Bill in QuickBooks Online.</li>
<li><b>updateBill</b>: Updates a Bill in QuickBooks Online.</li>
<li><b>fetchBills</b>: Fetches either a single Bill or list of Bills from QuickBooks Online.</li>
<li><b>createPurchaseOrder</b>: Creates a Purchase Order (PO) in QuickBooks Online.</li>
<li><b>updatePurchaseOrder</b>: Updates a Purchase Order (PO) in QuickBooks Online.</li>
<li><b>fetchPurchaseOrders</b>: Fetches either a single Purchase Order or a list of Purchase Orders from QuickBooks Online.</li>

</ul>

## RequestObject - Class
You have to create an Instance for RequestObject and pass to the "BreadwinnerQBOAPI.call()” method as one of the parameters. <br/>
```yaml
BreadwinnerQBOAPI.RequestObject request = new BreadwinnerQBOAPI.RequestObject(); 
```

It consists of the following variables:

### 1. qboContacts
It is an instance of the AccountWrapper (QuickBooks online Contact Wrapper) class. To Create/Insert a QuickBooks Online Contact, we should pass the desired values to the respective variables. For available qboContacts variables, please refer [here](https://dev-qboContacts.breadwinner.com/docs/CustomerOperations) <br/>
It is of type List. but for now we are accepting only one record.

```yaml
    List<qboapi_g1.BreadwinnerQBOAPI.AccountWrapper> qboContactList = new list<qboapi_g1.BreadwinnerQBOAPI.AccountWrapper>();
    qboapi_g1.BreadwinnerQBOAPI.AccountWrapper qboContact = new qboapi_g1.BreadwinnerQBOAPI.AccountWrapper();
    qboContact.name = 'Test Customer';
    qboContactList.add(qboContact);
    request.qboContacts = qboContactList;
```

### 2. qboInvoices
It is an instance of the Invoicewrapper class. To Create/Insert Invoice we should pass desired values to variables. For all Invoice variables you can refer [here](https://dev-qbo.breadwinner.com/docs/InvoiceOperations) <br/>
It is of type List. but for now we are accepting only one record.

```yaml
    List<qboapi_g1.BreadwinnerQBOAPI.Invoice> qboInvoiceList = new list<qboapi_g1.BreadwinnerQBOAPI.Invoice>();
    qboapi_g1.BreadwinnerQBOAPI.Invoice qboInvoice = new qboapi_g1.BreadwinnerQBOAPI.Invoice();
    qboInvoice.CustomerId = 'Test Customer'; 
    qboInvoice.description = 'desc';… 
    qboInvoiceList.add(qboInvoice);
    request.qboInvoice = qboInvoiceList;
```

### 3. options 
It is a collection of type Map (Map<String, Object>), used to pass any type of filters that to be passed in the request or any config settings that we enable.
below are the options can be used while fetching records. <br/>
    
> <b>Contacts</b>: ContactId, ContactNumber, where, PageNumber, ModifiedAfter <br/>
> <b>Invoices, Bills</b>: InvoiceNumber, InvoiceId, where, PageNumber, ModifiedAfter <br/>
> <b>PurchaseOrders</b>: PurchaseOrderNumber, PurchaseOrderID, where, PageNumber, ModifiedAfter <br/>

```yaml
request.options.put('PageNumber','1');
```
