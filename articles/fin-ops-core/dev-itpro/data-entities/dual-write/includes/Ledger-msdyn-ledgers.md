## <a name="ledger-to-msdyn_ledgers"></a>Redovisning till msdyn_ledgers

Den här mallen synkroniserar data mellan Finance and Operations-appar och Common Data Service.

Finance and Operations-fält | Mappningstyp | Övriga Dynamics 365-fält | Standardvärde
---|---|---|---
LEGALENTITYID | >> | msdyn_company.cdm_companycode | 
DESCRIPTION | >> | msdyn_description | 
ACCOUNTINGCURRENCY | >> | msdyn_accountingcurrency.isocurrencycode | 
ISBUDGETCONTROLENABLED | >> | msdyn_isbudgetcontrolenabled | 
NAME | >> | msdyn_name | 
REPORTINGCURRENCY | >> | msdyn_reportingcurrency.isocurrencycode | 
BUDGETEXCHANGERATETYPE | >> | msdyn_budgetexchangeratetype.msdyn_name | 
CHARTOFACCOUNTS | >> | msdyn_chartofaccounts.msdyn_name | 
EXCHANGERATETYPE | >> | msdyn_exchangeratetype.msdyn_name | 
FISCALCALENDAR | >> | msdyn_fiscalcalendar.msdyn_calendar | 
REPORTINGCURRENCYEXCHANGERATETYPE | >> | msdyn_reportingcurrencyexchangeratetype.msdyn_name | 
