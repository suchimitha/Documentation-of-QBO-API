---
layout: default
title: Update Vendor
parent: Contact Operations
nav_order: 8
---

# Update Vendor

To Update a QuickBooks Online Customer pass the values to Accountwrapper along with contactId (QuickBooks Online identifier) and assign it to request.qboContacts and then call the method BreadwinnerQBOAPI.call().

## sample code 

```scss
try{
	qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();	
	List<qboapi_g1.AccountWrapper> xeroContactsList = new List<qboapi_g1.AccountWrapper>();
	qboapi_g1.AccountWrapper xeroContact = new qboapi_g1.AccountWrapper();
	//xeroContact.name='Test Vendor Name -'; 
	xeroContact.DisplayName = 'Vendor full name updated';
    
    qboapi_g1.AccountWrapper.AddressWrapper adwrap = new qboapi_g1.AccountWrapper.AddressWrapper();
    adwrap.Line1 = '11-21-34/A';
    adwrap.City = 'hyderabad';
    adwrap.CountrySubDivisionCode = 'rangareddy';
    adwrap.PostalCode = '500087';
    adwrap.Country = 'India';
    xeroContact.BillAddr = adwrap;
	xeroContact.id = '85';

	xeroContactsList.add(xeroContact);            
	req.qboContacts= xeroContactsList;

	qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('updatevendor', req);
	if(res.errors != null && res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
			System.debug(er); 
		}
	}
	system.debug('updated vendor' +res.Contacts);
}catch(Exception ex){
	System.debug('Exception occurred while updating Vendor in QuickBooks Online.'+ex.getStackTraceString());
}
```