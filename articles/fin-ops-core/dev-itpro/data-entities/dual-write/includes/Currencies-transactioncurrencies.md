## <a name="currencies-to-transactioncurrencies"></a>Valutor till transactioncurrencies

Den här mallen synkroniserar data mellan Finance and Operations-appar och Common Data Service.

Källfilter: ((CURRENCYCODE != "999"))

Finance and Operations-fält | Mappningstyp | Övriga Dynamics 365-fält | Standardvärde
---|---|---|---
CURRENCYCODE | = | isocurrencycode | 
NAME | = | currencyname | 
SYMBOL | = | currencysymbol | 
none | >> | exchangerate | 1
