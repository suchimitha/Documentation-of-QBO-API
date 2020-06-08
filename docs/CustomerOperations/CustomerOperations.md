---
layout: default
title: Contact Operations
nav_order: 5
has_children: true
permalink: docs/CustomerOperations
---

# Contact Operations


The following parameters are required to create or update a contact

|Field  | Type                          | Description |
|:----------|:-------------------------------------|
|DisplayName * | String | The name of the person or organization as displayed. Must be unique across all Customer and Vendor (max length = 255), Required  |
|CompanyName | String | Contact/Vendor Company name|
|GivenName | String | Given name or first name of a person.|
|FamilyName |String | Family name or the last name of the person.|
|`BillAddr` | AddressWrapper | Type of BillAddr. check below for BillAddr fields|
|EmailAddress | String | Email address of contact/vendor|
|`PrimaryEmailAddr` | PrimaryEmailAddr | EmailAddress, Type of PrimaryEmailAddr. check below for PrimaryEmailAddr fields|
|Phone| String | Phone number of contact/vendor|
|MobileNumber| String | Mobile Number of contact/vendor|
|`PaymentMethodRef` | value_name | Type of value_name. check below for value_name fields|
|`SalesTermRef`  | value_name | Reference to a SalesTerm associated with this Customer object. It is a type of value_name. check below for value_name fields|
|`CurrencyRef` | value_name |  Reference to the currency in which all amounts associated with this customer are expressed. Once set, it cannot be changed. It is a type of value_name. check below for value_name fields|
|`ParentRef`| ParentRef | A reference to a Customer object that is the immediate parent of the Sub-Customer/Job in the hierarchical Customer:Job list. Required for the create operation if this object is a sub-customer |





|AddressWrapper fields | Type| 
|:---------------------|:-----------|
|Line1 | String | 
|Line2 | String |
|Line3 | String |
|Line4 | String |
|Line5 | String |
|City  | String |
|CountrySubDivisionCode | String |
|PostalCode | String |
|Country | String |




|PrimaryEmailAddr  Fields | Type|
|:------------------------|:----|
|Address | String |

|ParentRef Fields | Type|
|:----------------|:----|
|value | String | 

