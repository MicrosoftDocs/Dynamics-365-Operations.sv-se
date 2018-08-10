--- 
title: "Använd säkerhetslagerjournalen för att uppdatera minimumdisponering"
description: "I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d278b20724006ec3b3aa557738e8b130ca2bba15
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Använd säkerhetslagerjournalen för att uppdatera minimumdisponering

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen. Detta görs med hjälp av säkerhetslagerjournalen. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Denna uppgift är avsedd för produktionsplaneraren för att hjälpa till att bibehålla minsta disponering.


## <a name="create-a-new-safety-stock-journal-name"></a>Skapa ett nytt namn på säkerhetslagerjournal.
1. Gå till Namn på säkerhetslagerjournal.
2. Klicka på Ny.
3. Ange "Material" i fältet Namn.
4. Ange "Material" i fältet Beskrivning.
5. Stäng sidan.

## <a name="create-a-safety-stock-journal"></a>Skapa en säkerhetslagerjournal
1. Gå till Beräkning av säkerhetslager.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Namn.
    * Välj det säkerhetslagerjournalnamn som du har skapaat, t.ex. Material.  
4. Klicka på Skapa rader.
5. Ange ett datum i fältet Från datum.
    * Ange datumet till "2015-01-02".  
6. Ange ett datum i fältet Till datum.
    * Ange datumet till "2015-12-30".  
7. Klicka på OK.
    * Detta skapar rader för dimensionerna som har lagertransaktioner.  

## <a name="calculate-proposal"></a>Beräkna förslag
1. Klicka på Beräkna förslag.
2. Välj alternativet Use average issue during lead time.
3. Ange Multiplikationsfaktorn till "10".
    * Multiplikationsfaktorn används för att justera förslaget. Eftersom demodata bara har några transaktioner, måste du ange faktorn för att få ett realistiskt förslag.  
4. Klicka på OK.
    * Bläddra ned för att hitta M0002 och M0003. Visa kolumnen Beräknad minsta kvantitet.   

## <a name="update-minimum-quantity"></a>Uppdatera minsta kvantitet
1. Ange ett nummer i fältet Ny minsta kvantitet.
    * Uppdatera den Nya minsta kvantiteten till att matcha värdet i Beräknad minsta kvantitet. Om det beräknade minimivärdet är noll, kan du ange önskat framtida värde. Du kan till exempel ange den beräknade minimikvantiteten i det här fältet för M0002 som har lagerställe 12.  
2. Hitta och markera önskad post i listan.
    * Du kan till exempel välja M0002 som har lagerstället 12.  
3. Ange ett nummer i fältet Ny minsta kvantitet.
    * Uppdatera den Nya minsta kvantiteten till att matcha värdet i Beräknad minsta kvantitet. Om det beräknade minimivärdet är noll, kan du ange önskat framtida värde.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Bokför den nya minsta kvantiteten och verifiera resultatet
1. Klicka på Bokför.
2. Klicka på OK.
3. Klicka för att följa länken i fältet Artikelnummer.
4. Klicka för att följa länken i fältet Artikelnummer.
5. Klicka på Plan i åtgärdsfönstret.
6. Klicka på Artikeldisponering.
    * Observera att den minsta kvantiteten har uppdaterats med den nya minsta kvantiteten från säkerhetslagerjournalen.  


