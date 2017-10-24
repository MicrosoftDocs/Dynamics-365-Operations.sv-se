--- 
title: Skapa ett batchjobb
description: "Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-batch-job"></a>Skapa ett batchjobb

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning. Batchjobb körs med hjälp av säkerhetsreferenserna för användaren som skapade jobbet. Gör på följande sätt när du skapar ett batchjobb. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-the-batch-job"></a>Skapa batchjobbet
1. Gå till Systemadministration > Förfrågninger > Batchjobb.
2. Klicka på Ny.
3. Skriv ett värde i fältet Jobbbeskrivning.
4. I fältet Tidsplanerat startdatum/-tid anger du datum och tid.
5. Klicka på Spara.

## <a name="create-a-recurrence"></a>Skapa en upprepning
1. Klicka på Batchjobb i Åtgärdsfönstret.
2. Klicka på Upprepning.
    * Använd dessa alternativ om du vill ange ett intervall och mönster för upprepningen.  
3. Klicka på OK.

## <a name="add-alerts"></a>Lägg till notifieringar
1. Klicka på Batchjobb i Åtgärdsfönstret.
2. Klicka på Notifieringar.
    * Ange om du vill att notifieringar ska skickas när batchjobbet avslutas, innehåller ett fel eller annulleras. Sedan anger du om du vill att notifieringarna ska visas som popup-meddelanden.   
3. Klicka på OK.


