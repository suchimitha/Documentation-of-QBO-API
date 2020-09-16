---
layout: default
title: Create Invoice
parent: Invoice Operations
nav_order: 2
---

# Create Invoice


This is under development.

## Sample Requests and Responses

To create an Invoice, pass the values to InvoiceWrapper and assign it to request.qboInvoices and then call the method BreadwinnerQBOAPI.call(). Here customer CustomerRef (QuickBooks Contact Id) is required.



```scss
Map<String, Object> QBInvoice = new Map<String, Object>();
    QBInvoice.put('classification', new Map<String, Object>{'internalId'=>'5'});
    QBInvoice.put('currencyValue', new Map<String, Object>{'internalId'=>'2'});
    QBInvoice.put('customForm', new Map<String, Object>{'internalId'=>'124'});
    QBInvoice.put('department', new Map<String, Object>{'internalId'=>'2'});
    QBInvoice.put('discountItem', new Map<String, Object>{'internalId'=>'-6'});
    QBInvoice.put('discountRate', '-15');
    QBInvoice.put('dueDate', DateTime.newInstance(2020, 12, 31).getTime()/1000);
    QBInvoice.put('entity', new Map<String, Object>{'internalId'=>'362'});
    QBInvoice.put('entityStatus', new Map<String, Object>{'internalId'=>'8'});
    QBInvoice.put('expectedCloseDate', DateTime.newInstance(2020, 12, 31).getTime()/1000);
    QBInvoice.put('externalId', 'SFId: a012w00000Oyssh');
    QBInvoice.put('memo', 'Order 25');
    QBInvoice.put('otherRefNum', '4343399');
    QBInvoice.put('probability', 35);
    QBInvoice.put('title', 'SF Estimate');
    QBInvoice.put('tranDate', DateTime.newInstance(2020, 09, 07).getTime()/1000);
//  Initializing the Estimate Custom Fields
List<Object> estCustomFieldList = new List<Object>();
Map<String,Object> estCustomField = new Map<String,Object>();
    estCustomField.put('fieldType', 'select');
    estCustomField.put('scriptId', 'custbody_customlist');
    estCustomField.put('valueLookup', new Map<String,Object>{'internalId'=>'2'});
    estCustomFieldList.add(estCustomField);

//  Adding the Estimate Custom Fields
    QBInvoice.put('customFieldList', new Map<String,Object>{'customField'=>estCustomFieldList});

//  Initializing the Estimate Line Items
List<Object> lineItemList = new List<Object>();
Map<String, Object> lineItem = new Map<String, Object>();
    lineItem.put('description', 'A weapon for shooting arrows');
    lineItem.put('item', new Map<String, Object>{'internalId'=>'239'});
    lineItem.put('quantity', 1);
    lineItem.put('rate', '999');

//  Initializing the Line Item custom fields
List<Object> liCustomFieldList = new List<Object>();
Map<String, Object> liCustomField = new Map<String, Object>();
    liCustomField.put('fieldType', 'boolean');
    liCustomField.put('scriptId', 'custbody_checkbox');
    liCustomField.put('value', 'true');
    liCustomFieldList.add(liCustomField);

//  Adding the Estimate Line Item Custom Fields
    lineItem.put('customFieldList',new Map<String,Object>{'customField'=>liCustomFieldList});
    lineItemList.add(lineItem);

//  Adding the Line Items to Estimate
Map<String, Object> estimateLineitemList = new Map<String, Object>();
    estimateLineitemList.put('item',lineItemList);
    nsEstimate.put('itemList',estimateLineitemList);

//  Initializing the RequestJSON Data to be passed.
Map<String, Object> requestJSONMap = new Map<String, Object>();
    requestJSONMap.put('estimates', new List<Object>{nsEstimate});
    String reqJSON = JSON.serialize(requestJSONMap);

Map<String, Object> reqObj = new Map<String, Object>();
    reqObj.put('version', '1.0');
    reqObj.put('action', 'createEstimate');
    reqObj.put('requestJSON', reqJSON);

//  Placing a request to Breadwinner Global API
Map<String, Object> resp = breadwinner_ns.BreadwinnerNetSuiteAPI.call(reqObj);
System.debug(resp);
```


```scss
try{
	
    InvoiceWrapper Inv = new InvoiceWrapper();
    inv.docnumber= 'inv-API-VI8';
    //inv.GlobalTaxCalculation = 'TaxInclusive';//'TaxExcluded';
    inv.PaymentRefNum = 'payment Reference number';
    inv.PrivateNote = 'Private note stmt memo';
    inv.ShipDate = string.valueOf(System.today().adddays(10));
    inv.TrackingNum = 'inv tracking number';
    inv.TxnDate = string.valueOf(system.today());
    inv.DueDate = string.valueOf(System.today().adddays(20));
    InvoiceWrapper.BillEmailClass BEC = new InvoiceWrapper.BillEmailClass();
        BEC.Address='suchimitha@breadwinner.com';
    inv.BillEmail = BEC;
    InvoiceWrapper.value_name invCurrency = new InvoiceWrapper.value_name();
        invCurrency.value= 'GBP';
   //// inv.CurrencyRef = invCurrency;
    InvoiceWrapper.value_name custMemo = new InvoiceWrapper.value_name();
        custMemo.value= 'Customer Memo Message displayed on Sales Receipt';
    inv.CustomerMemo = custMemo;
    InvoiceWrapper.value_name custRef = new InvoiceWrapper.value_name();
        custRef.value = '88';
    inv.CustomerRef = custRef;
    InvoiceWrapper.value_name DTF = new InvoiceWrapper.value_name();
        DTF.value = '77';
    inv.DepositToAccountRef = DTF;
    InvoiceWrapper.value_name PMR = new InvoiceWrapper.value_name();
        PMR.value = '3';
    inv.PaymentMethodRef = PMR;
    InvoiceWrapper.value_name STR = new InvoiceWrapper.value_name();
        STR.value = 'Net 60';//'4';
    inv.SalesTermRef = STR;
    InvoiceWrapper.value_name SMR = new InvoiceWrapper.value_name();
        SMR.value = 'Shipping via 7 ship method ref';
        SMR.name = 'Shipping via 7 ship method ref';
    inv.ShipMethodRef = SMR;
    
    
    
    
    List<InvoiceWrapper.LineItem> invLines = new List<InvoiceWrapper.LineItem>();
    for(OpportunityLineItem opProduct: opp2.OpportunityLineitems){
        InvoiceWrapper.LineItem Li = new InvoiceWrapper.LineItem();
        
        Li.Description = opProduct.Description;
        li.DetailType = 'SalesItemLineDetail';
        InvoiceWrapper.SalesItemLineDetail lisid = new InvoiceWrapper.SalesItemLineDetail();
        InvoiceWrapper.value_name livn = new InvoiceWrapper.value_name();
        livn.value = string.valueOf(5);
        lisid.ItemRef =livn;
        lisid.qty=15;
        lisid.ServiceDate = string.valueOf(system.today());
        lisid.UnitPrice = 555;
        InvoiceWrapper.value_name TCR = new InvoiceWrapper.value_name();
        TCR.value = 'TAX';//'NON'//string.valueOf(5);///if taxincluded
        lisid.TaxCodeRef = TCR;
        li.SalesItemLineDetail = lisid;
        
        Li.Amount = lisid.qty*lisid.UnitPrice;//opProduct.unitPrice;
       
        invLines.add(li);
    }
    
    inv.Line = invLines;
    
     List<InvoiceWrapper.CustomFieldDetails> CFS = new List<InvoiceWrapper.CustomFieldDetails>();
        InvoiceWrapper.CustomFieldDetails CF1 =new InvoiceWrapper.CustomFieldDetails();
            CF1.DefinitionId = '1';
            CF1.Type = 'StringType';
            CF1.StringValue = ('Field 1 '+opp2.name).left(30);
            CFS.add(CF1);
        InvoiceWrapper.CustomFieldDetails CF2 =new InvoiceWrapper.CustomFieldDetails();
            CF2.DefinitionId = '2';
            CF2.Type = 'StringType';
            CF2.StringValue = ('Field 2 '+opp2.name).left(30);
            CFS.add(CF2);
      inv.CustomField = CFS;

    
	BreadwinnerQBOAPI.RequestObject req = new  BreadwinnerQBOAPI.RequestObject(); 
	req.qboInvoices = new List<InvoiceWrapper>{inv};
	BreadwinnerQBOAPI.ResponseObject res = BreadwinnerQBOAPI.call('createinvoice', req);//BreadwinnerQBOAPI.call('createinvoice', req);//BreadwinnerQBOAPI.call('createsalesreceipt', req);
	system.debug('========='+res);
    
	system.debug('created Invoice' +res );
	}catch(Exception ex){
		System.debug('Exception occurred while creating customers in QBO.'+ex.getStackTraceString());
	}
```