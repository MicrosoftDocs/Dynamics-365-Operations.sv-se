--- 
title: "Underhåll ett flöde för en produktmodell"
description: "När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2f3df2bd6018d07d65950398e38821cad475752e
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="maintain-a-route-for-a-product-model"></a>Underhåll ett flöde för en produktmodell

[!include[task guide banner](../../includes/task-guide-banner.md)]

När du kör den här proceduren krävs det att det finns en modell för produktkonfiguration. I den här proceduren använder högtalarmodellen i demonstrationsföretaget USMF.


## <a name="add-a-route-operation"></a>Lägga till en flödesoperation
1. Klicka på Definition av produktvariantmodell.
2. Klicka på Modeller för produktkonfiguration.
3. Hitta och markera önskad post i listan.
    * Välj högtalarmodellen till den här övningen.  
4. Klicka på länken på den valda raden i listan.
5. Expandera avsnittet Flödesoperationer.
6. Klicka på Lägg till.
7. Skriv ett värde i fältet Namn.
8. Ange ett värde i fältet Beskrivning.
9. Klicka på Spara.

## <a name="enter-route-operation-details"></a>Ange flödesoperationsinformation
1. Klicka på Flödesoperationsinformation.
2. Ange eller välj ett värde i fältet Operation.
3. I oper. Nr. fältet anger du ett tal.
    * Operationsnummer bestämmer ordningsföljden.  
    * Varje egenskap i en flödesoperation kan få ett statiskt värde eller mappas till ett attribut. Mappning till ett attribut leder till att värdet ställs in dom en del av konfigurationen.  
4. Ange eller välj ett värde i fältet Flödesgrupp.
    * Flödesgruppen bestämmer beteendet för kostnadsredovisning, förbrukning och inställning.  
5. Klicka på fliken Inställningar.
6. Klicka på fliken Tider.
7. I Processkvantitets- fältet anger du ett tal.
    * Bestäm hur många som ska bearbetas under en operation.  
8. Ange ett värde i fältet Timmar/tid.
    * Ange en tid.  
9. Markera kryssrutan Uppsättning.
10. Ange ett värde i fältet Körtid.
    * Bestäm bearbetningstiden för den kvantitet som du har angett.  
11. Klicka på fliken Resurskrav.
12. Klicka på Lägg till.
13. Markera vald rad i listan.
14. Välj ett alternativ i fältet Kravtyp.
    * Bestäm om du vill ange specifika resurser eller kvalifikationer som de måste ha.  
15. Ange eller välj ett värde i fältet Behov.
16. Klicka på OK.


