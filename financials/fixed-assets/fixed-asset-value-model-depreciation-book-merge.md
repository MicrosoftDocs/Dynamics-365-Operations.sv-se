---
title: "Sammanfogning av värdemodell för anläggningstillgångar och avskrivningsregler"
description: "I tidigare versioner har två värdering begrepp för anläggningstillgångar - värdemodeller och avskrivningsregler. I Microsoft Dynamics 365 för operationer 1611 slagits värdemodell funktioner och funktionen för avskrivningar för avskrivningsregel samman till ett enda begrepp som kallas en bok."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 6c8c005c7f5ede54ce0b6c8114cac69e2551d467
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Sammanfogning av värdemodell för anläggningstillgångar och avskrivningsregler

I tidigare versioner har två värdering begrepp för anläggningstillgångar - värdemodeller och avskrivningsregler. I Microsoft Dynamics 365 för operationer 1611 slagits värdemodell funktioner och funktionen för avskrivningar för avskrivningsregel samman till ett enda begrepp som kallas en bok.

Den nya funktionen för avskrivningsregel baseras på tidigare värdemodellfunktion men innehåller även alla funktioner som endast angetts tidigare i avskrivningsregler. [![Adressboken som en sammanslagning av värdet värdemodellen och adressbokens funktionalitet](./media/fixed-assets.png)](./media/fixed-assets.png) på grund av den här kopplingen nu kan du använda en enda uppsättning sidor, rapporter och frågor för alla anläggningstillgångar processer. Tabellerna i det här avsnittet beskriver de tidigare funktionerna för den avskrivningsregler och värdemodeller, tillsammans med de nya funktionerna för böcker.

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

