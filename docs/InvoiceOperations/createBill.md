---
layout: default
title: Create Bill
parent: Invoice Operations
nav_order: 4
---

# Create Bill

To create Bill, pass the values to Invoice wrapper and assign it to request.qboInvoices and then call the method BreadwinnerQBOAPI.call(). Here customer ClientId (QuickBooks Online Contact Id) is required. 


## Sample Code

```scss
try{
	qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();	
	List<qboapi_g1.Invoice> qboInvoicesList = new List<qboapi_g1.Invoice>();
	qboapi_g1.Invoice qboInvoice = new qboapi_g1.Invoice ();
	qboContacts.DueDate = string.valueof(system.today());
	qboapi_g1.Invoice.LineItemWrapper billLineItem = new qboapi_g1.Invoice.LineItemWrapper();
	billLineItem.ItemCode = 'Xmin-123'; 
	billLineItem.Description = 'li desc'; 
	billLineItem.AccountCode = '200';
	billLineItem.UnitAmount = 300;
	billLineItem.Quantity = 3;
	list<qboapi_g1.Invoice.LineItemWrapper> billLineItemsList = new list<qboapi_g1.Invoice.LineItemWrapper>();
	billLineItemsList.add(billLineItem);
	qboContacts.LineItems = billLineItemsList;
	qboContacts.ClientId = '39efa556-8dda-4c81-83d3-a631e59eb6d3';
	qboInvoicesList.add(qboInvoice);
	req.qboInvoices = qboInvoicesList;
	qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('createBill', req);
	if(res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
			System.debug(er); 
		}
	}
	system.debug('created Bill' +res.Invoices);
}catch(Exception ex){
	System.debug('Exception occurred while creating customers in QuickBooks Online.'+ex.getStackTraceString());
}
```