---
title: "Rapportera en produktionsorder som färdig"
description: "I den här proceduren visas hur du rapporterar en produktionsorder som färdig."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: e6f5e7316f89ba7c2b7091eb9df02aa07ea44dbd
ms.contentlocale: sv-se
ms.lasthandoff: 02/06/2018

---
# <a name="report-a-production-order-as-finished"></a>Rapportera en produktionsorder som färdig

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du rapporterar en produktionsorder som färdig. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Detta är den sjätte proceduren av sju som förklarar produktionsorderns livscykel.


## <a name="report-a-production-order-as-finished"></a>Rapportera en produktionsorder som färdig
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
    * Välj en produktionsorder som har statusen Startat.  
2. Klicka på Produktionsorder i åtgärdsfönstret.
3. Klicka på Rapportera som färdig.
    * På den här sidan kan du bekräfta kvantiteten av den färdiga produkten som ska rapporteras som färdig.  
4. Klicka på fliken Allmänt.
5. Ställ in Godkänd kvantitet på 18.
6. Ställ in Antal fel på 2.
7. Välj Material i fältet Felorsak.
8. Markera eller avmarkera kryssrutan Slutjobb.
9. Markera eller avmarkera kryssrutan Godta fel.
10. Klicka på OK.

## <a name="verify-the-report-as-finished-journal"></a>Verifiera journalen Rapporterat som färdigt
1. Klicka på Visa i åtgärdsfönstret.
2. Klicka på Rapporterat som färdigt.
3. Markera vald rad i listan.
4. Klicka på länken på den valda raden i listan.
    * Journalen för rapportering som slutfört bokförs. Om du vill göra justeringar i journalen, kan du manuellt skapa en ny journal där du kan göra ändringar.  

