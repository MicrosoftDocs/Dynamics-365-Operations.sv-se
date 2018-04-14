--- 
title: "Överför en anläggningstillgång"
description: "Den här uppgiftsguiden överför den ekonomiska informationen för en tillgångsförteckning från en uppsättning ekonomiska dimensioner till en ny uppsättning ekonomiska dimensioner."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b193cf6fbed810f0d5234514573d0f5c23c7b2c8
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-a-fixed-asset"></a>Överför en anläggningstillgång

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiftsguiden överför den ekonomiska informationen för en tillgångsförteckning från en uppsättning ekonomiska dimensioner till en ny uppsättning ekonomiska dimensioner.  Här används revisorrollen och demonstrationdata för den juridiska personen USMF.

1. Gå till anläggningstillgångar > anläggningstillgångar > Fasta tillgångar.
2. Hitta och välj den anläggningstillgång som ska överföras.
3. Klicka på Anläggningstillgång i åtgärdsfönstret.
4. Överför Överför fasta anläggningstillgångar.
5. I fältet Överföringsdatum, ange ett datum.
6. Ange en kommentar som beskriver överföringen.
    * Den här listan visar samtliga böcker för anläggningstillgången.  
7. Välj de böcker som du vill överföra till en ny ekonomisk dimensionsuppsättning.
    * Listan visar de befintliga ekonomiska dimensionsvärdena för den valda boken.  
    * Välj den ekonomiska dimension som du vill uppdatera för den valda tillgångsförteckningen.  
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Ekonomisk dimension.
    * Ange andra värden för ekonomisk dimension om det är tillämpligt.  
    * Alla värden för ekonomisk dimension ändras när en överföring uppstår, om ett värde har angetts eller lämnats tomt. Till exempel, om du anger ett värde för BusinessUnit och lämnar de ekonomiska dimensionerna CostCenter och Avdelning tomma. Om din kontostruktur tillåter toma värden för CostCenter och Avdelning leder överföringen till att varje värdemodell har det nya värdet för BusinessUnit och ett tomt värde för CostCenter och Avdelning.  
9. Klicka på Uppdatera.
    * Du har möjlighet att granska ändringar innan du slutför överföringen.  
    * Granska resultaten innan du överför tillgångsförteckningarna.  
10. Klicka på Överför.


