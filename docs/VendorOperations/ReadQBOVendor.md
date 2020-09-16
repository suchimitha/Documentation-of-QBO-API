---
layout: default
title: Read Vendor
parent: Vendor Operations
nav_order: 1
---

# Read Vendor

This is under development.



To get/fetch, the QuickBooks Online Vendor passes the parameters to request.Options variable and then calls the method BreadwinnerAPI.call(). Returns a map of AccountWrapper records. 
It developed to allow only 'vendor_id' (QuickBooks Online Unique Id).

## sample code 

Optional parameters to fetch QuickBooks Vendor(s):

```scss
try{
    qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();   
    req.options.put('vendor_id','84');

    qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('fetchVendor', req);
    if(res.errors!=null && res.errors.size()>0){
        for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
            System.debug(er); 
        }
    }
    else{
        system.debug(' Vendors ' +res.Contacts);
    }
}catch(Exception ex){
    System.debug('Exception occurred while fetching Vendors from QuickBooksOnline.'+ex.getStackTraceString());
}
```