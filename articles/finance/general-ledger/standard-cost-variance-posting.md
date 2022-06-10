---
title: Bokföring av standardkostnadsavvikelse
description: Detta ämne innehåller information om hur du ställer in bokföringsprofiler för standardkostnad.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: bc4f1bd7c1bf7a8f214f20460b10d371d8f3c790
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804626"
---
# <a name="standard-cost-variance-posting"></a>Bokföring av standardkostnadsavvikelse

När du använder standardkostnadsredovisning för en eller flera produkter i organisationen måste du konfigurera [förutsättningarna för standardkostnadsredovisning](/supply-chain/cost-management/prerequisites-standard-costs.md). I det här avsnittet beskrivs de bokföringskonton som krävs för steg 3 av förutsättningarna, "Tilldela redovisningskonton till artikelbokföring som hör till standardkostnadsavvikelser."

Olika typer av avvikelser kan uppstå för inköps- och tillverkningsorder. Exempel på produktionsavvikelser finns i [Vanliga källor till produktionsavvikelser](/supply-chain/cost-management/common-sources-of-production-variances.md). Prisavvikelser för inköpsorder inträffar när du använder standardkostnad för en inköpt artikel och det finns en skillnad mellan produktens standardkostnad och det fakturerade beloppet på inköpsordern.

## <a name="sample-posting-profile-configuration"></a>Exempel på konfiguration av bokföringsprofil

Följande tabell innehåller exempel på standardbokföringstyper. Det inkluderar exempel på huvudkonton och beskrivningar.

- "Debet/Kredit?" kolumnen anger om transaktionen normalt bokför en debet eller kredit. I vissa fall kan en transaktion bokföra antingen debet eller kredit.
- Kolumnen Clearingkonto visar att bokföringstypen är ett clearingkonto. Med andra ord innebär att det belopp som bokförs på detta konto återförs automatiskt när en senare transaktion bokförs.
- I kolumnen "P/F" anges bokföringstypen. "P" representerar fysisk bokföring och "F" representerar ekonomisk bokföring.
- Kolumnen Följ visar om huvudkontot för en bokföringstyp normalt är samma som huvudkontot för en annan bokföringstyp. Specifikt visar detta den bokföringstyp som vanligtvis används.

> [!NOTE]
> Huvudkontona och huvudkontonamnen i tabellen är bara förslag. Vi rekommenderar att du arbetar med revisorn för att avgöra vilken konfiguration som passar bäst för verksamheten.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | P/F | Följ | Beskrivning |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-----|--------|-------------|
| Inköpsprisavvikelse | 510310 | Inköpsprisavvikelse | Utgift | Antingen | Nej | F | Inte tillämpligt | Det här kontot används när det finns en avvikelse mellan inköpspriset och standardkostnaden på en inköpsorder. |
| Omvärdering av lagerkostnad | 510330 | Omvärdering av lagerkostnad | Utgift | Antingen | Nej | F | Inte tillämpligt | Det här kontot används när en ny kostnadsversion aktiveras för en standardkostnadsartikel för omvärdera lagerbehållningen. |
| Avvikelse för kostnadsändring | 510320 | Avvikelse för kostnadsändring | Utgift | Antingen | Nej | F | Inte tillämpligt | Det här kontot används när det finns en skillnad i standardkostnader mellan siter eller när en artikel returneras och det finns en ändring mellan den ursprungliga standardkostnaden och den aktuella standardkostnaden för en produkt. |
| Avvikelse för produktionspartistorlek | 510370 | Avvikelse för produktionspartistorlek | Utgift | Antingen | Nej | F | Inte tillämpligt | Det här kontot används när det finns skillnader mellan beräkningsunderlaget för strukturlistan och den faktiska kvantiteten för kostnadsberäkningen för tillverkningsordern. |
| Produktionsprisavvikelse | 510340 | Produktionsprisavvikelse | Utgift | Antingen | Nej | F | Inte tillämpligt | Detta konto används när det finns prisskillnader mellan den uppskattade kostnaden och den faktiska kostnaden för en tillverkningsorder. |
| Produktionskvantitetsavvikelse | 510350 | Produktionskvantitetsavvikelse | Utgift | Antingen | Nej | F | Inte tillämpligt | Detta konto används när det finns kvantitetsskillnader mellan den uppskattade kostnaden och den faktiska kostnaden för en tillverkningsorder. |
| Produktionsersättningsavvikelse | 510360 | Produktionsersättningsavvikelse | Utgift | Antingen | Nej | F | Inte tillämpligt | Det här kontot används när det sker en oväntat förbrukning på en tillverkningsorder. |
| Avrundningsavvikelse | 618160 | Avrundningsdifferens | Utgift | Antingen | Nej | F | Inte tillämpligt | Detta konto används när det finns en avrundningsdifferens när produktionskostnaderna beräknas från standardkostnaderna. |
