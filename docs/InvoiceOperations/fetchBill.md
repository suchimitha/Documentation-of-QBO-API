---
layout: default
title: Fetch Bills
parent: Invoice Operations
nav_order: 6
---
# Fetch Bills

To get/fetch the Bills, pass the parameters to request.options variable and then call the method BreadwinnerQBOAPI.call(). This method returns a list of Invoice wrapper records (Invoices).

## Sample Code

Optional parameters to fetch Bill(s):
invoiceID, invoiceNumber, where, orderBy, pageNumber, modifiedAfter.

```scss
try{
    qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();
    //req.options.put('invoicenumber','INV-0041');
    req.options.put('pagenumber','1');

    qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('fetchBills', req);
    if(res.errors.size()>0){
        for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
            System.debug(er); 
        }
    }
    system.debug('Bills '+res.Invoices);
}catch(Exception ex){
    System.debug('Exception occurred while creating customers in Stripe.'+ex.getStackTraceString());
}
```