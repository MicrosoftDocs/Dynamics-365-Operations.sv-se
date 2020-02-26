## <a name="withholding-tax-codes-to-msdyn_withholdingtaxcodes"></a>Källskattekoder till msdyn_withholdingtaxcodes

Den här mallen synkroniserar data mellan Finance and Operations-appar och Common Data Service.

Finance and Operations-fält | Mappningstyp | Övriga Dynamics 365-fält | Standardvärde
---|---|---|---
WITHHOLDINGCODE | = | msdyn_name | 
WITHHOLDINGTAXNAME | = | msdyn_description | 
WITHHOLDINGTAXROUNDOFF | = | msdyn_roundoff | 
WITHHOLDINGTAXROUNDOFFTYPE | >< | msdyn_roundofftype | 
CURRENCYCODEID | = | msdyn_currency.isocurrencycode | 
WITHHOLDINGTAXBASE | >< | msdyn_taxableamountorigin | 
