---
layout: default
title: Update Customer
parent: Contact Operations
nav_order: 2
---

# Update Customer


To Update a QuickBooks Online Customer pass the values to Accountwrapper along with contactId (QuickBooks Online identifier) and assign it to request.qboContacts and then call the method BreadwinnerQBOAPI.call().

## sample code 

```scss
try{
	qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();	
	List<qboapi_g1.AccountWrapper> xeroContactsList = new List<qboapi_g1.AccountWrapper>();
	qboapi_g1.AccountWrapper xeroContact = new qboapi_g1.AccountWrapper();
	xeroContact.name=' Contact name -'; 
	xeroContact.DisplayName = 'Customer full name updated';
    xeroContact.id='84';// is QuickbooksOnline Unique Contact Id
    
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

	qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('updatecustomer', req);
	if(res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
			System.debug(er); 
		}
	}
	system.debug('created customer' +res.Contacts);
}catch(Exception ex){
	System.debug('Exception occurred updating Customer in QuickBooks Online.'+ex.getStackTraceString());
}
```