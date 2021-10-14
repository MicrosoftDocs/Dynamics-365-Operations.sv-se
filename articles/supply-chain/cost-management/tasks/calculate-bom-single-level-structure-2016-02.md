---
title: Beräkna en strukturlista med en enda nivå (februari 2016)
description: Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda en enda nedbrytningsnivå som baseras på arket för kostnadsredovisning.
author: AndersGirke
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5968631f5fed8a43cd63165a4ddff86e8cb4b4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572107"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a>Beräkna en strukturlista med en enda nivå (februari 2016)

[!include [banner](../../includes/banner.md)]

Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda en enda nedbrytningsnivå som baseras på arket för kostnadsredovisning. Detta är den fjärde uppgiften i beräkningsserien för strukturlista. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.

1. Gå till Frisläppta produkter.
2. Hitta och markera önskad post i listan.
    * Välj produkten BOM_1.  
3. Klicka på Hantera kostnader i åtgärdsfönstret.
4. Klicka på Artikelpris.
5. Klicka på Beräkna artikelkostnad.
    * Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.  
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kostnadsredovisningsversion.
    * Välj 10 i det här exemplet. Detta är samma kostnadsversion som används för att lägga till självkostnaden för komponenter.  
7. Klicka på OK.
8. Klicka på Visa beräkningsuppgifter.
    * Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.    Här följer sammansättningen av kostnaden:  *    10 härleds från  ITEM_A, 10 från ITEM_B, 10 from BOM_2. I det här fallet finns ingen information för BOM_2 eftersom denna har registrerats som en standardkostnad på 10, men inte beräkningen.  *    7 härleds från ställtiden, som är en konstant kostnad, och ytterligare 7 härleds från körningen (Process).  *    Det finns också andra belopp som motsvarar indirekta kostnader.  
9. @SysTaskRecorder:_RequestClose



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]