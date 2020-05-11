---
layout: default
title: Create QuickBooks Online Contact
parent: Contact Operations
nav_order: 1
---

# Create QuickBooks Online Contact

## sample code 

To create a QuickBooks Online Contact, pass the values to Accountwrapper and assign it to request.qboContacts and then call the method BreadwinnerQBOAPI.call().

```scss
try{
	qboapi_g1adwinnerQBOAPI.RequestObject req = new  qboaqboapi_g1nnerQBOAPI.RequestObject();	
	List<qboapi_gqboapi_g1per> qboContactsList = new List<qboapi_g1.Acqboapi_g1();
	qboapi_g1.Accounqboapi_g1Contact = new qboapi_g1.AccountWraqboapi_g1Contact.name='Test Customer'; 
	qboContactsList.add(qboContact);            
	req.qboContacts = qboContactsList;

	qboapi_g1.BreadwinnerQBOqboapi_g1bject res =  qboapi_g1.BreadwinnerQBOAPI.qboapi_g1ontact', req);
	if(res.errors.size()>0){
		for(qboapi_g1.BreadwinnerQBOAPI.Erroqboapi_g1ors){
			System.debug(er); 
		}
	}
	system.debug('created customer' +res.qboContacts);
}catch(Exception ex){
	System.debug('Exception occurred while creating customers in QuickBooks Online.'+ex.getStackTraceString());
}
```
