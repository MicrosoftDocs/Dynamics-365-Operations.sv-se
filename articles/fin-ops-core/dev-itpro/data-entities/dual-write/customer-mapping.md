---
title: Integrerat kundhuvud
description: I det här avsnittet beskrivs integreringen av kunddata mellan Finance and Operations och Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b7e9cd27bb918dc3a6088b45803329deb01a864e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744412"
---
# <a name="integrated-customer-master"></a>Integrerad kundmaster

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


Kunddata kan hanteras i fler än ett Dynamics 365-program. En kundrad kan till exempel ha sitt ursprung trots att det finns försäljningsaktiviteter i Dynamics 365 Sales (en modellstyrd app i Dynamics 365), eller så kan en rad ha sitt ursprung i detaljhandelsaktivitet i Dynamics 365 Commerce (Finance and Operations-app). Oavsett var informationen kommer från kunden integreras den bakom kulisserna. Integrerad kund huvud ger dig flexibiliteten att hantera kunddata i alla Dynamics 365-program och ger en omfattande översikt över kunden över Dynamics 365-programpaketet.

## <a name="customer-data-flow"></a>Kunddataflöde

*Kunden* är ett väldefinierat begrepp i program. Därför innebär integreringen av kunddata bara harmonisering av kundkonceptet mellan de två programmen. Illustrationen som följer visar kunddataflödet.

![Kunddataflöde](media/dual-write-customer-data-flow.png)

Kunder kan i stort sett delas in i två typer: kommersiella/organisatoriska kunder och konsumenter/slutanvändare. Dessa två typer av kunder lagras och hanteras på olika sätt i Finance and Operations och Dataverse.

I Finance and Operations hanteras både kommersiella/organisatoriska kunder och konsumenter/slutanvändare i en enda tabell som kallas **CustTable** (CustCustomerV3Entity) och de klassificeras baserat på attributet **Typ**. (Om **typ** är inställd på **organisation** är kunden en kommersiell/organisatorisk kund och om **typ** är inställd på **person** är kunden en konsument/slutanvändare.) Den primära kontaktpersonens information hanteras via tabellen SMMContactPersonEntity.

I Dataverse hanteras kommersiella/organisatoriska kunder i kontotabellen och identifieras som kunder när attributet **RelationshipType** är inställt på **kund**. Både konsumenter/slutanvändare och kontaktpersonen representeras av kontakttabellen. För att ge en tydlig åtskillnad mellan en konsument/slutanvändare och en kontaktperson har tabellen **kontakt** en boolesk flagga som heter **säljbar**. När **säljbar** är **sant** är kontakten en konsument/slutanvändare och offerter och order kan skapas för den kontakten. När **säljbar** är **falskt** är kontakten bara en primär kontaktperson för en kund.

När en icke-säljbar kontakt deltar i en offert eller orderprocess är **säljbart** inställt på **sant** för att flagga kontakten som en säljbar kontakt. En kontakt som har blivit en säljbar kontakt förblir en säljbar kontakt.

## <a name="templates"></a>Mallar

Kunddata innehåller all information om kunden, till exempel kundgruppen, adresser, kontaktinformation, betalningsprofil, fakturaprofil och förmånsstatus. En samling tabellmappningar fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Finance and Operations-appar | Andra Dynamics 365-appar         | Beskrivning
----------------------------|---------------------------------|------------
CDS-kontakter V2             | kontakter                        | Den här mallen synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer.
Kundgrupper             | msdyn_customergroups            | Den här mallen synkroniserar kundgruppinformation.
Kundbetalningsmetod     | msdyn_customerpaymentmethods    | Den här mallen synkroniserar information om kundbetalningsmetod.
Kunder V3                | konton                        | Den här mallen synkroniserar kundhuvudinformation för kommersiella och organisatoriska kunder.
Kunder V3                | kontakter                        | Den här mallen synkroniserar kundhuvuddata för användare och slutanvändare.
Namnaffix                | msdyn_nameaffixes               | Mallen synkroniserar referensdata för namnaffix för både kunder och leverantörer.
Betalningsdagsrader – CDS V2    | msdyn_paymentdaylines           | Mallen synkroniserar referensdata för betalningsplanrader för både kunder och leverantörer.
Betalningsdagar – CDS            | msdyn_paymentdays               | Mallen synkroniserar referensdata för betalningsdagar för både kunder och leverantörer.
Betalningsplanrader      | msdyn_paymentschedulelines      | Synkronisera referensdata för betalningsplanrader för både kunder och leverantörer.
Betalningsplan            | msdyn_paymentschedules          | Mallen synkroniserar referensdata för betalningsplan för både kunder och leverantörer.
Betalningsvillkor            | msdyn_paymentterms              | Mallen synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer.

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]