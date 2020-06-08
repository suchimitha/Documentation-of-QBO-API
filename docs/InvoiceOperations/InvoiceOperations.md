---
layout: default
title: Invoice Operations
nav_order: 3
has_children: true
permalink: /docs/InvoiceOperations
---

# Invoice Operations

This is under development.

The following parameters are required to create or update a Invoice/Bill/PO

|Field  | Type                          | Description |
|:----------|:-------------------------------------|
| DocNumber | String | Invoice/Bill number  |
| `CurrencyRef` | value_name |Reference to the currency in which all amounts on the associated transaction are expressed.| 
| `CustomerRef` | value_name | The ID (Unique QuickBooks Online ID) for the referenced customer/vendor|
| GlobalTaxCalculation | String | fixed values (NotApplicable, TaxInclusive)|
| `BillEmail` | BillEmailClass | Identifies the e-mail address where the invoice is sent |
| PrivateNote | String | User entered, organization-private note about the transaction.|
| `CustomerMemo` | value_name | User-entered message to the customer; this message is visible to end user on their transactions|
| `BillAddr` | AddressWrapper | Identifies the e-mail address where the invoice is sent.|
| TxnDate | String | The date entered by the user when this transaction occurred.|
| DueDate | String | Date when the payment of the transaction is due. |
| SalesTermRef | value_name | Reference to the sales term associated with the transaction.|
| `CustomField` | CustomFieldDetails | One of, up to three custom fields for the transaction. Available for custom fields so configured for the company. |
| `Line` | LineItem | Individual line items of a transaction. |



|value_name Fields | Type|
|:----------------|:----|
| Value | String |


|BillEmailClass Fields | Type|Description|
|:----------------|:----|:------|
| Address | String |An email address. The address format must follow.|


|AddressWrapper fields | Type| Description|
|:---------------------|:-----------|
| Line1 | String | Address 1 |
| Line2 | String | Address 2 |
| Line3 | String | Address 3 |
| Line4 | String | Address 4 |
| Line5 | String | Address 5 |
| City  | String | City |
| CountrySubDivisionCode | String | Subdivision code|
| PostalCode | String | Postal code|
| Country | String | Country|



|LineItem fields | Type| 
|:---------------------|:-----------|
| Id | String |
| LineNum | Integer | 
| Amount | Decimal |
| Description | String |
| DetailType | String | 
| `SalesItemLineDetail` | SalesItemLineDetail |
| `ItemBasedExpenseLineDetail` | ItemBasedExpenseLineDetail |
| `AccountBasedExpenseLineDetail` | AccountBasedExpenseLineDetail |
| `DiscountLineDetail` | DiscountLineDetail |
| TaxInclusiveAmt | Decimal |


|SalesItemLineDetail fields | Type| 
|:---------------------|:-----------|
| `ItemRef` | value_name |
| `ClassRef` | value_name |
| `TaxCodeRef` | value_name |
| UnitPrice | Decimal | 
| Qty | Decimal | 
| ServiceDate | String | 



|CustomFieldDetails fields | Type| 
|:---------------------|:-----------|
| DefinitionId | String |
| Name | String |
| Type | String |
| StringValue | String |
	
