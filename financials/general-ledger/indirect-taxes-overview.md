---
title: "Momsöversikt"
description: "Det här avsnittet innehåller en översikt över momssystemet. Det ger en beskrivning av komponenterna för inställning av moms och hur de arbetar tillsammans."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13111
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 1adee145d705f239e0c663d310234286478fead0
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-overview"></a>Momsöversikt

Det här avsnittet innehåller en översikt över momssystemet. Det ger en beskrivning av komponenterna för inställning av moms och hur de arbetar tillsammans.

<a name="overview"></a>Översikt
--------

Moms framework stöder många typer av indirekta skatter, till exempel moms, moms (VAT), skatt på varor och tjänster (GST), enhetsbaserade avgifter och källskatt. Dessa skatter beräknas och dokumenterade transaktioner för inköp och försäljning. Med jämna mellanrum måste de rapporteras och betalas till skattemyndigheten. 

Följande diagram visar de enheterna för skatteinställning och hur de hör ihop.

[![TaxOverview](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

En momskod måste definieras för varje skatt som ett företag måste redovisa. En momskod lagrar skattesatserna och beräkningsregler för moms. 

Varje momskod måste vara länkad till en momskvittningsperiod. Momskvittningsperiodens definierar intervallerna med vilka moms rapporteras och betalas till skattemyndigheten. Varje momskvittningsperiod måste vara länkad till en skattemyndighet. En skattemyndighet representerar enheten som moms rapporteras och betalas till. Den definierar också utseendet på momsrapporten. Momsmyndigheter kan relateras till leverantörskonton. 

Varje momskod måste också vara länkad till en redovisningsbokföringsgrupp. En redovisningsbokföringgrupp anger huvudkontona som belopp för momskoderna som ska bokföras på. 

Valfria momsrapporteringkoder kan också anges. Dessa kan tilldelas i momskoder för de olika typer av belopp som har beräknats för momskoden. Rapporten **Momsbetalning per kod** visar summan per momsrapporteringskod för given momskvittningsperiod och givet intervall. 

Varje momspliktig transaktion som måste beräknas och bokföras måste ha en momsgrupp och en artikelmomsgrupp. Momsgrupper är relaterade till en part (exempelvis kund eller leverantör) för transaktionen, medan artikelmomsgrupper är kopplade till resursen (exempelvis artikel eller anskaffningskategori) för transaktionen. Momsgrupper innehåller en lista med momskoder. Momskoderna i både momsgruppen och artikelmomsgruppen för en transaktion är momskoden som gäller för den transaktionen. 

I tabellen nedan beskrivs enheterna och sekvensen för momsinställningar.

| Inställningsaktivitet                                                  | Nödvändig/frivillig och beskrivning                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Skapa huvudkonton.                                           | Obligatoriskt. Innan du kan ställa in momsfunktionerna måste du skapa huvudkontona som företaget använder för att betala och registrera skatter.                                                                                                                                                                             |
| Ställ in redovisningsbokföringsgrupper för moms.                     | Obligatoriskt. Redovisningsbokföringsgrupper definierar huvudkontona för att registrera och betala moms.                                                                                                                                                                                                                            |
| Ställ in momsmyndigheter.                                   | Obligatoriskt. Momsmyndigheter är de enheter som moms måste rapporteras och betalas till.                                                                                                                                                                                                                                   |
| Ställ in momskvittningsperioder.                            | Obligatoriskt. Momskvittningsperioder innehåller information om när och hur ofta moms måste rapporteras och betalas. De är relaterad till en momsmyndighet.                                                                                                                                                       |
| Ställ in momsrapporteringskoder.                               | Valfritt. Momsrapporteringskoder kan tilldelas till momskoder för rapport av belopp för flera momskoder under en momsrapporteringskod.                                                                                                                                                                 |
| Ställ in momskoder.                                         | Obligatoriskt. Momskoder lagrar skattesatserna och beräkningsregler för varje moms. Momskoder är relaterade till en momskvittningsperiod och en redovisningsbokföringsgrupp.                                                                                                                                        |
| Ställa in momsgrupper.                                        | Obligatoriskt. Momsgrupper innehåller en lista med försäljningskoder som gäller för parten (kund eller leverantör) för en transaktion. För en given transaktion bestämmer skärningspunkten för momskoder i momsgruppen och artikelmomsgruppen momskoderna som gäller för den transaktionen.                  |
| Ställ in artikelmomsgrupper.                                   | Obligatoriskt. Artikelmomsgrupper innehåller en lista med försäljningskoder som gäller för resursen (produkt, tjänst och så vidare) för en transaktion. För en given transaktion bestämmer skärningspunkten för momskoder i momsgruppen och artikelmomsgruppen momskoderna som gäller för den transaktionen. |
| Ställ in momsparametrar på ansökningsparametersidorna. | Obligatoriskt. Olika områden som till exempel Redovisning och Leverantörsreskontra, Kundreskontra, måste ställa in parametrar för korrekt beräkning av indirekta skatter. Även om de flesta av dessa parametrar har standardvärden måste de ändras så att de passar för varje företags behov.                                          |

## <a name="sales-tax-on-transactions"></a>Moms på transaktioner
På varje transaktion (försäljnings-/inköpsdokumentrader, journaler och så vidare) måste du ange en momsgrupp och en artikelmomsgrupp för att beräkna moms. Standardgrupper anges i huvuddata (till exempel, kund, leverantör, artikel och anskaffningskategori), men du kan manuellt ändra grupperna för en transaktion, om du måste. Båda grupperna innehåller en lista med momskoder och skärningspunkten av båda listorna med momskoder avgör listan med relevanta momskoder för transaktionen. 

På varje transaktion kan du slå upp den beräknade momsen genom att öppna sidan **Momstransaktion**. Du kan slå upp momsen för en dokumentrad eller för hela dokumentet. För vissa dokument (exempelvis,leverantörsfaktura och allmänna journaler) kan du justera den beräknade momsen om originaldokumentet visar avvikande belopp.

## <a name="sales-tax-settlement-and-reporting"></a>Momskvittning och rapportering
Moms måste rapporteras och betalas till skattemyndigheten med regelbundna intervall (månad, kvartal och så vidare). Microsoft Dynamics 365 för operationer innehåller funktioner som kan du kvitta skattebelopp för intervallet och saldon till avräkningskontot skatt enligt redovisningsbokföringsgrupper motbokas. Du kan använda den här funktionen på det **kvitta och bokföra moms** sida. Du måste ange en momskvittningsperiod som moms som ska betalas för. 

När momsen har betalats, ska saldot för momskvittningskontot balanseras mot bankkontot. Om skattemyndigheten som anges i momskvittningsperioden hör till ett annat leverantörskonto, bokförs momssaldot som en öppen leverantörsfaktura och inkluderas i det vanliga betalningsförslaget.

## <a name="conditional-sales-tax"></a>Villkorsmoms
Villkorsmoms är moms som ska betalas proportionellt mot det faktiska beloppet som betalas på en faktura. Däremot beräknas standardmoms vid faktureringstillfället. Villkorsmoms måste betalas till skattemyndigheten när betalningen bokförs, inte när fakturan bokförs. När fakturan bokförs rapporteras transaktionen i boken momsrapporten. Transaktionen måste vara undantagen från betalning av momsrapporten. 

Om du markerar kryssrutan villkorsmoms i formuläret Allmänna redovisningsparametrar kan ingen moms dras tills du har betalt fakturan. Detta är ett juridiskt krav i vissa länder/regioner.

> [!NOTE]
> När du markerar kryssrutan villkorsmoms måste du ställa in momskoder och momsgrupper och även skapa redovisningsbokföringsgrupper för att stödja formulärets funktionalitet. |

###  <a name="example"></a>Exempel

Du betalar in moms varje månad. Den 15 juni skapar en kundfaktura på 10 000 plus moms.
-   Momsen är 25 procent eller 2 500.
-   Fakturans förfaller den 30 juli.

Du skulle normalt behöva betala in 2 500 till skattemyndigheten när fakturan bokförs i juni, även om du inte har fått betalningen från kunden. 

Men om du använder en villkorsmoms kvitta du med skattemyndigheten när du får betalningen från kunden den 30 juli.


