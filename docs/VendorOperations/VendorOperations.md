---
layout: default
title: Vendor Operations
nav_order: 7
has_children: true
permalink: docs/VendorOperations
---

# Vendor Operations


The following parameters are required to create or update a contact

|Field  | Type                          | Description |
|:----------|:-------------------------------------|
|DisplayName * | String | The name of the person or organization as displayed. Must be unique across all Customer and Vendor (max length = 255), Required  |
|CompanyName | String | Contact/Vendor Company name|
|GivenName | String | Given name or first name of a person.|
|FamilyName |String | Family name or the last name of the person.|
|BillAddr | `AddressWrapper` | Type of BillAddr. check below for BillAddr fields|
|EmailAddress | String | Email address of contact/vendor|
|PrimaryEmailAddr | `PrimaryEmailAddr` | EmailAddress, Type of PrimaryEmailAddr. check below for PrimaryEmailAddr fields|
|Phone| String | Phone number of contact/vendor|
|MobileNumber| String | Mobile Number of contact/vendor|
|CurrencyRef | `value_name` |  Reference to the currency in which all amounts associated with this customer are expressed. Once set, it cannot be changed. It is a type of value_name. check below for value_name fields|
|PrimaryPhone | `PhoneWrapper` | Primary phone number.|
|Mobile | `PhoneWrapper` | Mobile phone number.|
|Id | String | Unique identifier for this object and ReadOnly field. |
|SyncToken | String | Version number of the object, It is used to lock an object for use by one app at a time and ReadOnly field. |
|Metadata | `Metadata` | Descriptive information about the entity. The MetaData values are set by Data Services and are read only. |
|PrintOnCheckName | String | Name of the person or organization as printed on a check. |




|AddressWrapper fields | Type| Description|
|:---------------------|:-----------|:------|
|Line1 | String | Address 1 |
|Line2 | String | Address 2 |
|Line3 | String | Address 3, as needed | 
|Line4 | String | Address 4, as needed |
|Line5 | String | Address 5, as needed |
|City  | String | City | 
|CountrySubDivisionCode | String | Subdivision code|
|PostalCode | String | Postal code | 
|Country | String | Country |




|PrimaryEmailAddr  Fields | Type|Description|
|:------------------------|:----|:----------|
|Address | String | An email address. The address format must follow. |


|PhoneWrapper Fields | Type | Description|
|:-------------------|:-----|:-----------|
| FreeFormNumber | String | 


|value_name Fields | Type | Description | 
|:-----------------|:-----|:-------------|
|Value | String | |
|Name | String | |


|Metadata Fields | Type | Description | 
|:-----------------|:-----|:-------------|
|PreferredDeliveryMethod | String | |
|ResaleNum | String | |



