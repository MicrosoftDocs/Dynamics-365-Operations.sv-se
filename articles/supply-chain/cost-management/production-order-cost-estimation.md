---
title: Kostnadsuppskattning av produktionsorder
description: Det här avsnittet innehåller information om produktionskostnadsuppskattning. Produktionskostnadsuppskattning ger dig information om material- och kapacitetsförbrukningskostnader vid produktion av en artikel i den kvantitet som anges på den planerade produktionsordern.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5debf62a3a0fc3ae8828473d7dd593c690e298712e5ed696077db1562796943
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724926"
---
# <a name="production-order-cost-estimation"></a>Kostnadsuppskattning av produktionsorder

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om produktionskostnadsuppskattning. Produktionskostnadsuppskattning ger dig information om material- och kapacitetsförbrukningskostnader vid produktion av en artikel i den kvantitet som anges på den planerade produktionsordern. 

När du har skapat en produktionsorder måste du beräkna produktionskostnader. Syftet är att uppskatta artikel- och flödesförbrukningen under produktionsprocessen eftersom dessa uppskattningar används för de efterföljande planerings- och produktionsprocesserna.

## <a name="production-cost-estimation"></a>Uppskattning av produktionskostnad
Uppskattning av produktionskostnader baseras på följande information:

-   Kvantitet på produktionsordern
-   Komponenterna i produktionsstrukturlistorna (BOMs)
-   Flödesoperationerna i produktionsflödet
-   Indirekta kostnader som gäller för komponenter och operationer
-   Aktiva kostnadsdata vid beräkningsdatumet

Om det finns en fiktiv radartikel i produktionsstrukturlistan återspeglar beräkningarna den fiktiva artikelns komponenter och flödesoperationer. Du kan använda uppskattningsuppgiften när du beräknar om uppskattade kostnader för att återspegla uppdaterad information. Den uppdaterade informationen kan till exempel vara ändringar i tillverkningsorderkvantiteten, komponenterna i produktionsstrukturlistan, flödesoperationerna i produktionsflödet, de indirekta kostnaderna som gäller för de här komponenterna och operationerna eller aktiva kostnadsdata på omräkningsdatumet. Beräkningarna av uppskattad kostnad föreslår också ett försäljningspris för produktionsartikeln baserat på kostnader plus tillägg. Beräkningarna av uppskattad kostnad kan också gälla för referensorder som återspeglar andra tillverkningsorder som är länkade till tillverkningsordern.

## <a name="view-the-estimated-costs"></a>Visa uppskattade kostnader
När du har kört en uppskattning kan du visa resultaten på sidan **Prisberäkning**. Vid uppskattningen beräknas följande värden:

-   **Produktionskostnad** – Produktionskostnaden visas på den översta raden i uppskattningen. Här visas den fullständiga kostnaden för tillverkningsordern och det totala försäljningspriset för produktionen. Detta är summan av alla kostnadsrader i uppskattningen.
-   **Flödes- eller resurskostnader** – Flödes- eller resurskostnader är kostnader för produktionsoperationerna. De inkluderar kostnaden för element såsom inställningstid, körtid och omkostnader.
-   **Materialkostnader** – Materialkostnader är de kostnader och priser för strukturlistekomponenter som krävs för att tillverka artikeln. De här kostnaderna har tidigare fastställts och registrerats i systemet.

## <a name="other-uses-of-cost-estimation"></a>Andra användningsområden för kostnadsuppskattning
En kostnadsuppskattning ger även följande information:

-   Välgrundande prisofferter
-   Uppskattning av orderns lönsamhet
-   Uppskattning av råmaterialanvändning
-   Jämförelser av kostnadsinformation från tidigare produktioner
-   Budget- och prognosinformation
-   Uppskattning av vilken produktionsstorlek som krävs för att upprätthålla en viss kostnad






[!INCLUDE[footer-include](../../includes/footer-banner.md)]