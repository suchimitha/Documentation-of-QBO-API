---
layout: default
title: Create Invoice
parent: Invoice Operations
nav_order: 1
---

# Create Invoice

## Sample Code


To create an Invoice, pass the values to Invoice wrapper and assign it to request.qboInvoices and then call the method BreadwinnerQBOAPI.call(). Here customer ClientId (QuickBooks Online Contact Id) is required.

```scss
try{
	qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();	
	List<qboapi_g1.Invoice> qboInvoicesList = new List<qboapi_g1.Invoice>();
	qboapi_g1.Invoice qboInvoice = new qboapi_g1.Invoice ();
	qboContacts.InvoiceNumber = 'inv-123';
	qboContacts.DueDate = string.valueof(system.today());
	qboapi_g1.Invoice.LineItemWrapper invoiceLineItem = new qboapi_g1.Invoice.LineItemWrapper();
	invoiceLineItem.ItemCode = 'xc-123'; 
	invoiceLineItem.Description ='li desc'; 
	invoiceLineItem.AccountCode = '200';
	invoiceLineItem.UnitAmount = 300;
	invoiceLineItem.Quantity = 3;
	list<qboapi_g1.Invoice.LineItemWrapper> invoiceLineItemsList = new list<qboapi_g1.Invoice.LineItemWrapper>();
	invoiceLineItemsList.add(invoiceLineItem);
	qboContacts.LineItems = invoiceLineItemsList;
	qboContacts.ClientId = '39efa556-8dda-4c81-83d3-a631e59eb6d3';
	qboInvoicesList.add(qboInvoice);
	req.qboInvoices = qboInvoicesList;
	qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('createInvoice', req);
	if(res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
			System.debug(er); 
		}
	}
	system.debug('created Invoice' +res.Invoices );
}catch(Exception ex){
	System.debug('Exception occurred while creating customers in QuickBooks Online.'+ex.getStackTraceString());
}
```