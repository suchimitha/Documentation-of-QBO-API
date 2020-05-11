---
layout: default
title: Update Purchase Order
parent: Invoice Operations
nav_order: 8
---

# Update Purchase Order

To update purchase Order pass the values to Invoice wrapper along with PurchaseorderId (QuickBooks Online identifier) and assign it to request.qboInvoices and then call the method BreadwinnerQBOAPI.call().

## Sample Code

```scss
try{
    qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();
    List<qboapi_g1.Invoice> qboInvoicesList = new List<qboapi_g1.Invoice>();
    qboapi_g1.Invoice qboInvoice = new qboapi_g1.Invoice ();
    qboContacts.PurchaseorderId = '5eac31f6-a05f-4a84-b3aa-47154c82afca'; // Required
    qboContacts.DueDate = string.valueof(system.today()+30);
    qboapi_g1.Invoice.LineItemWrapper poLineItem = new qboapi_g1.Invoice.LineItemWrapper();
    poLineItem.ItemCode = ''; 
    poLineItem.Description = 'li desc';
    poLineItem.UnitAmount = 500;
    poLineItem.Quantity = 3;
    poLineItem.AccountCode = '200';
    list<qboapi_g1.Invoice.LineItemWrapper> poLineItemsList = new list<qboapi_g1.Invoice.LineItemWrapper>();
    poLineItemsList.add(poLineItem);
    qboContacts.LineItems = poLineItemsList;
    qboContacts.ClientId = '39efa556-8dda-4c81-83d3-a631e59eb6d3';
    qboInvoicesList.add(qboInvoice);
    req.qboInvoices = qboInvoicesList;


    qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('updatePurchaseOrder', req);
    if(res.errors.size()>0){
        for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
            System.debug(er); 
        }
    }
    system.debug('Updated PO' +res.Invoices);
}catch(Exception ex){
    System.debug('Exception occurred while creating customers in Stripe.'+ex.getStackTraceString());
}
```