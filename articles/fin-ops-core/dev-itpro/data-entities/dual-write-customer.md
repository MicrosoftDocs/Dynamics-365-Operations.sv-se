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
ms.openlocfilehash: 09d985e5c6816ec0c718aaf418f4e85fb828f1c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769693"
---
# <a name="integrated-customer-master"></a>Integrerat kundhuvud

[!include [banner](../includes/banner.md)]

Det är typiskt för kundposter som ska hanteras i mer än ett program. Försäljningsaktivitet kan till exempel föra in kommersiella kundposter via ett Sales-program och e-handels- eller butiksförsäljning kan ta in kundposter via ett Finance and Operations-program. Oavsett var kundposten har sitt ursprung integreras den bakom kulisserna i programgränser och infrastrukturskillnader. Integrerad kundhantering hjälper till att hantera scenarier med flera hanteringar och ger en heltäckande vy av kunden till Dynamics 365 programsvit.

## <a name="customer-data-flow"></a>Kunddataflöde

*Kunden* är ett väldefinierat begrepp i program. Därför innebär integreringen av kunddata bara harmonisering av kundkonceptet mellan de två programmen. Illustrationen som följer visar kunddataflödet.

![Kunddataflöde](media/dual-write-customer-data-flow.png)

Kunder kan i stort sett delas in i två typer: kommersiella/organisatoriska kunder och konsumenter/slutanvändare. Dessa två typer av kunder lagras och hanteras på olika sätt i Finance and Operations och Common Data Service.

I Finance and Operations hanteras både kommersiella/organisatoriska kunder och konsumenter/slutanvändare i en enda tabell som kallas **CustTable** (CustomerCustomerV3Entity) och de klassificeras baserat på attributet **Typ**. (Om **typ** är inställd på **organisation** är kunden en kommersiell/organisatorisk kund och om **typ** är inställd på **person** är kunden en konsument/slutanvändare.) Den primära kontaktpersonens information hanteras via entiteten SMMContactPersonEntity.

I Common Data Service hanteras kommersiella/organisatoriska kunder i kontoentiteten och identifieras som kunder när attributet **RelationshipType** är inställt på **kund**. Både konsumenter/slutanvändare och kontaktpersonen representeras av kontaktentiteten. För att ge en tydlig åtskillnad mellan en konsument/slutanvändare och en kontaktperson har entiteten **kontakt** en boolesk flagga som heter **säljbar**. När **säljbar** är **sant** är kontakten en konsument/slutanvändare och offerter och order kan skapas för den kontakten. När **säljbar** är **falskt** är kontakten bara en primär kontaktperson för en kund.

När en icke-säljbar kontakt deltar i en offert eller orderprocess är **säljbart** inställt på **sant** för att flagga kontakten som en säljbar kontakt. En kontakt som har blivit en säljbar kontakt förblir en säljbar kontakt.

## <a name="templates"></a>Mallar

Kunddata innehåller all information om kunden, till exempel kundgruppen, adresser, kontaktinformation, betalningsprofil, fakturaprofil och förmånsstatus. En samling entitetsmappningar fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Finance and Operations-appar | Andra Dynamics 365-appar         | Beskrivning
----------------------------|---------------------------------|------------
CDS-kontakter V2             | kontakter                        | Den här mallen synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer.
Kundgrupper             | msdyn_customergroups            | Den här mallen synkroniserar kundgruppinformation.
Kundbetalningsmetod     | msdyn_customerpaymentmethods    | Den här mallen synkroniserar information om kundbetalningsmetod.
Kunder V3                | konton                        | Den här mallen synkroniserar kundhuvudinformation för kommersiella och organisatoriska kunder.
Kunder V3                | kontakter                        | Den här mallen synkroniserar kundhuvuddata för användare och slutanvändare.
Förmånskort                | msdyn_loyaltycards              | Den här mallen synkroniserar information om förmånskort.
Namnaffix                | msdyn_nameaffixes               | Mallen synkroniserar referensdata för namnaffix för både kunder och leverantörer.
Betalningsdagsrader – CDS V2    | msdyn_paymentdaylines           | Mallen synkroniserar referensdata för betalningsplanrader för både kunder och leverantörer.
Betalningsdagar – CDS            | msdyn_paymentdays               | Mallen synkroniserar referensdata för betalningsdagar för både kunder och leverantörer.
Betalningsplanrader      | msdyn_paymentschedulelines      | Synkronisera referensdata för betalningsplanrader för både kunder och leverantörer.
Betalningsplan            | msdyn_paymentschedules          | Mallen synkroniserar referensdata för betalningsplan för både kunder och leverantörer.
Betalningsvillkor            | msdyn_paymentterms              | Mallen synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer.

[!include [banner](../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](dual-write/CDSContactsV2-contacts.md)]

[!include [mapping customer group](dual-write/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](dual-write/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](dual-write/CustomersV3-accounts.md)]

[!include [mapping customer contacts](dual-write/CustomersV3-contacts.md)]

[!include [mapping loyalty card](dual-write/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](dual-write/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](dual-write/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](dual-write/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](dual-write/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](dual-write/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](dual-write/TermsofPayment-msdyn-paymentterms.md)]
