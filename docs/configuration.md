---
layout: default
title: Request
nav_order: 2
---

# Request
{: .no_toc }


## Actions
Below are the supported actions which can be processed using Breadwinner for QBO Global API.

<ul>

<li><b>createCustomer</b>: Creates a QuickBooks Online Customer.</li>
<li><b>updateCustomer</b>: Updates a QuickBooks Online Customer.</li>
<li><b>readCustomer</b>: Fetches a single QuickBooks Online Customer or a list of QuickBooks Online Customers from QuickBooks Online.</li>
<li><b>createVendor</b>: Creates a QuickBooks Online Vendor.</li>
<li><b>updateVendort</b>: Updates a QuickBooks Online Vendor.</li>
<li><b>readVendor</b>: Fetches a single QuickBooks Online Vendor or a list of QuickBooks Online Vendors from QuickBooks Online.</li>
<li><b>createInvoice</b>: Creates an Invoice in QuickBooks Online.</li>
<li><b>updateInvoice</b>: Updates in Invoice in QuickBooks Online.</li>
<li><b>readInvoices</b>: Fetches either a single Invoice or list of Invoices from QuickBooks Online.</li>
<li><b>createBill</b>: Creates a Bill in QuickBooks Online.</li>
<li><b>updateBill</b>: Updates a Bill in QuickBooks Online.</li>
<li><b>readBills</b>: Fetches either a single Bill or list of Bills from QuickBooks Online.</li>
<li><b>createPurchaseOrder</b>: Creates a Purchase Order (PO) in QuickBooks Online.</li>
<li><b>updatePurchaseOrder</b>: Updates a Purchase Order (PO) in QuickBooks Online.</li>
<li><b>readPurchaseOrders</b>: Fetches either a single Purchase Order or a list of Purchase Orders from QuickBooks Online.</li>
<li><b>createSalesReceipt</b>: Creates a Sales Receipt in QuickBooks Online.</li>
<li><b>updateSalesReceipt</b>: Updates a Sales Receipt in QuickBooks Online.</li>
<li><b>readSalesReceipt</b>: Fetches either a single Sales Receipt or a list of Sales Receipts from QuickBooks Online.</li>
<li><b>createCreditMemo</b>: Creates a Credit Memo in QuickBooks Online.</li>
<li><b>updateCreditMemo</b>: Updates a Credit Memo in QuickBooks Online.</li>
<li><b>readCreditMemo</b>: Fetches either a single Credit Memo or a list of Credit Memos from QuickBooks Online.</li>

</ul>

As of now, Breadwinner supports only the above mentioned actions. More actions will be included in upcoming releases.

## Request

As mentioned earlier, Breadwinner accepts the Request data in the form of a Map<String, Object>.

These are the supported keys: 

|Key (String) | Value (Object) | Required |
|:------------|:---------------|:---------|
|version|‘1.0’ |True|
|action|See the list of available actions.|True|
|requestJSON|Pass the data as a JSON string, based on the specified action.|True|


