---
title: "Momsöversikt"
description: "Det här ämnet innehåller en översikt över momssystemet. Det ger en beskrivning av komponenterna för inställning av moms och hur de arbetar tillsammans."
author: twheeloc
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, Retail
ms.custom: 13111
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 02d28aef2316d7cfe5ad4eb45272dc1a22c96789
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="sales-tax-overview"></a>Momsöversikt

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

Det här ämnet innehåller en översikt över momssystemet. Det ger en beskrivning av komponenterna för inställning av moms och hur de arbetar tillsammans.

<a name="overview"></a>Översikt
--------

Ramverket för moms stöder många typer av indirekta skatter, till exempel moms/mervärdesskatt, skatt på varor och tjänster (GST), enhetsbaserade avgifter och källskatt. Dessa skatter beräknas och dokumenteras i samband med inköps- och försäljningstransaktioner. Dessa måste regelbundet rapporteras och betalas till skattemyndigheten. 

Följande diagram visar de enheterna för skatteinställning och hur de hör ihop.

[![TaxOverview](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

För varje momstyp som ett företag redovisar redovisa måste en momskod anges. En momskod lagrar skattesatserna och beräkningsregler för moms. 

Varje momskod måste vara länkad till en momskvittningsperiod. Momskvittningsperiodens definierar intervallerna med vilka moms rapporteras och betalas till skattemyndigheten. Varje momskvittningsperiod måste vara länkad till en skattemyndighet. En skattemyndighet representerar enheten som moms rapporteras och betalas till. Den definierar också utseendet på momsrapporten. Momsmyndigheter kan relateras till leverantörskonton. Mer information finns i [Ställ in moms för kvittningsperioder](tasks/set-up-sales-tax-settlement-periods.md).

Varje momskod måste också vara länkad till en redovisningsbokföringsgrupp. En redovisningsbokföringgrupp anger huvudkontona som belopp för momskoderna som ska bokföras på. 

Valfria momsrapporteringkoder kan också anges. Dessa kan tilldelas i momskoder för de olika typer av belopp som har beräknats för momskoden. Rapporten **Momsbetalning per kod** visar summan per momsrapporteringskod för given momskvittningsperiod och givet intervall. 

Varje momspliktig transaktion som måste beräknas och bokföras måste ha en momsgrupp och en artikelmomsgrupp. Momsgrupper är relaterade till en part (exempelvis kund eller leverantör) för transaktionen, medan artikelmomsgrupper är kopplade till resursen (exempelvis artikel eller anskaffningskategori) för transaktionen. Momsgrupper innehåller en lista med momskoder. Momskoderna i både momsgruppen och artikelmomsgruppen för en transaktion är momskoden som gäller för den transaktionen. 

I tabellen nedan beskrivs enheterna och sekvensen för momsinställningar.

| Inställningsaktivitet                                                  | Nödvändig/frivillig och beskrivning                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Skapa huvudkonton.                                           | Obligatoriskt. Innan du kan ställa in momsfunktionerna måste du skapa huvudkontona som företaget använder för att betala och registrera skatter.                                                                                                                                                                             |
| Ställ in redovisningsbokföringsgrupper för moms.                     | Obligatoriskt. Redovisningsbokföringsgrupper definierar huvudkontona för att registrera och betala moms.   Mer information finns i [Ställ in redovisningsbokföringsgrupper för moms](tasks/set-up-ledger-posting-groups-sales-tax.md).                                                                                 |
| Ställ in momsmyndigheter.                                   | Obligatoriskt. Momsmyndigheter är de enheter som moms måste rapporteras och betalas till.    Mer information finns i [Ställ in skattemyndigheter](tasks/set-up-sales-tax-authorities.md).                                                                                                                                          |
| Ställ in momskvittningsperioder.                            | Obligatoriskt. Momskvittningsperioder innehåller information om när och hur ofta moms måste rapporteras och betalas. De är relaterad till en momsmyndighet.                                                                                                                                                       |
| Ställ in momsrapporteringskoder.                               | Valfritt. Momsrapporteringskoder kan tilldelas till momskoder för rapport av belopp för flera momskoder under en momsrapporteringskod. Mer information finns i [Ställ in momsrapporteringskoder](tasks/set-up-sales-tax-reporting-codes.md).                                         |
| Ställ in momskoder.                                         | Obligatoriskt. Momskoder lagrar skattesatserna och beräkningsregler för varje moms. Momskoder är relaterade till en momskvittningsperiod och en redovisningsbokföringsgrupp. Mer information finns i [Ställ in momskoder](tasks/set-up-sales-tax-codes.md).                                |
| Ställa in momsgrupper.                                        | Obligatoriskt. Momsgrupper innehåller en lista med försäljningskoder som gäller för parten (kund eller leverantör) för en transaktion. För en given transaktion bestämmer skärningspunkten för momskoder i momsgruppen och artikelmomsgruppen momskoderna som gäller för den transaktionen.                  |
| Ställ in artikelmomsgrupper.                                   | Obligatoriskt. Artikelmomsgrupper innehåller en lista med försäljningskoder som gäller för resursen (produkt, tjänst och så vidare) för en transaktion. För en given transaktion bestämmer skärningspunkten för momskoder i momsgruppen och artikelmomsgruppen momskoderna som gäller för den transaktionen. Mer information, se [Ange momsgrupper och artikelmomsgruppe](tasks/set-up-sales-tax-groups-item-sales-tax-groups.md). |
| Ställ in momsparametrar på ansökningsparametersidorna. | Obligatoriskt. Olika områden som till exempel Redovisning och Leverantörsreskontra, Kundreskontra, måste ställa in parametrar för korrekt beräkning av indirekta skatter. Även om de flesta av dessa parametrar har standardvärden måste de ändras så att de passar för varje företags behov.                                          |

## <a name="sales-tax-on-transactions"></a>Moms på transaktioner
På varje transaktion (försäljnings-/inköpsdokumentrader, journaler och så vidare) måste du ange en momsgrupp och en artikelmomsgrupp för att beräkna moms. Standardgrupper anges i huvuddata (till exempel, kund, leverantör, artikel och anskaffningskategori), men du kan manuellt ändra grupperna för en transaktion, om du måste. Båda grupperna innehåller en lista med momskoder och skärningspunkten av båda listorna med momskoder avgör listan med relevanta momskoder för transaktionen. 

På varje transaktion kan du slå upp den beräknade momsen genom att öppna sidan **Momstransaktion**. Du kan slå upp momsen för en dokumentrad eller för hela dokumentet. För vissa dokument (exempelvis,leverantörsfaktura och allmänna journaler) kan du justera den beräknade momsen om originaldokumentet visar avvikande belopp.

## <a name="sales-tax-settlement-and-reporting"></a>Momskvittning och rapportering
Moms måste rapporteras och betalas till skattemyndigheten med regelbundna intervall (månad, kvartal och så vidare). Microsoft Dynamics 365 for Finance and Operations innehåller de funktioner som gör att du kan kvitta momskonton för intervallet, och förskjuta saldon till momskvittningskontot, enligt uppgifterna i redovisningsbokföringsgrupperna. Du kan använda den här funktionen på sidan **Kvitta och bokföra moms**. Du måste ange en momskvittningsperiod för vilken moms ska kvittas. 

När momsen har betalats, ska saldot för momskvittningskontot balanseras mot bankkontot. Om skattemyndigheten som anges i momskvittningsperioden hör till ett annat leverantörskonto, bokförs momssaldot som en öppen leverantörsfaktura och inkluderas i det vanliga betalningsförslaget.

## <a name="conditional-sales-tax"></a>Villkorsmoms
Villkorsmoms är moms som ska betalas proportionellt mot det faktiska beloppet som betalas på en faktura. Däremot beräknas standardmoms vid faktureringstillfället. Villkorsmoms måste betalas till skattemyndigheten när betalningen bokförs, inte när fakturan bokförs. När fakturan bokförs måste transaktionen rapporteras momsboksrapporten. Transaktionen måste emellertid vara undantagen ur momsbetalningsrapporten. 

Om du markerar kryssrutan Villkorsmoms i formuläret Allmänna redovisningsparametrar, kan ingen moms dras förrän du har betalt fakturan. Detta är ett juridiskt krav i vissa länder/regioner.

> [!NOTE]
> När du väljer kryssrutan för villkorsmoms måste du ställa in momskoder, och momsgrupper, samt även skapa redovisningsbokföringsgrupper för att kunna använda funktionen. |

###  <a name="example"></a>Exempel

Du kvittar momsen varje månad. Den 15 juni skapar du en kundfaktura på 10 000 plus moms.
-   Momsen är 25 procent, eller 2 500.
-   Fakturabetalningen förfaller den 30 juli.

Du skulle normalt behöva betala in 2 500 till skattemyndigheten när fakturan bokförs i juni, även om du inte har fått betalningen från kunden. 

Om du emellertid använder villkorsmoms kvittar du med skattemyndigheten när du får betalningen från kunden den 30 juli.


Mer information finns i [Ställ in källskatt](tasks/set-up-withholding-tax.md).

