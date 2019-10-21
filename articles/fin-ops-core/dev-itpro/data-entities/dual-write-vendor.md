---
title: Integrerat leverantörshuvud
description: I det här avsnittet beskriver integreringen av leverantörsdata mellan Finance and Operations-appar och Common Data Service.
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
ms.openlocfilehash: 2b8d1e872b65f40a63c0771cb95d8d1c0875ca82
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249096"
---
## <a name="integrated-vendor-master"></a>Integrerat leverantörshuvud

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Termen *leverantör* hänvisar till en leverantörsorganisation eller en enskild firma som är en del av leveranskedjeprocessen och som levererar varor för verksamheten. Även om *leverantören* är ett etablerat koncept i Finance and Operations-appar finns inget annat leverantörskoncept i Dynamics 365-appar. I stället överbelastar vissa företag kontoentiteten för att lagra både kundinformation och leverantörsinformation. Andra företag använder ett anpassat leverantörskoncept. Common Data Service-integrationen stöder båda dessa konstruktioner. Därför kan du aktivera någon av konstruktionerna, beroende på ditt affärsscenario.

Integrering av leverantörsdata mellan Finance and Operations-appar och andra Dynamics 365-appar gör att du kan hantera flera data. Oavsett var leverantörsdata har sitt ursprung integreras den bakom kulisserna i programgränser och infrastrukturskillnader. 

### <a name="vendor-data-flow"></a>Leveranstörsdataflöde

Om du vill använda Dynamics 365-appar för leverantörshantering och vill isolera leverantörsinformation från kundinformationen kan du använda den nya leverantörsdesignen.

![Leveranstörsdataflöde](media/dual-write-vendor-data-flow.png)

Om du vill använda andra Dynamics 365-appar för leverantörshantering och vill fortsätta använda kontoentiteten för att lagra leverantörsinformationen kan du använda den nya utökade leverantörsdesignen. I den här designen lagras utökad leverantörsinformation, till exempel leverantörsgrupp och leverantörsbokföringsprofil, i leverantörsdetaljerna.

![Utökat leveranstörsdataflöde](media/dual-write-vendor-detail.jpg)

Leverantörens kontaktinformation liknar kundens kontaktinformation. Bakom kulisserna lagras kontaktpersonens information och hämtas från samma entiteter.

## <a name="templates"></a>Mallar

Leverantörsdata innehåller all information om leverantören, till exempel leverantörsgruppen, adresser, kontaktinformation, betalningsprofil och fakturaprofil. En samling entitetsmappningar fungerar tillsammans under leverantörsdatainteraktion, som visas i följande tabell.

Finance and Operations-appar  | Andra Dynamics 365-appar
------------------------|---------------------------------
Leverantör V2               | Konto
Leverantör V2               | Msdyn\_vendors
CDS-kontakter V2         | Kontakt
Leverantörsgrupper           | Msdyn\_vendorgroups
Betalningsmetod för leverantör   | Msdyn\_vendorpaymentmethods
Betalningsplan        | Msdyn\_paymentschedules
Betalningsplan        | Msdyn\_paymentschedulelines
Betalningsdag – CDS         | Msdyn\_paymentdays
Betalningsdagsrader – CDS   | Msdyn\_paymentdaylines
Betalningsvillkor        | Msdyn\_paymentterms
Namnaffix            | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="vendor-v2-and-account"></a>Leverantör V2 och konto 

Företag som använder kontoentiteten för att lagra leverantörsinformation kan fortsätta att använda den på samma sätt. De kan också dra nytta av de explicita leverantörsfunktioner som kommer på grund av Finance and Operations-appintegrering.

## <a name="vendor-v2-and-msdyn_vendors"></a>Leverantör V2 och Msdyn\_leverantörer

Företag som använder en anpassad lösning för leverantörer kan dra nytta av det färdiga leverantörskoncept som introduceras i Common Data Service på grund av Finance and Operations-appintegrering. 

<!-- ![vendor mappings](media/dual-write-vendors-1.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-2.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-3.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
VENDORACCOUNTNUMBER | = | msdyn\_vendoraccountnumber
VENDORGROUPID | = | msdyn\_vendorgroupid.msdyn\_vendorgroup
VENDORORGANIZATIONNAME | = | msdyn\_name
VENDORPARTYTYPE | \>\< | msdyn\_isperson
PERSONFIRSTNAME | = | msdyn\_firstname
PERSONLASTNAME | = | msdyn\_lastname
CREDITLIMIT | = | msdyn\_vendorcreditlimit
ISFOREIGNENTITY | \>\< | msdyn\_isforeignentity
ISONETIMEVENDOR | \>\< | msdyn\_isonetimevendor
ADDRESSBUILDINGCOMPLIMENT | = | msdyn\_addressbuildingcompliment
PERSONCHILDRENNAMES | = | msdyn\_childrennames
ADDRESSCITY | = | msdyn\_addresscity
ADDRESSCOUNTRYREGIONID | = | msdyn\_addresscountryregionid
ADDRESSCOUNTRYREGIONISOCODE | = | msdyn\_addresscountryregionisocode
ADDRESSCOUNTYID | = | msdyn\_addresscountyid
CREDITRATING | = | msdyn\_creditrating
ADDRESSDESCRIPTION | = | msdyn\_addressdescription
ADDRESSDISTRICTNAME | = | msdyn\_addressdistrictname
DUNSNUMBER | = | msdyn\_dunsnumber
ETHNICORIGINID | = | msdyn\_ethnicorigin
FORMATTEDPRIMARYADDRESS | = | msdyn\_formattedprimaryaddress
PERSONHOBBIES | = | msdyn\_hobbies
PERSONINITIALS | = | msdyn\_initials
LANGUAGEID | = | msdyn\_languageid
PERSONLASTNAMEPREFIX | = | msdyn\_lastnameprefix
PERSONMIDDLENAME | = | msdyn\_middlename
ORGANIZATIONNUMBER | = | msdyn\_organizationnumber
OURACCOUNTNUMBER | = | msdyn\_ourvendoraccountnumber
PAYMENTID | = | msdyn\_paymentid
PERSONPHONETICFIRSTNAME | = | msdyn\_phoneticfirstname
PERSONPHONETICMIDDLENAME | = | msdyn\_phoneticmiddlename
PERSONPHONETICLASTNAME | = | msdyn\_phoneticlastname
ORGANIZATIONPHONETICNAME | = | msdyn\_organizationphoneticname
ADDRESSPOSTBOX | = | msdyn\_addresspostbox
PRIMARYURL | = | msdyn\_primarycontacturl
PRIMARYEMAILADDRESS | = | msdyn\_primaryemailaddress
PRIMARYEMAILADDRESSDESCRIPTION | = | msdyn\_primaryemailaddressdescription
PRIMARYFACEBOOK | = | msdyn\_primaryfacebook
PRIMARYFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYFAXNUMBER | = | msdyn\_primaryfaxnumber
PRIMARYFAXNUMBERDESCRIPTION | = | msdyn\_primaryfaxnumberdescription
PRIMARYFAXNUMBEREXTENSION | = | msdyn\_primaryfaxnumberextension
PRIMARYLINKEDIN | = | msdyn\_primarylinkedin
PRIMARYLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescription
PRIMARYPHONENUMBER | = | msdyn\_pimaryphonenumber
PRIMARYPHONENUMBERDESCRIPTION | = | msdyn\_primaryphonenumberdescription
PRIMARYPHONENUMBEREXTENSION | = | msdyn\_primaryphonenumberextension
PRIMARYTELEX | = | msdyn\_primarytelex
PRIMARYTELEXDESCRIPTION | = | msdyn\_primarytelexdescription
PRIMARYTWITTER | = | msdyn\_primarytwitter
PRIMARYTWITTERDESCRIPTION | = | msdyn\_primarytwitterdescription
PRIMARYURLDESCRIPTION | = | msdyn\_primaryurldescription
PERSONPROFESSIONALSUFFIX | = | msdyn\_professionalsuffix
PERSONPROFESSIONALTITLE | = | msdyn\_professionatitle
ADDRESSSTATEID | = | msdyn\_addressstateid
ADDRESSSTREET | = | msdyn\_addressstreet
ADDRESSSTREETNUMBER | = | msdyn\_addressstreetnumber
VENDORKNOWNASNAME | = | msdyn\_vendorknownasname
ADDRESSZIPCODE | = | msdyn\_addresszipcode
DEFAULTPAYMENTDAYNAME | = | msdyn\_defaultpaymentdayname.msdyn\_name
DEFAULTPAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
DEFAULTPAYMENTTERMSNAME | = | msdyn\_paymentterms.msdyn\_name
HASONLYTAKENBIDS | \>\< | msdyn\_hasonlytakenbids
ISMINORITYOWNED | \>\< | msdyn\_isminorityowned
ISVENDORLOCALLYOWNED | \>\< | msdyn\_isvendorlocallyowned
ISSERVICEVETERANOWNED | \>\< | msdyn\_isserviceveteranowned
ISOWNERDISABLED | \>\< | msdyn\_ownerisdisabled
ISWOMANOWNER | \>\< | msdyn\_womanowner
PERSONANNIVERSARYDAY | = | msdyn\_personanniversaryday
PERSONANNIVERSARYYEAR | = | msdyn\_anniversaryyear
PERSONBIRTHDAY | = | msdyn\_birthday
PERSONBIRTHYEAR | = | msdyn\_birthyear
ORGANIZATIONEMPLOYEEAMOUNT | = | msdyn\_numberofemployees
VENDORHOLDRELEASEDATE | = | msdyn\_vendoronholdreleasedate
VENDORPARTYNUMBER | = | msdyn\_vendorpartynumber
ADDRESSLOCATIONID | = | msdyn\_addresslocationid
PERSONANNIVERSARYMONTH | = | msdyn\_vendorpersonanniversarymonth
PERSONBIRTHMONTH | = | msdyn\_vendorpersonbirthmonth
PERSONMARITALSTATUS | \>\< | msdyn\_maritalstatus
ADDRESSLATITUDE | \>\> | msdyn\_addresslatitude
ADDRESSLONGITUDE | \>\> | msdyn\_addresslongitude
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
CURRENCYCODE | = | msdyn\_currencycode.isocurrencycode
ISVENDORLOCATEDINHUBZONE | \>\< | msdyn\_isvendorlocatedinhubzone
DEFAULTVENDORPAYMENTMETHODNAME | = | msdyn\_vendorpaymentmethod.msdyn\_name
INVOICEVENDORACCOUNTNUMBER | = | msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber
PERSONGENDER | \>\< | msdyn\_gender
AREPRICESINCLUDINGSALESTAX | \>\< | msdyn\_priceincludessalestax
SALESTAXGROUPCODE | = | msdyn\_taxgroup.msdyn\_name
VENDORPRICETOLERANCEGROUPID | = | msdyn\_pricetolerancegroup.msdyn\_groupid

## <a name="contacts"></a>Kontakter

Den här mallen synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer, mellan Finance and Operations-appar och Dynamics 365-appar. Information om entitetsmappningen finns i [integrerat kundhuvud](dual-write-customer.md#contacts).

## <a name="vendor-groups"></a>Leverantörsgrupper

Den här mallen synkroniserar leverantörsgruppinformation mellan Finance and Operations-appar och Dynamics 365-appar.

<!-- ![vendor groups mappings](media/dual-write-vendor-groups.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
DEFAULTPAYMENTTERMNAME | = | msdyn\_paymentterms.msdyn\_name
BESKRIVNING | = | msdyn\_description
VENDORGROUPID | = | msdyn\_vendorgroup
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymentpermname.msdyn\_name

### <a name="vendor-payment-method"></a>Betalningsmetod för leverantör

Den här mallen synkroniserar information om leverantörsbetalningsmetod mellan Finance and Operations-appar och Dynamics 365-appar.

<!-- ![vendor payment method mappings](media/dual-write-vendor-payment-method.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
NAMN | = | msdyn\_name
BESKRIVNING | = | msdyn\_description
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
ALLOWPAYMENTCOPIES | \>\< | msdyn\_allowpaymentcopies
PAYMENTTYPE | \>\< | msdyn\_paymenttype
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
ACCOUNTTYPE | \>\< | msdyn\_accounttype
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingposting
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_postdatedcheckclearingposting
PROMISSORYNOTEDRAFTTYPE | \>\< | msdyn\_promissorynotedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

