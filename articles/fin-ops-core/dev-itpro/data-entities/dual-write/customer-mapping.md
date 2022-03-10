---
title: Integrerat kundhuvud
description: I det här avsnittet beskrivs integreringen av kunddata mellan Finance and Operations och Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 41e4b6c192b6125a144e4d5ef952ba0975821d44
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063299"
---
# <a name="integrated-customer-master"></a>Integrerad kundmaster

[!include [banner](../../includes/banner.md)]



Kunddata kan hanteras i fler än ett Dynamics 365-program. En kundrad kan till exempel ha sitt ursprung trots att det finns försäljningsaktiviteter i Dynamics 365 Sales (en kundengagemangsapp) eller så kan en rad ha sitt ursprung i detaljhandelsaktivitet i Dynamics 365 Commerce (en Finance and operations-app). Oavsett var informationen kommer från kunden integreras den bakom kulisserna. Integrerad kund huvud ger dig flexibiliteten att hantera kunddata i alla Dynamics 365-program och ger en omfattande översikt över kunden över Dynamics 365-programpaketet.

## <a name="customer-data-flow"></a>Kunddataflöde

*Kunden* är ett väldefinierat begrepp i program. Därför innebär integreringen av kunddata bara harmonisering av kundkonceptet mellan de två programmen. Illustrationen som följer visar kunddataflödet.

![Kunddataflöde.](media/dual-write-customer-data-flow.png)

Kunder kan i stort sett delas in i två typer: kommersiella/organisatoriska kunder och konsumenter/slutanvändare. Dessa två typer av kunder lagras och hanteras på olika sätt i Finance and Operations och Dataverse.

I Ekonomi och Drift hanteras både kommersiella/organisatoriska kunder och konsumenter/slutanvändare i en enda tabell som kallas **CustTable** (CustCustomerV3Entity) och de klassificeras baserat på attributet **Typ**. (Om **typ** är inställd på **organisation** är kunden en kommersiell/organisatorisk kund och om **typ** är inställd på **person** är kunden en konsument/slutanvändare.) Den primära kontaktpersonens information hanteras via tabellen SMMContactPersonEntity.

I Dataverse hanteras kommersiella/organisatoriska kunder i kontotabellen och identifieras som kunder när attributet **RelationshipType** är inställt på **kund**. Både konsumenter/slutanvändare och kontaktpersonen representeras av kontakttabellen. För att ge en tydlig åtskillnad mellan en konsument/slutanvändare och en kontaktperson har tabellen **kontakt** en boolesk flagga som heter **säljbar**. När **säljbar** är **sant** är kontakten en konsument/slutanvändare och offerter och order kan skapas för den kontakten. När **säljbar** är **falskt** är kontakten bara en primär kontaktperson för en kund.

När en icke-säljbar kontakt deltar i en offert eller orderprocess är **säljbart** inställt på **sant** för att flagga kontakten som en säljbar kontakt. En kontakt som har blivit en säljbar kontakt förblir en säljbar kontakt.

## <a name="templates"></a>Mallar

Kunddata innehåller all information om kunden, till exempel kundgruppen, adresser, kontaktinformation, betalningsprofil, fakturaprofil och förmånsstatus. En samling tabellmappningar fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Finance and Operations-appar | Kundengagemangsappar         | beskrivning
----------------------------|---------------------------------|------------
[CDS-kontakter V2](mapping-reference.md#115) | kontakter | Den här mallen synkroniserar all primär, sekundär och tertiär kontaktinformation för både kunder och leverantörer.
[Kundgrupper](mapping-reference.md#126) | msdyn_customergroups | Den här mallen synkroniserar kundgruppinformation.
[Kundbetalningsmetod](mapping-reference.md#127) | msdyn_customerpaymentmethods | Den här mallen synkroniserar information om kundbetalningsmetod.
[Kunder V3](mapping-reference.md#101) | konton | Den här mallen synkroniserar kundhuvudinformation för kommersiella och organisatoriska kunder.
[Kunder V3](mapping-reference.md#116) | kontakter | Den här mallen synkroniserar kundhuvuddata för användare och slutanvändare.
[Namnaffix](mapping-reference.md#155) | msdyn_nameaffixes | Mallen synkroniserar referensdata för namnaffix för både kunder och leverantörer.
[Betalningsdagsrader – CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Mallen synkroniserar referensdata för betalningsplanrader för både kunder och leverantörer.
[Betalningsdagar – CDS](mapping-reference.md#158) | msdyn_paymentdays | Mallen synkroniserar referensdata för betalningsdagar för både kunder och leverantörer.
[Betalningsplanrader](mapping-reference.md#159) | msdyn_paymentschedulelines | Synkronisera referensdata för betalningsplanrader för både kunder och leverantörer.
[Betalningsplan](mapping-reference.md#160) | msdyn_paymentschedules | Mallen synkroniserar referensdata för betalningsplan för både kunder och leverantörer.
[Betalningsvillkor](mapping-reference.md#161) | msdyn_paymentterms | Mallen synkroniserar referensdata för betalningsvillkor för både kunder och leverantörer.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
