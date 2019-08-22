---
title: Använd säkerhetslagerjournalen för att uppdatera minimumdisponering
description: I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f3b2916d6d2f24579fd9795c0e0bc548b6c2b747
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835798"
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

