---
layout: default
title: Update Customer
parent: Customer Operations
nav_order: 3
---

# Update Customer


To Update a QuickBooks Online Customer pass the values to Accountwrapper along with contactId (QuickBooks Online identifier) and assign it to request.qboContacts and then call the method BreadwinnerQBOAPI.call().

## sample code 

```scss
try{
	qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();	
	List<qboapi_g1.AccountWrapper> qboContactsList = new List<qboapi_g1.AccountWrapper>();
	qboapi_g1.AccountWrapper qboContact = new qboapi_g1.AccountWrapper();
	//qboContact.name=' Contact name -'; 
	qboContact.DisplayName = 'Customer full name updated';
    qboContact.id='84';// is QuickbooksOnline Unique Contact Id
    
    qboapi_g1.AccountWrapper.AddressWrapper adwrap = new qboapi_g1.AccountWrapper.AddressWrapper();
    adwrap.Line1 = '11-21-34/A';
    adwrap.City = 'hyderabad';
    adwrap.CountrySubDivisionCode = 'rangareddy';
    adwrap.PostalCode = '500087';
    adwrap.Country = 'India';
    qboContact.BillAddr = adwrap;

	qboContactsList.add(qboContact);            
	req.qboContacts= qboContactsList;

	qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('updatecustomer', req);
	if(res.errors!=null && res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
			System.debug(er); 
		}
	}
	system.debug('updated customer' +res.Contacts);
}catch(Exception ex){
	System.debug('Exception occurred updating Customer in QuickBooks Online.'+ex.getStackTraceString());
}
```