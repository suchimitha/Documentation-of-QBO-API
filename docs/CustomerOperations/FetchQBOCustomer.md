---
layout: default
title: Fetch Customer
parent: Customer Operations
nav_order: 3
---

# Fetch Customer

This is under development.


To get/fetch, the QuickBooks Online Customer passes the parameters to request.Options variable and then calls the method BreadwinnerAPI.call(). Returns a map of AccountWrapper records. 
It developed to allow only 'customer_id' (QuickBooks Online Unique Id).

## sample code 

Optional parameters to fetch QuickBooks Customer(s):

```scss
try{
    qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();   
    req.options.put('customer_id','84');

    qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('fetchcustomer', req);
    if(res.errors!=null && Sres.errors.size()>0){
        for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
            System.debug(er); 
        }
    }
    else{
        system.debug(' Customers ' +res.Contacts);
    }
}catch(Exception ex){
    System.debug('Exception occurred while fetching customers from QuickBooksOnline.'+ex.getStackTraceString());
}
```