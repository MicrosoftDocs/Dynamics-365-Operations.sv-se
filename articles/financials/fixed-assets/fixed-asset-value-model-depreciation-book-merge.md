---
title: Sammanfogning av värdemodell för anläggningstillgångar och avskrivningsregler
description: 'I tidigare versioner fanns två värderingsbegrepp för anläggningstillgångar: värdemodeller och avskrivningsregler. I versionen Microsoft Dynamics 365 for Operations (1611), har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för "bok".'
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 26f4b73f67064a83eb7b3d57f2dc98d90602c254
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568881"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Sammanfogning av värdemodell för anläggningstillgångar och avskrivningsregler

[!include [banner](../includes/banner.md)]

I tidigare versioner fanns två värderingsbegrepp för anläggningstillgångar: värdemodeller och avskrivningsregler. I versionen Microsoft Dynamics 365 for Operations (1611), har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för "bok".

Den nya funktionen för avskrivningsregel baseras på tidigare värdemodellfunktion men innehåller även alla funktioner som endast angetts tidigare i avskrivningsregler. [![Boka som en sammanslagning av värdemodell och funktionen för avskrivningsbok](./media/fixed-assets.png)](./media/fixed-assets.png) På grund av denna sammanslagning kan du nu använda en enda uppsättning sidor, rapporter och frågor för alla Anläggningstillgångsprocesser. Tabellerna i det här avsnittet beskriver de tidigare funktionerna för den avskrivningsregler och värdemodeller, tillsammans med de nya funktionerna för böcker.

## <a name="setup"></a>Inställningar
Som standard bokförs böcker i både huvudboken (GL) och i anläggningstillgångar. Böcker har ett nytt alternativ **Bokför i redovisningen** som låter dig inaktivera bokföring till huvudboken och bara bokföra till anläggningstillgångar. Denna funktion liknar det tidigare bokföringbeteendet för avskrivningsregler. Inställningen av journalnamn har ett nytt bokföringsskikt som kallas Inga. Detta bokföringsskikt lades specifikt till för anläggningstillgångar. Om du vill bokföra transaktioner för böcker som inte bokförs till huvudboken måste du använda ett journalnamn som har bokföringsskiktet inställt på **Ingen**.

|                                                  |                                 |                                 |                                                         |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
|                                                  | Förteckning över avskrivningsregler               | Värdemodell                     | Bok (ny)                                              |
| Bokför till huvudboken                                   | Aldrig                           | Alltid                          | Alternativ att bokföra till huvudboken                                |
| Bokföringsskikt                                   | Inte tillämpligt                  | 3. Aktuella, operationer och moms | 11: Aktuella, operationer, moms, 7 anpassade skikt och Inga |
| Journalnamn                                    | Journalnamn för avskrivningsregel | Huvudbok - Journalnamn              | Huvudbok - Journalnamn                                      |
| Härledda räkenskapsböcker                                    | Tillåts inte                     | Tillåts                         | Tillåts                                                 |
| Avskrivningsprofil åsidosätter på tillgångsnivån | Tillåts                         | Tillåts inte                     | Tillåts                                                 |

## <a name="processes"></a>Processer
Processer använder nu en gemensam sida. Vissa processer tillåts bara om alternativet **Bokför till huvudboken** inställd på **Nej** i bokinställningar.

|                                |                           |                     |                                          |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
|                                | Förteckning över avskrivningsregler         | Värdemodell         | Bok (ny)                               |
| Transaktionspost              | Journal för avskrivningsregel | Journal för anläggningstillgångar | Journal för anläggningstillgångar                      |
| Bonusavskrivning             | Tillåts                   | Inte tillåtet         | Tillåts                                  |
| Radera historiska transaktioner | Tillåts                   | Inte tillåtet         | Tillåtet, om du inte bokför i huvudboken |
| Massuppdatering                    | Tillåts                   | Inte tillåtet         | Tillåtet, om du inte bokför i huvudboken |

## <a name="inquiries-and-reports"></a>Förfrågningar och rapporter
Förfrågningar och rapporter stöder alla böcker. Rapporter som inte ingår i följande tabell gav tidigare stöd för både avskrivningsregler och värdemodeller och ska nu fortsätta att stödja alla boktyper. Fältet **Bokföringsskikt** har också lagts till rapporterna, så att du enkelt kan identifiera bokföring av transaktioner.

|                                       |                                |                          |                          |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
|                                       | Förteckning över avskrivningsregler              | Värdemodell              | Bok (ny)               |
| Förfrågningar                             | Transaktioner för avskrivningsregel | Transaktioner för anläggningstillgång | Transaktioner för anläggningstillgång |
| Kontoutdrag för anläggningstillgång                 | Tillåts inte                    | Tillåts                  | Tillåts                  |
| Underlag för anläggningstillgång                     | Tillåts                        | Tillåts inte              | Tillåts                  |
| Anläggningstillgångar kvartalsrapport | Tillåts                        | Tillåts inte              | Tillåts                  |

## <a name="upgrade"></a>Uppgradera
Uppgraderingsprocessen flyttar din befintliga inställning och alla befintliga transaktioner till den nya bokstrukturen. Värdemodeller kommer att kvarstå som de är, som en bok som bokförs till huvudboken. Emellertid flyttas avskrivningsregler till en bok som har alternativet **Bokför i huvudboken** inställt på **Nej**. Journalnamn för avskrivningsregel ska flyttas till ett journalnamn för huvudbok som har bokföringsskiktet inställt på **Ingen**.



