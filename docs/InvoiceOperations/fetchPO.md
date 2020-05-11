---
layout: default
title: Fetch Purchase Orders
parent: Invoice Operations
nav_order: 9
---

# Fetch Purchase Orders

To get/fetch the Purchase Orders, pass the parameters to request.options variable and then call the method BreadwinnerQBOAPI.call(). This method returns a list of Invoice wrapper records (Invoices).

## Sample Code

Optional parameters to fetch Purchase Order(s):
purchaseOrderID, purchaseOrderNumber, where, orderBy, pageNumber, modifiedAfter.


```scss
try{
    qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();
    req.options.put('page','1');

    qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('fetchPurchaseOrders', req);
    if(res.errors.size()>0){
        for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
            System.debug(er); 
        }
    }
    system.debug('Purchase Orders '+res.Invoices);
}catch(Exception ex){
    System.debug('Exception occurred while creating customers in Stripe.'+ex.getStackTraceString());
}
```