## <a name="fiscal-calendar-period-to-msdyn_fiscalcalendarperiods"></a>Räkenskapskalenderperiod till msdyn_fiscalcalendarperiods

Den här mallen synkroniserar data mellan Finance and Operations-appar och Common Data Service.

Finance and Operations-fält | Mappningstyp | Övriga Dynamics 365-fält | Standardvärde
---|---|---|---
COMMENTS | = | msdyn_comments | 
ENDDATE | = | msdyn_enddate | 
MONTH | >< | msdyn_month | 
CALENDAR | = | msdyn_fiscalcalendar.msdyn_calendar | 
QUARTER | >< | msdyn_quarter | 
SHORTNAME | = | msdyn_shortname | 
STARTDATE | = | msdyn_startdate | 
TYPE | >< | msdyn_fiscalperiodtype | 
PERIODNAME | = | msdyn_periodname | 
FISCALYEAR | = | msdyn_fiscalcalendaryear.msdyn_name | 
CALENDAR | = | msdyn_fiscalcalendaryear.msdyn_fiscalcalendarname | 
