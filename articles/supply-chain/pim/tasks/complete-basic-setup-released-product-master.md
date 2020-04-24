---
title: Slutför grundläggande inställningar för en frisläppt produktmall
description: Det här avsnittet visar hur du slutför de basinställningar som krävs innan produktmallen kan användas i strukturversioner.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b8fde67699270906b893eee06600b8acf4c681e9
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208327"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Slutför grundläggande inställningar för en frisläppt produktmall

[!include [banner](../../includes/banner.md)]

Det här avsnittet visar hur du slutför de basinställningar som krävs innan produktmallen kan användas i strukturversioner.

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

