---
layout: default
title: Invoice Operations
nav_order: 3
has_children: true
permalink: /docs/InvoiceOperations
---

# Invoice Operations

This is under development.

The following parameters are required to create or update a contact

|Field  | Type                          | Description |
|:----------|:-------------------------------------|
| DocNumber | String | Invoice/Bill number  |
| `CurrencyRef` | value_name | 
| `CurrencyRef` | value_name |
| GlobalTaxCalculation | String | fixed values (NotApplicable, )|
| `BillEmail` | BillEmailClass | 
| PrivateNote | String | 
| `CustomerMemo` | value_name |
| `BillAddr` | AddressWrapper | 
| TxnDate | String |
| DueDate | String |
| SalesTermRef | value_name | 
| `CustomField` | CustomFieldDetails | 
| `Line` | LineItem | 



|value_name Fields | Type|
|:----------------|:----|
| Value | String |


|BillEmailClass Fields | Type|
|:----------------|:----|
| Address | String |


|AddressWrapper fields | Type| 
|:---------------------|:-----------|
| Line1 | String | 
| Line2 | String |
| Line3 | String |
| Line4 | String |
| Line5 | String |
| City  | String |
| CountrySubDivisionCode | String |
| PostalCode | String |
| Country | String |



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


|LineItem fields | Type| 
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
	
