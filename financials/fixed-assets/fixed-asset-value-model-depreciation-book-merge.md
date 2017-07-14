---
title: "Sammanfogning av värdemodell för anläggningstillgångar och avskrivningsregler"
description: "I tidigare versioner fanns två värderingsbegrepp för anläggningstillgångar: värdemodeller och avskrivningsregler. I Microsoft Dynamics 365 for Operations, version 1611, har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för \"bok\"."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: add41ceb1dd31d5b5aa26916114d7d7864cb1626
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Sammanfogning av värdemodell för anläggningstillgångar och avskrivningsregler
<a id="fixed-asset-value-model-and-depreciation-book-merge" class="xliff"></a>

[!include[banner](../includes/banner.md)]


I tidigare versioner fanns två värderingsbegrepp för anläggningstillgångar: värdemodeller och avskrivningsregler. I Microsoft Dynamics 365 for Operations, version 1611, har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för "bok".

Den nya funktionen för avskrivningsregel baseras på tidigare värdemodellfunktion men innehåller även alla funktioner som endast angetts tidigare i avskrivningsregler. [![Boka som en sammanslagning av värdemodell och funktionen för avskrivningsbok](./media/fixed-assets.png)](./media/fixed-assets.png) På grund av denna sammanslagning kan du nu använda en enda uppsättning sidor, rapporter och frågor för alla Anläggningstillgångsprocesser. Tabellerna i det här avsnittet beskriver de tidigare funktionerna för den avskrivningsregler och värdemodeller, tillsammans med de nya funktionerna för böcker.

## Inställningar
<a id="setup" class="xliff"></a>
Som standard bokförs böcker i både huvudboken (GL) och i anläggningstillgångar. Böcker har ett nytt alternativ **Bokför i redovisningen** som låter dig inaktivera bokföring till huvudboken och bara bokföra till anläggningstillgångar. Denna funktion liknar det tidigare bokföringbeteendet för avskrivningsregler. Inställningen av journalnamn har ett nytt bokföringsskikt som kallas Inga. Detta bokföringsskikt lades specifikt till för anläggningstillgångar. Om du vill bokföra transaktioner för böcker som inte bokförs till huvudboken måste du använda ett journalnamn som har bokföringsskiktet inställt på **Ingen**.

|                                                  |                                 |                                 |                                                         |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
|                                                  | Förteckning över avskrivningsregler               | Värdemodell                     | Bok (ny)                                              |
| Bokför till huvudboken                                   | Aldrig                           | Alltid                          | Alternativ att bokföra till huvudboken                                |
| Bokföringsskikt                                   | Inte tillämpligt                  | 3. Aktuella, operationer och moms | 11: Aktuella, operationer, moms, 7 anpassade skikt och Inga |
| Journalnamn                                    | Journalnamn för avskrivningsregel | Huvudbok - Journalnamn              | Huvudbok - Journalnamn                                      |
| Härledda räkenskapsböcker                                    | Tillåts inte                     | Tillåts                         | Tillåts                                                 |
| Avskrivningsprofil åsidosätter på tillgångsnivån | Tillåts                         | Tillåts inte                     | Tillåts                                                 |

## Processer
<a id="processes" class="xliff"></a>
Processer använder nu en gemensam sida. Vissa processer tillåts bara om alternativet **Bokför till huvudboken** inställd på **Nej** i bokinställningar.

|                                |                           |                     |                                          |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
|                                | Förteckning över avskrivningsregler         | Värdemodell         | Bok (ny)                               |
| Transaktionspost              | Journal för avskrivningsregel | Journal för anläggningstillgångar | Journal för anläggningstillgångar                      |
| Bonusavskrivning             | Tillåts                   | Inte tillåtet         | Tillåts                                  |
| Radera historiska transaktioner | Tillåts                   | Inte tillåtet         | Tillåtet, om du inte bokför i huvudboken |
| Massuppdatering                    | Tillåts                   | Inte tillåtet         | Tillåtet, om du inte bokför i huvudboken |

## Förfrågningar och rapporter
<a id="inquiries-and-reports" class="xliff"></a>
Förfrågningar och rapporter stöder alla böcker. Rapporter som inte ingår i följande tabell gav tidigare stöd för både avskrivningsregler och värdemodeller och ska nu fortsätta att stödja alla boktyper. Fältet **Bokföringsskikt** har också lagts till rapporterna, så att du enkelt kan identifiera bokföring av transaktioner.

|                                       |                                |                          |                          |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
|                                       | Förteckning över avskrivningsregler              | Värdemodell              | Bok (ny)               |
| Förfrågningar                             | Transaktioner för avskrivningsregel | Transaktioner för anläggningstillgång | Transaktioner för anläggningstillgång |
| Kontoutdrag för anläggningstillgång                 | Tillåts inte                    | Tillåts                  | Tillåts                  |
| Underlag för anläggningstillgång                     | Tillåts                        | Tillåts inte              | Tillåts                  |
| Anläggningstillgångar kvartalsrapport | Tillåts                        | Tillåts inte              | Tillåts                  |

## Uppgradera
<a id="upgrade" class="xliff"></a>
Uppgraderingsprocessen flyttar din befintliga inställning och alla befintliga transaktioner till den nya bokstrukturen. Värdemodeller kommer att kvarstå som de är, som en bok som bokförs till huvudboken. Emellertid flyttas avskrivningsregler till en bok som har alternativet **Bokför i huvudboken** inställt på **Nej**. Journalnamn för avskrivningsregel ska flyttas till ett journalnamn för huvudbok som har bokföringsskiktet inställt på **Ingen**.




