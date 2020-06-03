---
layout: default
title: Create Customer
parent: Contact Operations
nav_order: 1
---

# Create Customer

## sample code 

To create a QuickBooks Online Customer, pass the values to Accountwrapper and assign it to request.qboContacts and then call the method BreadwinnerAPI.call().

```scss
try{
	qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();	
	List<qboapi_g1.AccountWrapper> xeroContactsList = new List<qboapi_g1.AccountWrapper>();
	qboapi_g1.AccountWrapper xeroContact = new qboapi_g1.AccountWrapper();
	xeroContact.name='Test Customer -'; 
	xeroContact.DisplayName = 'Customer full name';
    
    qboapi_g1.AccountWrapper.AddressWrapper adwrap = new qboapi_g1.AccountWrapper.AddressWrapper();
    adwrap.Line1 = '11-21-34/A';
    adwrap.City = 'hyderabad';
    adwrap.CountrySubDivisionCode = 'rangareddy';
    adwrap.PostalCode = '500087';
    adwrap.Country = 'India';
    xeroContact.BillAddr = adwrap;
    BreadwinnerUtil.SfAccountId = '0012w0000092ngS';

	xeroContactsList.add(xeroContact);            
	req.qboContacts= xeroContactsList;

	qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('createcustomer', req);
	if(res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
			System.debug(er); 
		}
	}
	system.debug('created customer' +res.Contacts);
}catch(Exception ex){
	System.debug('Exception occurred while creating customers in Xero.'+ex.getStackTraceString());
}
```
