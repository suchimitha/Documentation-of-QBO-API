---
layout: default
title: Fetch QuickBooks Online Contacts
parent: Contact Operations
nav_order: 3
---

# Fetch QuickBooks Online Contacts

To get/fetch, the QuickBooks Online Contact pass the parameters to request.Options variable and then call the method BreadwinnerQBOAPI.call(). Returns a map of AccountWrapper records (QuickBooksOnlineIdCustomerMap). 

## sample code 

Optional parameters to fetch QuickBooks Online Contact(s):
ContactId, ContactNumber, where, orderby, pagenumber, modifiedafter.

```scss
try{
    qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();
    req.options.put('pagenumber','1');

    qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('fetchContacts', req);
        if(res.errors.size()>0){
            for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
                System.debug(er); 
            }
        }
        else{
            system.debug('created customer' +res.qboContacts);
        }
}catch(Exception ex){
    System.debug('Exception occurred while creating customers in Stripe.'+ex.getStackTraceString());
}
```