---
title: " Skapa, beräkna och bokföra ett utdrag för en butik"
description: Den här proceduren går igenom de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9ea30e7e008bfcce77a7ee2f4d7d01a6cf1ababc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548334"
---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a> Skapa, beräkna och bokföra ett utdrag för en butik

[!include[task guide banner](../includes/task-guide-banner.md)]

Den här proceduren går igenom de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik. Det finns också batchjobb som kan konfigureras för samma uppgifter. Stegen för att konfigurera och att köra batchjobb finns i andra avsnitt. För att slutföra den här proceduren måste du ha transaktioner som slutfördes i kassan och sedan samlats in till Dynamics AX. I den här insamlingen används demonstrationsföretaget USRT. Den här proceduren kan referera till Microsoft DynamicsAX. Notera att Dynamics AX nu kallas Microsoft Dynamics 365 for Operations.

1. Alla arbetsytor > .. > Butiksekonomi.
2. Klicka på Nytt utdrag.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Butiksnummer.
4. Klicka på länken på den valda raden i listan.
5. Klicka på OK.
    * Gruppen Inställningar har inställningar för att kontrollera vilka transaktioner som ingår i utdraget och hur de grupperas till utdragsrader. Du kan öppna gruppen Inställningar och ändra inställningarna, eller använda standardinställningarna.  
    * Utdragmetodfältet definierar hur utdragsraderna grupperas.  
    * Välj en medarbetare eller ett register om du vill beräkna ett utdrag för den specifika medarbetaren eller registret.  
6. Markera ett alternativ i fältet Stängningsmetod.
7. Klicka på Beräkna utdrag.
8. Klicka på Ja.
    * När du har beräknat utdraget måste det finnas rader som skapas med totalbelopp för varje betalningsmetod och utdragmetod som användes.  
    * Ange ett räknat belopp på varje rad om det behöver anges eller uppdateras. Det beräknade fältet fylls i med belopp från kassaavstämningar som gjorts i kassan.  
9. Klicka på Bokför utdrag.
10. Klicka på Stäng.
11. Gå till Butik och handel > Kanaler > Butiksekonomi.
12. Klicka på fliken Bokförda utdrag.

