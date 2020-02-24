## <a name="cds-contacts-v2-to-contacts"></a>CDS-kontakter V2 till kontakter

Den här mallen synkroniserar data mellan Finance and Operations-appar och Common Data Service.

Källfilter: (AssociatedContactType = 1)

Återfört källfilter: msdyn_contactforvendor eq true and msdyn_sellable eq false and msdyn_contactpersonid ne ''

Finance and Operations-fält | Mappningstyp | Övriga Dynamics 365-fält | Standardvärde
---|---|---|---
CONTACTPERSONPARTYNUMBER | = | msdyn_partynumber | 
ASSOCIATEDCONTACTTYPE | << | none | Leverantör
FIRSTNAME | = | firstname | 
MIDDLENAME | = | middlename | 
LASTNAME | = | lastname | 
ASSOCIATEDCONTACTNUMBER | = | msdyn_vendorcontactid.msdyn_vendoraccountnumber | 
PRIMARYADDRESSCITY | = | address1_city | 
PRIMARYADDRESSCOUNTRYREGIONID | = | address1_country | 
PRIMARYADDRESSCOUNTYID | = | address1_county | 
PRIMARYFAXNUMBER | = | fax | 
PRIMARYADDRESSSTATEID | = | address1_stateorprovince | 
PRIMARYADDRESSSTREET | = | address1_line1 | 
PRIMARYADDRESSZIPCODE | = | address1_postalcode | 
PRIMARYPHONENUMBER | = | telephone1 | 
PRIMARYEMAILADDRESS | = | emailaddress1 | 
EMPLOYMENTDEPARTMENT | = | department | 
NOTES | = | description | 
GENDER | >< | gendercode | 
GOVERNMENTIDENTIFICATIONNUMBER | = | governmentid | 
PRIMARYURL | = | websiteurl | 
MARITALSTATUS | >< | familystatuscode | 
ISRECEIVINGDIRECTMAIL | >< | donotemail | 
EMPLOYMENTPROFESSION | = | jobtitle | 
SPOUSENAME | = | spousesname | 
none | >> | msdyn_contactforvendor | True
CONTACTPERSONID | = | msdyn_contactpersonid | 
