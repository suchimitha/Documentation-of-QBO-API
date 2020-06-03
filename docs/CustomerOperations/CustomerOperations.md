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
|DisplayName * | String | Full name of contact/vendor/organisation (max length = 255), Required  |
|CompanyName | String | Contact/Vendor companey name|
|GivenName | String | Contact/Vendor name|
|FamilyName |String | contact/Vendor family name|
|`BillAddr` | AddressWrapper | Type of BillAddr. check below for BillAddr fields|
|EmailAddress | String | Email address of contact/vendor|
|`PrimaryEmailAddr` | PrimaryEmailAddr | Type of PrimaryEmailAddr. check below for PrimaryEmailAddr fields|
|Phone| String | Phone number of contact/vendor|
|MobileNumber| String | Mobile Number of contact/vendor|
|`PaymentMethodRef` | value_name | Type of value_name. check below for value_name fields|
|`SalesTermRef`  | value_name | Type of value_name. check below for value_name fields|
|`CurrencyRef` | value_name |  Type of value_name. check below for value_name fields|





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

|value_name Fields | Type|
|:----------------|:----|
|Value | String |

