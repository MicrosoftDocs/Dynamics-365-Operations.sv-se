---
title: Mappa dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar
description: Genom att mappa olika dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar för kostnadselement slår du samman data till ett gemensamt format för analysändamål.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3ce207b74c9515c72f4fce7680ee9eea50edd0f8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810160"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Mappa dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar

[!include [banner](../includes/banner.md)]

Genom att mappa olika dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar för kostnadselement slår du samman data till ett gemensamt format för analysändamål.

Om du är ett globalt företag och följer lagstadgade redovisningsbestämmelser, kan du använda flera kontoplaner. När du importerar dimensionsmedlemmar för kostnadselement från olika kontoplaner, kan du sluta med en blandning av konton. Dessa konton är kanske emellertid av samma slag och du vill kanske analysera och fördela kostnader för dem, genom att använda ett gemensamt format.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>Mappa dimensionsmedlemmar för kostnadselement till en gemensamt format
Följande exempel visar hur du som en kostnadscontroller kan skapa en ny dimension för kostnadselement i som mappar dimensionsmedlemmar för kostnadselement för den amerikanska kontoplanstrukturen och den franska kontoplanstrukturen till en gemensam uppsättning med dimensionsmedlemmar för kostnadselement. Du kan sedan använda den gemensam uppsättningen med dimensionsmedlemmar för kostnadselement om du vill analysera kostnadsdata från de två juridiska personerna i en kostnadsredovisning.

| Källa: amerikanska kontoplanen                                          | Källa: franska kontoplanen                                          | Ny gemensam uppsättning med dimensionsmedlemmar för kostnadselement                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Importerade dimensionsmedlemmar för kostnadselement från den amerikanska kontoplanen | Importerade dimensionsmedlemmar för kostnadselement från den franska kontoplanen | Mappning av franska och amerikanska dimensionsmedlemmar för kostnadselement till en gemensam uppsättning |
| 5001: Försäljning                                                           | 5001: Försäljning och reklam                                               | 5000: Försäljning och reklam                                             |
| 5030: Reklam                                                     | 6390: Lagerinköp\*                                                    | 7000: Rengöringskostnader                                                 |
| 7001: Rengöringskostnader                                               | 7001: Reseutgifter                                                      | 7001: Reseutgifter                                                   |

\*Lagerinköp för franska dimensionsmedlemmar för kostnadselement är inte mappade.

## <a name="currency-conversion"></a>Valutakonvertering
De olika kontoplanerna som du använder, kan kanske ställas in för att använda olika valutor. Kontrollera att du anger en valutakonvertering så att kostnadsdata bearbetas, genom att använda korrekt valuta, enligt definitionen i kostnadsredovisningen där dimensionsmedlemmar för kostnadselement används. I föregående exempel om amerikanska dollar (USD) används i kostnadsredovisningen, måste du skapa en valutakonvertering från USD till euro (EUR) för att bearbeta transaktioner för de mappade dimensionsmedlemmarna för kostnadselement.

## <a name="update-mappings-at-any-time"></a>Uppdatera mappningar när som helst
Du kan uppdatera mappningdefinitioner för en dimension för kostnadselement när som helst. Eftersom mappningar inte har giltighetsdatum, tillämpas ändringar nästa gång du bearbetar kostnadstransaktioner eller kör kostnadsberäkningar.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]