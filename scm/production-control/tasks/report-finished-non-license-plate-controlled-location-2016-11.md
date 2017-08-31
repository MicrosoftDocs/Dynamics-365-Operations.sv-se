--- 
title: "Rapportera som färdig till en plats som styrs av ID-nummer "
description: "Den här uppgiftsguiden visar ett exempel på rapporteringen som slutförd till en plats som inte är ID-nummertyrd."
author: ChristianRytt
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 9b861d8499db2b7ba362664e271bedda1d392a23
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="report-as-finished-to-a-plate-controlled-location"></a>Rapportera som färdig till en plats som styrs av ID-nummer  

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiftsguiden visar ett exempel på rapporteringen som slutförd till en plats som inte är ID-nummertyrd. En tillämplig arbetspolicy är förutsättningen är den här uppgiften. En tidigare uppgiftsguide visade inställningarna för arbetspolicyn. Den här uppgiftsguiden kräver Dynamics AX program 7.0.1 eller senare.




## <a name="set-up-an-output-location"></a>Ställ in en utleveransplats
1. Gå till Organisationsadministration > Resurser > Resursgrupper.
2. Välj resursgrupp "5102" i listan.
3. Klicka på Redigera.
4. Ange "51" i fältet Utleveranslagerställe.
5. Ange "001" i fältet Utleveransplats.
    * Plats 001 är en ej ID-nummertyrd plats. Du kan ställa in en plats för ej ID-nummertyrd utleveransplats bara om en lämplig arbetspolicy finns för platsen.  

## <a name="create-a-production-order-and-report-it-as-finished"></a>Skapa en produktionsorder och rapportera den som färdig.
1. Stäng sidan.
2. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
3. Klicka på Ny produktionsorder.
4. Ange ett artikelnummer i fältet "L0101".
5. Klicka på Skapa.
6. Klicka på Produktionsorder i åtgärdsfönstret.
7. Klicka på Uppskattning.
8. Klicka på OK.
9. Klicka på Start.
10. Klicka på fliken Allmänt.
11. Välj "Aldrig" i fältet Automatisk strukturlisteförbrukning.
12. Klicka på OK.
13. Klicka på Rapportera som färdigt.
14. Klicka på fliken Allmänt.
15. Välj Ja i fältet Godkänn fel.
16. Klicka på OK.
17. Klicka på Lagerställe i åtgärdsfönstret.
18. Klicka på Information om arbete.
    * När tillverkningsordern rapporterades som färdig, genererades inget arbete för plats. Detta inträffar, eftersom en arbetspolicy definieras som hindrar arbete från att genereras när produkten L0101 rapporterats som färdig till plats 001.  


