---
title: Sammanfogning av värdemodell för anläggningstillgångar och avskrivningsregler
description: 'I tidigare versioner fanns två bedömningsbegrepp för anläggningstillgångar: värdemodeller och avskrivningsregler. I versionen Microsoft Dynamics 365 for Operations (1611), har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för "bok".'
author: moaamer
ms.date: 10/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f4f06b7916fb2eeed802b2dce95edfce448dcd97
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880857"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Sammanfogning av värdemodell för anläggningstillgångar och avskrivningsregler

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver den aktuella bokfunktionen i Anläggningstillgångar. Denna funktionalitet är baserad på den värdemodellfunktion som fanns i tidigare versioner men innehåller även alla funktioner som endast angetts tidigare i avskrivningsregler.

Med bokföringsfunktionen kan du använda en uppsättning sidor, förfrågningar och rapporter för alla dina processer för anläggningstillgångar. Tabellerna i den här artikeln beskriver de tidigare funktionerna för den avskrivningsregler och värdemodeller, tillsammans med aktuella funktionerna för böcker.

## <a name="setup"></a>Ställ in
Som standard bokförs böcker i både huvudboken (GL) och i anläggningstillgångar. Böcker har ett nytt alternativ **Bokför i redovisningen** som låter dig inaktivera bokföring till redovisningen och bara bokföra till anläggningstillgångar. Denna funktion liknar det tidigare bokföringbeteendet för avskrivningsregler. Inställningen av journalnamn har ett nytt bokföringsskikt som kallas Inga. Detta bokföringsskikt lades specifikt till för anläggningstillgångar. Om du vill bokföra transaktioner för böcker som inte bokförs till redovisning måste du använda ett journalnamn som har bokföringsskiktet inställt på **Ingen**.


| &nbsp;                                           | Förteckning över avskrivningsregler               | Värdemodell                     | Bok (ny)                                              |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
| Bokför i redovisningen                                   | Aldrig                           | Alltid                          | Möjlighet att posta till redovisningen                                |
| Bokföringsskikt                                   | Inte tillämpligt                  | 3. Aktuella, operationer och moms | 11: Aktuella, operationer, moms, 7 anpassade skikt och Inga |
| Journalnamn                                    | Journalnamn för avskrivningsregel | Redovisning - Journalnamn              | Redovisning - Journalnamn                                      |
| Härledda räkenskapsböcker                                    | Tillåts inte                     | Tillåtet                         | Tillåtet                                                 |
| Avskrivningsprofil åsidosätter på tillgångsnivån | Tillåts                         | Tillåts inte                     | Tillåts                                                 |

## <a name="processes"></a>Processer
Processer använder nu en gemensam sida. Vissa processer tillåts bara om alternativet **Bokför till huvudboken** inställd på **Nej** i bokinställningar.

| &nbsp;                                           | Förteckning över avskrivningsregler               | Värdemodell                     | Bok (ny)                                              |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
| Transaktionspost              | Journal för avskrivningsregel | Journal för anläggningstillgångar | Journal för anläggningstillgångar                      |
| Bonusavskrivning             | Tillåts                   | Inte tillåtet         | Tillåts                                  |
| Radera historiska transaktioner | Tillåts                   | Inte tillåtet         | Tillåtet, om du inte bokför i huvudboken |
| Massuppdatering                    | Tillåts                   | Inte tillåtet         | Tillåtet, om du inte bokför i huvudboken |

## <a name="inquiries-and-reports"></a>Förfrågningar och rapporter
Förfrågningar och rapporter stöder alla böcker. Rapporter som inte ingår i följande tabell gav tidigare stöd för både avskrivningsregler och värdemodeller och ska nu fortsätta att stödja alla boktyper. Fältet **Bokföringsskikt** har också lagts till rapporterna, så att du enkelt kan identifiera bokföring av transaktioner.

| &nbsp;                                           | Förteckning över avskrivningsregler               | Värdemodell                     | Bok (ny)                                              |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
| Förfrågningar                             | Transaktioner för avskrivningsregel | Transaktioner för anläggningstillgång | Transaktioner för anläggningstillgång |
| Kontoutdrag för anläggningstillgång                 | Tillåts inte                    | Tillåts                  | Tillåts                  |
| Underlag för anläggningstillgång                     | Tillåts                        | Tillåts inte              | Tillåts                  |
| Anläggningstillgångar kvartalsrapport | Tillåts                        | Tillåts inte              | Tillåts                  |

## <a name="upgrade"></a>Uppgradera
Uppgraderingsprocessen flyttar din befintliga inställning och alla befintliga transaktioner till den nya bokstrukturen. Värdemodeller kommer att kvarstå som de är, som en bok som bokförs till redovisningen. Emellertid flyttas avskrivningsregler till en bok som har alternativet **Bokför i redovisningen** inställt på **Nej**. Journalnamn för avskrivningsregel ska flyttas till ett journalnamn för redovisningen som har bokföringsskiktet inställt på **Ingen**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
