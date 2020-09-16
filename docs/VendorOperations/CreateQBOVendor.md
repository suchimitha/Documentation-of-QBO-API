---
layout: default
title: Create Vendor
parent: Vendor Operations
nav_order: 2
---

# Create Vendor

## sample code 

To create a QuickBooks Online Vendor, pass the values to Accountwrapper and assign it to request.qboContacts and then call the method BreadwinnerAPI.call().

```scss
try{
	qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();	
	List<qboapi_g1.AccountWrapper> qboContactsList = new List<qboapi_g1.AccountWrapper>();
	qboapi_g1.AccountWrapper qboContact = new qboapi_g1.AccountWrapper();
	//qboContact.name='Test Vendor Name -'; 
	qboContact.DisplayName = 'Vendor full name';
    
    qboapi_g1.AccountWrapper.AddressWrapper adwrap = new qboapi_g1.AccountWrapper.AddressWrapper();
    adwrap.Line1 = '11-21-34/A';
    adwrap.City = 'hyderabad';
    adwrap.CountrySubDivisionCode = 'rangareddy';
    adwrap.PostalCode = '500087';
    adwrap.Country = 'India';
    qboContact.BillAddr = adwrap;
    qboContact.AccountId = '0012w0000092ngS';

	qboContactsList.add(qboContact);            
	req.qboContacts= qboContactsList;

	qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('createvendor', req);
	if(res.errors != null && res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
			System.debug(er); 
		}
	}
	system.debug('created Vendor' +res.Contacts);
}catch(Exception ex){
	System.debug('Exception occurred while creating customers in QuickBooks Online.'+ex.getStackTraceString());
}
```
