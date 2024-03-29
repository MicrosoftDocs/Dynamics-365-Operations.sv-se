---
title: Kostnadsposter
description: Det här avsnittet innehåller information om kostnadsposter och när de skapas. En kostnadspost är en post för registrering av kvantiteten och kostnaden för en viss händelse.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 07e0e5f2e579d81fc96e1e03a2c63aea4c5c956f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673282"
---
# <a name="cost-entries"></a>Kostnadsposter

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om kostnadsposter och när de skapas. En kostnadspost är en post för registrering av kvantiteten och kostnaden för en viss händelse.

Kostnadsposter är sammansättningar av lagertransaktioner som har registrerats i aktiva ekonomiska lagerdimensioner.

## <a name="examples"></a>Exempel
### <a name="example-1-no-cost-entries-are-created"></a>Exempel 1: Inga kostnadsposter skapas

En överföringsjournalhändelse registreras. Händelsen överför en del av artikel A från plats A till plats B. Platslagerdimensionen räknas inte som en del av kostnadsobjektet. Därför skapar händelsen två lagertransaktioner och inga kostnadsposter.

### <a name="example-2-cost-entries-are-created"></a>Exempel 2: Kostnadsposter skapas

En överföringsjournalhändelse registreras. Händelsen överför 1 st av artikel A från plats 1 till plats 2. Platsens lagerdimension betraktas som en del av kostnadsobjektet. Därför skapar händelsen två lagertransaktioner och två kostnadsposter.

### <a name="example-3-one-cost-entry-is-created"></a>Exempel 3: En kostnadspost skapas

En produktinleveranshändelse registreras för en inköpsorder. Händelsen registrerar 100 enheter av artikel A med en enhetskostnad på 10,00 USD. Eftersom artikel A använder serienummer för att spåra syftet med lagerhantering, skapas ett unikt serienummer för varje artikel som tas emot. Därför skapar händelsen 100 lagertransaktioner och en kostnadspost.

## <a name="cost-entries-page"></a>Sidan Kostnadsposter
Den nya sidan **Kostnadsposter** visar och kontrollerar registreringar för kostnader och kvantiteter. Den här sidan kompletterar sidorna **Lagertransaktion** och **Lagerkvittning**. Poster registreras i kronologisk ordning för en händelse. Därför kan du snabbt söka efter och kontrollera ackumulerade kostnader för en viss händelse eller alla händelser som hör till ett dokument. Här är ett exempel:

-   En produktinleveranshändelse registreras för artikel A. Etthundra enheter inkommer till en enhetskostnad på 10,00 USD.
-   Några dagar efter att fakturahändelsen har registrerats ökar kostnaden till 11,00 USD. Därför är totalbeloppet är 1 100 USD. En andra verifikation skapas för att redovisa skillnaden 100 USD.
-   Några dagar senare registreras ett tillägg på 15,00 USD på inköpsordern som täcker transportkostnaden.

| Verifikation | Datum       | Referens      | Nummer | Parti-ID  | Kvantitet | Belopp  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 01-01-2015 | Inköpsorder | 100001 | 0000101 | 100,00   | 1000,00 |
| 00002   | 20-01-2015 | Inköpsorder | 100001 | 0000101 |          | 100,00  |
| 00003   | 31-01-2015 | Justering     | 100001 | 0000101 |          | 15,00   |

Sidan **Kostnadsposter** aktiverar filtrering efter dokument-ID och dokumentdatum. 

> [!NOTE]
> Obs! Kostnadsposter är endast tillgängliga för [kostnadsobjekt](cost-object.md) eller frisläppta produkter.

## <a name="additional-resources"></a>Ytterligare resurser

[Kostnadsobjekt](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]