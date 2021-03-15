---
title: Exempel på bokföringsdefinitioner
description: Denna artikel innehåller exempel som visar hur du använder bokföringsdefinitioner för inköpsorderinteckningar och budgetanslag.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 751be602b701ac7a5b593404bf655e1a9852f863
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990499"
---
# <a name="posting-definition-examples"></a>Exempel: bokföringsdefinitioner

[!include [banner](../includes/banner.md)]

Denna artikel innehåller exempel som visar hur du använder bokföringsdefinitioner för inköpsorderinteckningar och budgetanslag.

Innan du läser det här avsnittet, ska du känna till bokföringsdefinitioner och bokföringsdefinitioner för transaktioner. Mer information finns i [Bokföringsdefinitioner](posting-definitions.md). Följande exempel kan ställas in på sidan **Bokföringsdefinitioner**. Varje exempel innehåller följande ämnen:

-   Bokföringsdefinition – matchvillkor
-   Bokföringsdefinition – genererade poster
-   Transaktioner med konton, dimensionsvärden och belopp
-   Redovisningposter som genereras med bokföringsdefinitionen

När en matchaning uppstår mellan kontona och dimensionsvärdena i fönstret **Matchvillkor** för bokföringsdefinitionen och konton och dimensionsvärden på transaktionen, redovisningsposter genereras baserat på fönstret **Genererade poster** för bokföringsdefinitionen. 
> [!NOTE]
> Använd sidan **Bokföringsdefinitioner för transaktioner** för att koppla en bokföringsdefinition till en specifik transaktionstyp. När du associerar en bokföringsdefinition med en transaktionstyp och väljer **Använd bokföringsdefinitioner** på sidan **Redovisningsparametrar**, måste samtliga transaktioner av vald transaktionstyp använda bokföringsdefinitioner.

## <a name="example-purchase-order-encumbrances"></a>Exempel: Inköpsorderinteckningar
När du aktiverar inteckningsbearbetning genom att välja **Aktivera inteckningsprocess** på sidan **Allmänna redovisningsparametrar**, måste bokföringsdefinitioner användas för att registrera inteckningar i redovisningen för alla konton som ska reserveras. I de flesta fall reserveras alla utgiftskonton i balansräkningen. 

Bokföringsdefinitioner för inteckningar är inställda för modulen **Inköp** på sidan **Bokföringsdefinitioner**. I området **Inköp** på sidan **Bokföringsdefinitioner för transaktioner** kan du välja sidan **Inköpsorder** transaktionstyp för att associera bokföringsdefinitionen med inköpsorder. 

Alla verifikationstransaktioner för inköpsorderinteckningar måste balanseras (detta betyder att debet måste vara lika med kredit), i varje unik dimension på en verifikation.

### <a name="posting-definition--match-criteria"></a>Bokföringsdefinition – matchvillkor

| Kontostruktur       | Matcha kontonummer | Prioritet  |
|-------------------------|----------------------|----------|
| Kontostruktur – Resultat | \*                   | 1        |

<em>Ett mellanrumsvärde i fältet **Matchningskontonummer</em>* betyder att alla matchningskonton i den definierade kontostrukturen är en del av matchningsregeln.

### <a name="posting-definition--generated-entries"></a>Bokföringsdefinition – genererade poster

| Kontostruktur | Genererat kontonummer                    | Debet/kredit har skapats |
|-------------------|---------------------------------------------|------------------------|
| Saldo           | 300143 – (Inteckningkonto)             | Samma                   |
| Saldo           | 300144 – - (Reservera för inteckningkonto) | Balanserar              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transaktioner med konton, dimensionsvärden och belopp

Kontona och dimensionsvärden kommer antingen från redovisningsfördelningarna, som du anger för en inköpsorderrad, eller från konton och dimensioner som genereras automatiskt baserat på standardinställningarna för leverantörer, artiklar, kategorier och dimensionsmallar.

| Konto + dimensioner           | Debet  | Kredit | Kommentar |
|--------------------------------|--------|--------|---------|
| 606400-OU\_1-OU\_3566-Training | 250.00 |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Redovisningposter som genereras med bokföringsdefinitionen

Genererade redovisningsposter skapas för att registrera inteckningarna.

| Konto + dimensioner           | Debet  | Kredit | Kommentar |
|--------------------------------|--------|--------|---------|
| 300143-OU\_1-OU\_3566-utbildning | 250.00 |        |         |
| 300144-OU\_1-OU\_3566-Training |        | 250.00 |         |

I det här exemplet matchar alla konton, som är en del av kontostrukturen – Resultat matchar bokföringsdefinitionvillkoren. När 606500-OU\_1-OU\_3566-utbildning ska utvärderas, genereras därför poster för de konton som anges i fönstret **Genererade poster** för bokföringsdefinitionen.

## <a name="example-budget-appropriations"></a>Exempel: Budgetanslag
När du aktiverar budgettransaktioner genom att välja **Aktivera budgetanslag** på sidan **Allmänna redovisningsparametrar**, måste bokföringsdefinitioner användas för att bokföra budgetregisterposter i redovisningen. När en budgetkontrollkonfiguration är aktiv och aktiveras, kan bokföringsdefinitioner och transaktionbokföringsdefinitioner användas som stöd för registreringen av poster för anslag, ändringar, överföringar, projekt, anläggningstillgångar och leverans- och efterfrågeprognoser i redovisningen. 

Om du vill ställa in en bokföringsdefinition för budgetregisterposter som har budgettypen **Ursprunglig budget** och som har anslag aktiverade, välj modulen **Budget** på sidan **Bokföringsdefinitioner** . Sedan i området **Budget** på sidan **Bokföringsdefinitioner för transaktioner** kan du använda budgetkoder för att koppla bokföringsdefinitionen med budgetregisterposter som ha budgettypen **Ursprunglig budget** 

När budgetanslag och budgeterade bokföringsdefinitioner aktiveras, registreras de här registerposterna för budgetkontroll och i redovisningen.

### <a name="posting-definition--match-criteria"></a>Bokföringsdefinition – matchvillkor

| Kontostruktur       | Matcha kontonummer | Prioritet  |
|-------------------------|----------------------|----------|
| Kontostruktur – Resultat | \*                   | 1        |

<em>Ett mellanrumsvärde i fältet **Matchningskontonummer</em>* betyder att alla matchningskonton i den definierade kontostrukturen är en del av matchningsregeln.

### <a name="posting-definition--generated-entries"></a>Bokföringsdefinition – genererade poster

| Kontostruktur | Genererat kontonummer              | Debet/kredit har skapats |
|-------------------|---------------------------------------|------------------------|
| Kontostruktur | 300145 – - (uppskattad intäkt) | Samma                   |
| Kontostruktur | 300146 – (Anslagskonto)     | Balanserar              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transaktioner med konton, dimensionsvärden och belopp

Du anger konton, dimensionsvärden och belopp för budgetkontoposten på sidan **Budgetregisterpost**.

| Konto + dimensioner           | Debet | Kredit | Kommentar |
|--------------------------------|-------|--------|---------|
| 606400-OU\_1-OU\_3566-Training |       | 250.00 |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Redovisningposter som genereras med bokföringsdefinitionen

Genererade redovisningsposter skapas för att registrera den ursprungliga budgeten i varje dimension.

| Konto + dimensioner           | Debet  | Kredit | Kommentar |
|--------------------------------|--------|--------|---------|
| 300145-OU\_1-OU\_3566-Training |        | 250.00 |         |
| 300146-OU\_1-OU\_3566-Training | 250.00 |        |         |

I det här exemplet matchar alla konton, som är en del av kontostrukturen – Resultat matchar bokföringsdefinitionvillkoren. När 606400-OU\_1-OU\_3566-utbildning utvärderas, skapas därför genererade bokföringsposter.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]