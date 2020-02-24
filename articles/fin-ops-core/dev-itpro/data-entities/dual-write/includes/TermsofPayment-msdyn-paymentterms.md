## <a name="terms-of-payment-to-msdyn_paymentterms"></a>Betalningsvillkor till msdyn_paymentterms

Den här mallen synkroniserar data mellan Finance and Operations-appar och Common Data Service.

Finance and Operations-fält | Mappningstyp | Övriga Dynamics 365-fält | Standardvärde
---|---|---|---
BESKRIVNING | = | msdyn_description | 
NAMN | = | msdyn_name | 
NUMBEROFMONTHS | = | msdyn_numberofmonth | 
CUTOFFDAYOFMONTH | = | msdyn_cutoffdayofmonth | 
ISCASHPAYMENT | >< | msdyn_iscashpayment | 
NUMBEROFDAYS | = | msdyn_days | 
ISCERTIFIEDCOMPANYCHECK | >< | msdyn_iscertifiedcompanycheck | 
ISDEFAULTPAYMENTTERM | >< | msdyn_isdefaultpaymentterm | 
CREDITCARDPAYMENTTYPE | >< | msdyn_creditcardpaymenttype | 
CREDITCARDCREDITCHECKTYPE | >< | msdyn_creditcardcreditchecktype | 
PAYMENTDAYNAME | = | msdyn_paymentdayname.msdyn_name | 
PAYMENTMETHODTYPE | >< | msdyn_paymentmethodtype | 
PAYMENTSCHEDULENAME | = | msdyn_paymentschedulename.msdyn_name | 
