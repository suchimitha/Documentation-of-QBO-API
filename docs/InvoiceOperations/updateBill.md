---
layout: default
title: Update Bill
parent: Invoice Operations
nav_order: 5
---

# Update Bill

To update Bill pass the values to Invoice wrapper along with InvoiceId (QuickBooks Online identifier) and assign it to request.qboInvoices and then call the method BreadwinnerQBOAPI.call().

## Sample Code

```scss
try{
    qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();
   	List<qboapi_g1.Invoice> qboInvoicesList = new List<qboapi_g1.Invoice>();
    qboapi_g1.Invoice qboInvoice = new qboapi_g1.Invoice ();
    qboContacts.InvoiceID = '5eac31f6-a05f-4a84-b3aa-47154c82afca'; // Required
    qboContacts.DueDate = string.valueof(system.today()+30);
    qboapi_g1.Invoice.LineItemWrapper billLineItem = new qboapi_g1.Invoice.LineItemWrapper();
    billLineItem.ItemCode = ''; 
    billLineItem.Description ='li desc';
    billLineItem.UnitAmount = 500;
    billLineItem.Quantity = 3;
    billLineItem.AccountCode = '200';
    list<qboapi_g1.Invoice.LineItemWrapper> billLineItemsList = new list<qboapi_g1.Invoice.LineItemWrapper>();
    billLineItemsList.add(billLineItem);
    qboContacts.LineItems = billLineItemsList;
    qboContacts.ClientId = '39efa556-8dda-4c81-83d3-a631e59eb6d3';
   	qboInvoicesList.add(qboInvoice);
    req.qboInvoices = qboInvoicesList;


    qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('updateBill', req);
    if(res.errors.size()>0){
        for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
            System.debug(er); 
        }
    }
    system.debug('Updated Bill' +res.Invoices);
}catch(Exception ex){
    System.debug('Exception occurred while creating customers in Stripe.'+ex.getStackTraceString());
}
```