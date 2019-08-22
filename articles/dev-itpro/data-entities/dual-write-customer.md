---
title: Integrerat kundhuvud
description: I det här avsnittet beskrivs integreringen av kunddata mellan Finance and Operations och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a8030d9d1f1f3636a679d334afddad0f573a824e
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789246"
---
## <a name="integrated-customer-master"></a>Integrerat kundhuvud

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Det är typiskt för kundposter som ska hanteras i mer än ett program. Försäljningsaktivitet kan till exempel föra in kommersiella kundposter via ett Microsoft Dynamics 365 for Sales-program och e-handels- eller butiksförsäljning kan ta in kundposter via ett Dynamics 365 for Finance and Operations-program. Oavsett var kundposten har sitt ursprung integreras den bakom kulisserna i programgränser och infrastrukturskillnader. Integrerad kundhantering hjälper till att hantera scenarier med flera hanteringar och ger en heltäckande vy av kunden till Dynamics 365 programsvit.

## <a name="customer-data-flow"></a>Kunddataflöde

*Kund* är ett väldefinierat koncept inom både Finance and Operations och Common Data Service. Därför innebär integreringen av kunddata bara harmonisering av kundkonceptet mellan Finance and Operations och Common Data Service-applikationer. Illustrationen som följer visar kunddataflödet.

![Kunddataflöde](media/dual-write-customer-data-flow.png)

Kunder kan i stort sett delas in i två typer: kommersiella/organisatoriska kunder och konsumenter/slutanvändare. Dessa två typer av kunder lagras och hanteras på olika sätt i Finance and Operations och Common Data Service.

I Finance and Operations hanteras både kommersiella/organisatoriska kunder och konsumenter/slutanvändare i en enda tabell som kallas **CustTable** (CustomerCustomerV3Entity) och de klassificeras baserat på attributet **Typ**. (Om **typ** är inställd på **organisation** är kunden en kommersiell/organisatorisk kund och om **typ** är inställd på **person** är kunden en konsument/slutanvändare.) Den primära kontaktpersonens information hanteras via entiteten SMMContactPersonEntity.

I Common Data Service hanteras kommersiella/organisatoriska kunder i kontoentiteten och identifieras som kunder när attributet **RelationshipType** är inställt på **kund**. Både konsumenter/slutanvändare och kontaktpersonen representeras av kontaktentiteten. För att ge en tydlig åtskillnad mellan en konsument/slutanvändare och en kontaktperson har entiteten **kontakt** en boolesk flagga som heter **säljbar**. När **säljbar** är **sant** är kontakten en konsument/slutanvändare och offerter och order kan skapas för den kontakten. När **säljbar** är **falskt** är kontakten bara en primär kontaktperson för en kund.

När en icke-säljbar kontakt deltar i en offert eller orderprocess är **säljbart** inställt på **sant** för att flagga kontakten som en säljbar kontakt. En kontakt som har blivit en säljbar kontakt förblir en säljbar kontakt.

## <a name="templates"></a>Mallar

Kunddata innehåller all information om kunden, till exempel kundgruppen, adresser, kontaktinformation, betalningsprofil, fakturaprofil och förmånsstatus. En samling entitetsmappningar fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Finance and Operations    | Customer Engagement-program
--------------------------|---------------------------------
Kund V3               | Konto
Kund V3               | Kontakt
CDS-kontakter V2           | Kontakt
Kundgrupper           | Msdyn\_customergroups
Kundbetalningsmetod   | Msdyn\_customerpaymentmethods
Förmånskort              | Msdyn\_loyaltycards
Betalningsplan          | Msdyn\_paymentschedules
Betalningsplan          | Msdyn\_paymentschedulelines
Betalningsdag – CDS           | Msdyn\_paymentdays
Betalningsdagsrader – CDS     | Msdyn\_paymentdaylines
Betalningsvillkor          | Msdyn\_paymentterms
Namnaffix              | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="customer-v3-to-account"></a>Kund V3 till konto

Den här mallen synkroniserar kundhuvudinformation för kommersiella och organisatoriska kunder mellan Finance and Operations och Common Data Service.

<!-- ![](media/dual-write-account-1.png) -->

<!-- ![](media/dual-write-account-2.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
CUSTOMERACCOUNT | = | accountnumber
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
CREDITLIMIT | = | creditlimit
DELIVERYADDRESSCITY | = | address1\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
DELIVERYADDRESSCOUNTY | = | address1\_county
DELIVERYADDRESSLATITUDE | \> | address1\_latitude
DELIVERYADDRESSLONGITUDE | \> | address1\_longitude
DELIVERYADDRESSZIPCODE | = | address1\_postalcode
ORGANIZATIONNAME | = | namn
ORGANIZATIONNUMBEROFEMPLOYEES | = | numberofemployees
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTTWITTER | = | primarytwitterid
PRIMARYCONTACTURL | = | websiteurl
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | beskrivning
CREDITLIMITISMANDATORY | \>\< | msdyn\_creditlimitismandatory
CREDITRATING | = | msdyn\_creditrating
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
INVOICEACCOUNT | = | msdyn\_billingaccount.accountnumber
INVOICEADDRESS | \>\< | msdyn\_invoiceaddress
ISONETIMECUSTOMER | \>\< | msdyn\_onetimecustomer
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PAYMENTDAY | = | msdyn\_paymentday.msdyn\_name
PAYMENTMETHOD | = | msdyn\_customerpaymentmethod.msdyn\_name
PAYMENTSCHEDULE | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTTERMS | = | msdyn\_paymentterm.msdyn\_name
PAYMENTTERMSBASEDAYS | = | msdyn\_paymenttermsbasedays
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
PRIMARYCONTACTLINKEDIN | = | msdyn\_primarylinkedinid
TAXEXEMPTNUMBER | = | msdyn\_taxexemptnumber
VENDORACCOUNT | = | msdyn\_vendor.msdyn\_vendoraccountnumber
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
LANGUAGEID | \<\< | ingen
DELIVERYADDRESSSTREET | = | address1\_line1
DELIVERYADDRESSSTATE | = | address1\_stateorprovince
ingen | \>\> | address1\_addresstypecode
ingen | \>\> | customertypecode
PARTYTYPE | \<\< | ingen
PARTYNUMBER | = | msdyn\_partynumber

## <a name="customer-v3-to-contact"></a>Kund V3 till kontakt

Den här mallen synkroniserar kundhuvuddata för kommersiella och slutanvändare mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-contact-1.png) -->
<!-- ![](media/dual-write-contact-2.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
ingen | \>\> | msdyn\_säljbar
PARTYTYPE | \<\< | ingen
PARTYNUMBER | = | msdyn\_partynumber
CUSTOMERACCOUNT | = | msdyn\_contactpersonid
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
PERSONFIRSTNAME | = | förnamn
PERSONLASTNAME | = | efternamn
PERSONMIDDLENAME | = | mellannamn
PERSONPROFESSIONALTITLE | = | jobtitle
PERSONGENDER | \>\< | gendercode
PERSONMARITALSTATUS | \>\< | familystatuscode
LANGUAGEID | \<\< | ingen
ADDRESSCITY | = | address1\_city
ADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
ADDRESSCOUNTY | = | address1\_county
ADDRESSLATITUDE | \> | address1\_latitude
ADDRESSLONGITUDE | \> | address1\_longitude
ADDRESSLOCATIONROLES | \<\< | ingen
ADDRESSSTATE | = | address1\_stateorprovince
ADDRESSSTREET | = | address1\_line1
ADDRESSZIPCODE | = | address1\_postalcode
ADDRESSPOSTBOX | = | address1\_postofficebox
ingen | \>\> | address1\_addresstypecode
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
ingen | \>\> | address2\_addresstypecode
DELIVERYADDRESSCITY | = | address3\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address3\_country
DELIVERYADDRESSCOUNTY | = | address3\_county
DELIVERYADDRESSLATITUDE | \> | address3\_latitude
DELIVERYADDRESSLONGITUDE | \>\> | address3\_longitude
DELIVERYADDRESSSTATE | = | address3\_stateorprovince
DELIVERYADDRESSSTREET | = | address3\_line1
DELIVERYADDRESSZIPCODE | = | address3\_postalcode
ingen | \>\> | address3\_addresstypecode
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTLINKEDIN | = | msdyn\_primaryinkedinid
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTER | = | msdyn\_primarytwitterid
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURL | = | websiteurl
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | beskrivning

## <a name="contacts"></a>Kontakter

Den här mallen synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer, mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-contacts.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
CONTACTPERSONPARTYNUMBER | = | msdyn\_partynumber
ASSOCIATEDCONTACTTYPE | \<\< | ingen
FIRSTNAME | = | förnamn
mellannamn | = | mellannamn
LASTNAME | = | efternamn
ASSOCIATEDCONTACTNUMBER | = | msdyn\_vendorcontactid.msdyn\_vendoraccountnumber
PRIMARYADDRESSCITY | = | address1\_city
PRIMARYADDRESSCOUNTRYREGIONID | = | address1\_country
PRIMARYADDRESSCOUNTYID | = | address1\_county
PRIMARYFAXNUMBER | = | fax
PRIMARYADDRESSSTATEID | = | address1\_stateorprovince
PRIMARYADDRESSSTREET | = | address1\_line1
PRIMARYADDRESSZIPCODE | = | address1\_postalcode
PRIMARYPHONENUMBER | = | telephone1
PRIMARYEMAILADDRESS | = | emailaddress1
EMPLOYMENTDEPARTMENT | = | avdelning
NOTES | = | beskrivning
GENDER | \>\< | gendercode
GOVERNMENTIDENTIFICATIONNUMBER | = | governmentid
PRIMARYURL | = | websiteurl
MARITALSTATUS | \>\< | familystatuscode
ISRECEIVINGDIRECTMAIL | \>\< | donotemail
EMPLOYMENTPROFESSION | = | jobtitle
SPOUSENAME | = | spousesname
ingen | \>\> | msdyn\_contactforvendor
ingen | \>\> | msdyn\_contactpersonid

## <a name="customer-groups"></a>Kundgrupper

Den här mallen synkroniserar kundgruppinformation mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-customer-groups.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
CUSTOMERGROUPID | = | msdyn\_groupid
BESKRIVNING | = | msdyn\_description
ISSALESTAXINCLUDEDINPRICE | \>\< | msdyn\_issalestaxincludedinprice
PAYMENTTERMID | = | msdyn\_paymenttermid.msdyn\_name
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymenttermname.msdyn\_name

## <a name="customer-payment-methods"></a>Kundbetalningsmetoder

Den här mallen synkroniserar information om kundbetalningsmetod mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-customer-payment-methods.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
NAMN | = | msdyn\_name
ACCOUNTTYPE | \>\< | msdyn\_accounttype
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingpostingenabled
ISSEPA | \>\< | msdyn\_issepa
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
BESKRIVNING | = | msdyn\_description
PAYMENTTYPE | \>\< | msdyn\_paymenttype
CREATEANDDRAWBILLOFEXCHANGEDURINGINVOICEPOSTING | \>\< | msdyn\_invoiceupdate
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_enablepostdatescheckclearingposting
BILLOFEXCHANGEDRAFTTYPE | \>\< | msdyn\_billofexchangedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

## <a name="loyalty-cards"></a>Förmånskort

Den här mallen synkroniserar information om kundförmånskort mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-loyalty-cards.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
CARDNUMBER | = | msdyn\_cardnumber
CARDTENDERTYPE | \>\< | msdyn\_cardtendertype
PARTYNUMBER | = | msdyn\_partynumber
REPLACEMENTCARDNUMBER | \> | msdyn\_replacementcardnumber
OMOPERATINGUNITNUMBER | = | msdyn\_operatingunitnumber
LOYALTYENROLLMENTDATE | = | msdyn\_enrollmentdate

## <a name="payment-schedules"></a>Betalningsplaner

Den här mallen synkroniserar referensdata för betalningsplan för både kunder och leverantörer mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-payment-schedules.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
NAMN | = | msdyn\_name
BESKRIVNING | = | msdyn\_description
ALLOCATIONMETHOD | \>\< | msdyn\_allocationmethod
PAYMENTFREQUENCYUNITS | \>\< | msdyn\_paymentfrequencyunit
PAYMENTFREQUENCY | = | msdyn\_paymentfrequency
NUMBEROFPAYMENTS | = | msdyn\_numberofpayments
FIXEDPAYMENTAMOUNT | = | msdyn\_fixedpaymentamount
MINIMUMPAYMENTAMOUNT | = | msdyn\_minimumpaymentamount
SALESTAXALLOCATIONMETHOD | \>\< | msdyn\_salestaxallocationmethod
NOTES | = | msdyn\_note

## <a name="payment-schedule-lines"></a>Betalningsplanrader

Synkronisera referensdata för betalningsplanrader för både kunder och leverantörer mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-payment-schedule-lines.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTSCHEDULENAME | \> | msdyn\_name
LINENUMBER | = | msdyn\_linenumber
PERIODSAFTERDUEDATE | = | msdyn\_periodsafterduedate
PERCENTORAMOUNT | \>\< | msdyn\_percentoramount
PERCENTORAMOUNTVALUE | = | msdyn\_percentoramountvalue

## <a name="payment-days"></a>Betalningsdagar

Den här mallen synkroniserar referensdata för betalningsdagar för både kunder och leverantörer mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-payment-days.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
NAMN | = | msdyn\_name
BESKRIVNING | = | msdyn\_description

## <a name="payment-day-lines"></a>Betalningsdagsrader

Den här mallen synkroniserar referensdata för betalningsdagsrader för både kunder och leverantörer mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-payment-day-lines.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
CDSINTEGRATIONKEY | = | msdyn\_paymentdaylineid
FREKVENS | \>\< | msdyn\_frequency
DAYOFWEEK | \>\< | msdyn\_dayofweek
DAYOFMONTH | = | msdyn\_dayofmonth
NAMN | = | msdyn\_paymentday.msdyn\_name

## <a name="payment-terms"></a>Betalningsvillkor

Den här mallen synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-payment-terms.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
BESKRIVNING | = | msdyn\_description
NAMN | = | msdyn\_name
NUMBEROFMONTHS | = | msdyn\_numberofmonth
CUTOFFDAYOFMONTH | = | msdyn\_cutoffdayofmonth
ISCASHPAYMENT | \>\< | msdyn\_iscashpayment
NUMBEROFDAYS | = | msdyn\_days
ISCERTIFIEDCOMPANYCHECK | \>\< | msdyn\_iscertifiedcompanycheck
ISDEFAULTPAYMENTTERM | \>\< | msdyn\_isdefaultpaymentterm
CREDITCARDPAYMENTTYPE | \>\< | msdyn\_creditcardpaymenttype
CREDITCARDCREDITCHECKTYPE | \>\< | msdyn\_creditcardcreditchecktype
PAYMENTDAYNAME | = | msdyn\_paymentdayname.msdyn\_name
PAYMENTMETHODTYPE | \>\< | msdyn\_paymentmethodtype
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedulename.msdyn\_name

## <a name="name-affixes"></a>Namnaffix

Den här mallen synkroniserar referensdata för namnaffix för både kunder och leverantörer mellan Finance and Operations och Customer Engagement.

<!-- ![](media/dual-write-name-affixes.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
AFFIX | = | msdyn\_affix
TYP | \>\< | msdyn\_affixtype
BESKRIVNING | = | msdyn\_description
