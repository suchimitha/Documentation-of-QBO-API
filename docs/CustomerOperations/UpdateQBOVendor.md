---
layout: default
title: Update QuickBooks Online Contact
parent: Contact Operations
nav_order: 2
---

# Update QuickBooks Online Contact
To Update a QuickBooks Online Contact pass the values to Accountwrapper along with contactId (QuickBooks Online identifier) and assign it to request.qboContacts and then call the method BreadwinnerQBOAPI.call().

## sample code 

```scss
try{
	qboapi_g1.BreadwinnerQBOAPI.RequestObject req = new  qboapi_g1.BreadwinnerQBOAPI.RequestObject();	
	List<qboapi_g1.AccountWrapper> qboContactsList = new List<qboapi_g1.AccountWrapper>();
	qboapi_g1.AccountWrapper qboContact = new qboapi_g1.AccountWrapper();
	qboContact.name='Test Customer'; 
	qboContact.contactId ='3f5873c9-0faf-4ca4-9c0d-140c59636d0e'; //Required		
	qboContactsList.add(qboContact);            
	req.qboContacts = qboContactsList;

	qboapi_g1.BreadwinnerQBOAPI.ResponseObject res =  qboapi_g1.BreadwinnerQBOAPI.call('updateContact', req);
	if(res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Error er :res.errors){
			System.debug(er); 
		}
	}
	system.debug('created customer' +res.qboContacts);
}catch(Exception ex){
	System.debug('Exception occurred while creating customers in QuickBooks Online.'+ex.getStackTraceString());
}
```