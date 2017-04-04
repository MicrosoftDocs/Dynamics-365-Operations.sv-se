---
title: Kostnadsposter
description: "Det här avsnittet innehåller information om kostnadsposter och när de skapas. En kostnadspost är en post för registrering av kvantiteten och kostnaden för en viss händelse."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 55f5ee731c40acc40e8fe20c24d4ed707fe2c81a
ms.lasthandoff: 03/31/2017


---

# <a name="cost-entries"></a>Kostnadsposter

Det här avsnittet innehåller information om kostnadsposter och när de skapas. En kostnadspost är en post för registrering av kvantiteten och kostnaden för en viss händelse.

Kostnadsposter är sammansättningar av lagertransaktioner som har registrerats i aktiva ekonomiska lagerdimensioner.

## <a name="examples"></a>Exempel
### <a name="example-1-no-cost-entries-are-created"></a>Exempel 1: Inga kostnadsposter skapas

En överföringsjournalhändelse registreras. Händelsen överför en del av artikel A från plats A till plats B. Platslagerdimensionen räknas inte som en del av kostnadsobjektet. Därför skapar händelsen två lagertransaktioner och inga kostnadsposter.

### <a name="example-2-cost-entries-are-created"></a>Exempel 2: Kostnadsposter skapas

En överföringsjournalhändelse registreras. Händelsen Överför från plats 1 en exemplaret av artikel A till plats 2. Sitens lagerdimension betraktas som en del av kostnadsbäraren. Därför skapar händelsen två lagertransaktioner och två kostnadsposter.

### <a name="example-3-one-cost-entry-is-created"></a>Exempel 3: En kostnadspost skapas

En produktinleveranshändelse registreras för en inköpsorder. Händelsen registrerar 100 enheter av artikel A med en enhetskostnad på 10,00 USD. Eftersom artikel A använder serienummer för att spåra syftet med lagerhantering, skapas ett unikt serienummer för varje artikel som tas emot. Därför skapar händelsen 100 lagertransaktioner och en kostnadspost.

## <a name="cost-entries-page"></a>Sidan Kostnadsposter
Den nya sidan **Kostnadsposter** visar och kontrollerar registreringar för kostnader och kvantiteter. Den här sidan kompletterar sidorna **Lagertransaktion** och **Lagerkvittning**. Poster registreras i kronologisk ordning för en händelse. Därför kan du snabbt söka efter och kontrollera ackumulerade kostnader för en viss händelse eller alla händelser som hör till ett dokument. Här är ett exempel:

-   En produktinleveranshändelse registreras för artikel A. Etthundra enheter inkommer till en enhetskostnad på 10,00 USD.
-   Några dagar efter att fakturahändelsen har registrerats ökar kostnaden till 11,00 USD. Därför är totalbeloppet är 1 100 USD. En andra verifikation skapas för att redovisa skillnaden 100 USD.
-   Några dagar senare registreras ett tillägg på 15,00 USD på inköpsordern som täcker transportkostnaden.

| Verifikation | Datum       | Referens      | Nummer | Parti-ID  | Referensparti | Returparti-ID | Kvantitet | Belopp  |
|---------|------------|----------------|--------|---------|---------------|---------------|----------|---------|
| 00001   | 01-01-2015 | Inköpsorder | 100001 | 0000101 |               |               | 100,00   | 1000,00 |
| 00002   | 20-01-2015 | Inköpsorder | 100001 | 0000101 |               |               |          | 100,00  |
| 00003   | 31-01-2015 | Justering     | 100001 | 0000101 |               |               |          | 15,00   |

Sidan **Kostnadsposter** aktiverar filtrering efter dokument-ID och dokumentdatum. **Anmärkning:** kostnadstransaktioner visas bara i [kostnadsbärare](cost-object.md) eller frisläppta produkter.

<a name="see-also"></a>Se även
--------

[Cost objects](cost-object.md)


