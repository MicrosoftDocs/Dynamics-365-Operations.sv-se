---
title: Skapa ett batchjobb
description: Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning.
author: matapg007
ms.date: 11/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: matgupta
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
ms.openlocfilehash: 06fb9a18e70c316be97645ba76f9462cd3ccc729
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292463"
---
# <a name="create-a-batch-job"></a>Skapa ett batchjobb

[!include [banner](../../includes/banner.md)]

Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning. Batchjobb körs med hjälp av säkerhetsreferenserna för användaren som skapade jobbet. Gör på följande sätt när du skapar ett batchjobb. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-the-batch-job"></a>Skapa batchjobbet
1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Frågor > Batchjobb**.
2. Välj **Ny**.
3. I fältet **Jobbeskrivning** ange en beskrivning av batch-jobbet.
4. I fältet **Tidsplanerat startdatum/-tid**, ange datum och tid när batchjobbet ska köras.
5. Välj **Spara**.

## <a name="create-a-recurrence"></a>Skapa en upprepning
1. Klicka på **Batchjobb** i Åtgärdsfönstret.
2. Ange **upprepning**. Använd dessa alternativ om du vill ange ett intervall och mönster för upprepningen.  
3. Välj **OK**.

## <a name="add-alerts"></a>Lägg till notifieringar
1. Klicka på **Batchjobb** i Åtgärdsfönstret.
2. Välj **notifieringar**. Ange om du vill att notifieringar ska skickas när batchjobbet avslutas, innehåller ett fel eller annulleras. Sedan anger du om du vill att notifieringarna ska visas som popup-meddelanden.   
3. Välj **OK**.

## <a name="add-a-task-to-a-batch-job"></a>Lägga till en uppgift i ett batchjobb
1.  På sidan **batchjobb**, välj **visa uppgifter**.
2.  Välj **Ctrl+N** för att skapa en uppgift.
3.  Ange en beskrivning av batch-uppgift.
4.  I fältet **Företagskonton**, välj den företagsdatabas som uppgiften ska köras i.
5.  I fältet **Klassnamn**, välj den process som uppgiften ska köras i. 
6.  Välj en batchgrupp för uppgiften om det behövs.

    Klientuppgifter måste tilldelas en batchgrupp. De tilldelas automatiskt till standardbatchgruppen (även kallad tom batchgrupp).

7.  Välj **Ctrl+S** för att spara uppgiften.
8.  Om du vill göra den valda uppgiften beroende av en annan uppgift i jobbet väljer du rutnätet **Har villkor** och följer sedan dessa steg för varje villkor som du vill ange:

    1. Välj **Ctrl+N** för att skapa ett villkor.
    2. Välj uppgifts-ID för den överordnade uppgiften.
    3. Välj status som den överordnade uppgiften måste ha innan den beroende uppgiften kan köras.
    4. Välj **Ctrl+S** för att spara villkoret.

    Om du definierar mer än ett villkor och om *alla* villkor måste uppfyllas innan den beroende uppgiften kan köras, väljer du villkorstypen **Alla**. Välj villkorstypen *någon* om villkoren har uppfyllts välj en villkorstyp av **någon**.

9.  Välj hur misslyckade uppgifter ska hanteras. För att ignorera misslyckandet med en specifik uppgift, på fliken **Allmänt**, välj alternativet **Ignorera uppgiftsfel** för den uppgiften. Om du markerar det här alternativet misslyckas inte jobbet om uppgiften misslyckas. Du kan också använda fältet **Maximalt antal försök igen** om du vill ange antalet gånger som en uppgift måste försöka köras igen innan den betraktas som misslyckad. Vi rekommenderar att du inte anger fältet **Maximalt antal försök igen** till ett värde som är högre än **5**.

    Mer information om nya batchförsök finns i [Aktivera nya batchförsök](../retryable-batch.md).

## <a name="adjust-batch-job-status"></a>Justera batchjobbstatus
1. Gå till **Systemadministration > Förfrågninger > Batchjobb**.
2. Välj lämplig batchjobb.
3. Klicka på **Batchjobb > Funktioner > Ändra status** i Åtgärdsfönstret.
4. Välj lämplig status.
    - **Källskatte**: Ställ in batchjobbet som **källskatt** så att det inte dras från batchjobbets tidsplan. Motsvarar *stopp*.
    - **Väntar**: Ställ in batchjobbet som **väntar** så att det väntar på att få hämtas av batchjobbets tidsplan. Motsvarar *gå*.
5. Välj **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
