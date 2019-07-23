---
title: Skapa ett batchjobb
description: Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d211dcd7cb47df135d395d2a993429746aa35a85
ms.sourcegitcommit: 6ba4006fb6a67ddd4b1e54e3d62b9d1239b5e5a3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/21/2019
ms.locfileid: "1700851"
---
# <a name="create-a-batch-job"></a>Skapa ett batchjobb

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning. Batchjobb körs med hjälp av säkerhetsreferenserna för användaren som skapade jobbet. Gör på följande sätt när du skapar ett batchjobb. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-the-batch-job"></a>Skapa batchjobbet
1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Frågor > Batchjobb**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Jobbbeskrivning**.
4. I fältet **Tidsplanerat startdatum/-tid** anger du datum och tid.
5. Klicka på **Spara**.

## <a name="create-a-recurrence"></a>Skapa en upprepning
1. Klicka på **Batchjobb** i Åtgärdsfönstret.
2. Klicka på **Upprepning.** Använd dessa alternativ om du vill ange ett intervall och mönster för upprepningen.  
3. Klicka på **OK**.

## <a name="add-alerts"></a>Lägg till notifieringar
1. Klicka på **Batchjobb** i Åtgärdsfönstret.
2. Klicka på **Notifieringar**. Ange om du vill att notifieringar ska skickas när batchjobbet avslutas, innehåller ett fel eller annulleras. Sedan anger du om du vill att notifieringarna ska visas som popup-meddelanden.   
3. Klicka på **OK**.

## <a name="adjust-batch-job-status"></a>Justera batchjobbstatus
1. Gå till **Systemadministration > Förfrågninger > Batchjobb**.
2. Välj lämplig batchjobb.
3. Klicka på **Batchjobb > Funktioner > Ändra status** i Åtgärdsfönstret.
4. Välj lämplig status.
    - **Källskatte**: Ställ in batchjobbet som **källskatt** så att det inte dras från batchjobbets tidsplan. Motsvarar *stopp*.
    - **Väntar**: Ställ in batchjobbet som **väntar** så att det väntar på att få hämtas av batchjobbets tidsplan. Motsvarar *gå*.
5. Klicka på **OK**.
