---
title: Slutför grundläggande inställningar för en frisläppt produktmall
description: Denna artikel visar hur du slutför de basinställningar som krävs innan produktmallen kan användas i versioner för strukturlistor.
author: t-benebo
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a403600bfdc257587441b5b5a907981d5eebaf58
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844891"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Slutför grundläggande inställningar för en frisläppt produktmall

[!include [banner](../../includes/banner.md)]

Denna artikel visar hur du slutför de basinställningar som krävs innan produktmallen kan användas i versioner för strukturlistor.

Detta är den tredje proceduren utav åtta som förklarar hur du ställer upp kombinationer för dimensionsbaserad konfiguration. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.
2. Hitta och markera önskad post i listan. Välj den produktmall som har frisläppts i den andra proceduren. Den här produktmallen skapas med dimensionsbaserad konfigurationsteknik.  
3. Välj **Produkt** i åtgärdsfönstret.
4. Välj **Dimensionsgrupper** för att öppna dialogrutan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.
6. Hitta och markera önskad post i listan. Lagringsdimensionsgruppen avgör vilka lagringsdimensioner som används för produkttransaktion. Välj **Plats** för den här proceduren.  
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.
8. Hitta och markera önskad post i listan. Spårningsdimensionsgruppen avgör vilka spårningsdimensioner som används för produkttransaktion. Välj **Ingen** för den här proceduren.  
9. Klicka på **OK**.
10. Klicka på **Redigera**.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelmodellgrupp**.
12. Hitta och markera önskad post i listan. Artikelmodellgrupper innehåller inställningar som bestämmer hur artiklar kontrolleras och hanteras för artikelinleveranser och artikelutleveranser. De bestämmer även hur artikelförbrukningen beräknas. Välj **FIFO** för den här proceduren.  
13. Expandera avsnittet **Hantera kostnader**.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelgrupp**.
15. Hitta och markera önskad post i listan. Artikelgrupper används för att hantera lager genom att dela upp lagerartiklar i grupper. Välj **CarAudio** för den här proceduren.  
16. Klicka på **Plan** i åtgärdsfönstret.
17. Välj **Standardorderinställningar**.
18. Välj ett alternativ i fältet **Standardordertyp**. Välj **Produktion** om du vill ange att standardleveransalternativet för den här produktmall är att producera den.  
19. Välj **Spara**.
20. Stäng sidan.
21. Stäng formuläret **Information om frisläppt produkt**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]