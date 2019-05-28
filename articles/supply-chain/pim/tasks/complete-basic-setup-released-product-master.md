---
title: Slutför grundläggande inställningar för en frisläppt produktmall
description: I den här proceduren visas hur du slutför de basinställningar som krävs innan produktmallen kan användas i strukturversioner.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d3a91977c38c0ce0f9fe114bec943c7cb32a5d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568785"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Slutför grundläggande inställningar för en frisläppt produktmall

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du slutför de basinställningar som krävs innan produktmallen kan användas i strukturversioner.

Detta är den tredje proceduren utav åtta som förklarar hur du ställer upp kombinationer för dimensionsbaserad konfiguration. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Hitta och markera önskad post i listan.
    * Välj den produktmall som har frisläppts i den andra proceduren. Den här produktmallen skapas med dimensionsbaserad konfigurationsteknik.  
3. Klicka på Produkt i åtgärdsfönstret.
4. Klicka på Dimensionsgrupper för att öppna dialogrutan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagringsdimensionsgrupp.
6. Hitta och markera önskad post i listan.
    * Lagringsdimensionsgruppen avgör vilka lagringsdimensioner som används för produkttransaktion. Välj Plats för den här proceduren.  
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Spårningsdimensionsgrupp.
9. Hitta och markera önskad post i listan.
    * Spårningsdimensionsgruppen avgör vilka spårningsdimensioner som används för produkttransaktion. Välj Ingen för den här proceduren.  
10. Klicka på länken på den valda raden i listan.
11. Klicka på OK.
12. Klicka på länken på den valda raden i listan.
13. Klicka på Redigera.
    * Öppna formuläret Information om frisläppt produkt om du vill fortsätta med inställningsuppgiften.  
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmodellgrupp.
15. Hitta och markera önskad post i listan.
    * Artikelmodellgrupper innehåller inställningar som bestämmer hur artiklar kontrolleras och hanteras för artikelinleveranser och artikelutleveranser. De bestämmer även hur artikelförbrukningen beräknas. Välj FIFO för den här proceduren.  
16. Klicka på länken på den valda raden i listan.
17. Visa eller dölj avsnittet Hantera kostnader.
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelgrupp.
19. Hitta och markera önskad post i listan.
    * Artikelgrupper används för att hantera lager genom att dela upp lagerartiklar i grupper. Välj CarAudio för den här proceduren.  
20. Klicka på länken på den valda raden i listan.
21. Klicka på Plan i åtgärdsfönstret.
22. Visa standardorderinställningar.
23. Välj ett alternativ i fältet Standardordertyp.
    * Välj Produktion om du vill ange att standardleveransalternativet för den här produktmall är att producera den.  
24. Stäng sidan.
25. Stäng formuläret Information om frisläppt produkt.

