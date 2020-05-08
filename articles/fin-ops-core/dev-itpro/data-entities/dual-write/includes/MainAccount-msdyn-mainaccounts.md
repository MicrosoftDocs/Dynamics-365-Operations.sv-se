## <a name="main-account-to-msdyn_mainaccounts"></a>Huvudkonto till msdyn_mainaccounts

Den här mallen synkroniserar data mellan Finance and Operations-appar och Common Data Service.

Finance and Operations-fält | Mappningstyp | Övriga Dynamics 365-fält | Standardvärde
---|---|---|---
MAINACCOUNTID | = | msdyn_accountnumber | 
CHARTOFACCOUNTS | = | msdyn_chartofaccounts.msdyn_name | 
NAMN | = | msdyn_name | 
BALANCECONTROL | >< | msdyn_balancecontrol | 
EXCHANGEADJUSTMENTRATETYPE | = | msdyn_exchangeadjustmentratetype.msdyn_name | 
CLOSING | >< | msdyn_closing | 
REPORTINGEXCHANGEADJUSTMENTRATETYPE | = | msdyn_reportingexchangeadjustmentratetype.msdyn_name | 
DEBITCREDITREQUIREMENT | >< | msdyn_debitcreditrequirement | 
FINANCIALREPORTINGEXCHANGERATETYPE | = | msdyn_financialreportingexchangeratetype.msdyn_name | 
FOREIGNCURRENCYREVALUATION | >< | msdyn_foreigncurrencyrevaluation | 
MAINACCOUNTCATEGORY | = | msdyn_mainaccountcategoryname | 
MANDATORYPAYMENTREFERENCE | >< | msdyn_mandatorypaymentreference | 
MONETARY | >< | msdyn_monetary | 
OFFSETACCOUNTDISPLAYVALUE | = | msdyn_offsetaccount | 
POSTINGTYPE | >< | msdyn_postingtype | 
SRUCODE | = | msdyn_srucode | 
VALIDATECURRENCY | >< | msdyn_validatecurrencycode | 
VALIDATEUSER | >< | msdyn_validateuser | 
DEBITCREDITDEFAULT | >< | msdyn_debitcreditdefault | 
DEFAULTCURRENCY | = | msdyn_defaultcurrency.isocurrencycode | 
MAINACCOUNTTYPE | >< | msdyn_mainaccounttype | 
FINANCIALREPORTINGCURRENCYTRANSLATIONTYPE | >< | msdyn_financialreportingcurrencytrantype | 
USER | = | msdyn_user | 
VALIDATEPOSTINGTYPE | >< | msdyn_validateposting | 