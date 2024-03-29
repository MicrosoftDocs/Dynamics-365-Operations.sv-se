---
title: Använd säkerhetslagerjournalen för att uppdatera minimumdisponering
description: I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen.
author: johanhoffmann
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ae2209fc2412a4a67b46d6eb82ecb70aafc0159
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573619"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Använd säkerhetslagerjournalen för att uppdatera minimumdisponering

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du beräknar minsta disponeringsförslag som baseras på historiska transaktioner och uppdaterar sedan med artikeldisponeringen med förslagen. Detta görs med hjälp av säkerhetslagerjournalen. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Denna uppgift är avsedd för produktionsplaneraren för att hjälpa till att bibehålla minsta disponering.


## <a name="create-a-new-safety-stock-journal-name"></a>Skapa ett nytt namn på säkerhetslagerjournal.
1. I **navigeringfönstret**, gå till **Huvudplanering > Inställningar > Namn på säkerhetslagerjournal**.
2. Klicka på **Ny**.
3. Ange "Material" i fältet **Namn**.
4. Ange "Material" i fältet **Beskrivning**.
5. Stäng sidan.

## <a name="create-a-safety-stock-journal"></a>Skapa en säkerhetslagerjournal
1. I **navigeringfönstret**, gå till **Huvudplanering > Huvudplanering > Kör > Beräkning av säkerhetslager**.
2. Klicka på **Ny**.
3. I fältet **Namn** anger eller väljer du ett värde. Välj det säkerhetslagerjournalnamn som du har skapaat, t.ex. Material.  
4. Klicka på **Skapa rader.**
5. I fältet **Från datum** anger du ett datum.  
6. I fältet **Till-datum**, anger du ett datum.
7. Klicka på **OK**. Detta skapar rader för dimensionerna som har lagertransaktioner.  

## <a name="calculate-proposal"></a>Beräkna förslag
1. Klicka på **Beräkna förslag**.
2. Välj alternativet **Använd genomsnittlig utleverans under produktionstid**.
3. Ange **Multiplikationsfaktor** till 10. Multiplikationsfaktorn används för att justera förslaget. Eftersom demodata bara har några transaktioner, måste du ange faktorn för att få ett realistiskt förslag.  
4. Klicka på **OK**. Bläddra ned för att hitta M0002 och M0003. Visa kolumnen **Beräknad minst kvantitet**.   

## <a name="update-minimum-quantity"></a>Uppdatera minsta kvantitet
1. Ange ett nummer i fältet **Ny minsta kvantitet**. Uppdatera den Nya minsta kvantiteten till att matcha värdet i Beräknad minsta kvantitet. Om det beräknade minimivärdet är noll, kan du ange önskat framtida värde. Du kan till exempel ange den beräknade minimikvantiteten i det här fältet för M0002 som har lagerställe 12.  
2. Hitta och markera önskad post i listan. Du kan till exempel välja M0002 som har lagerstället 12.  
3. Ange ett nummer i fältet **Ny minsta kvantitet**. Uppdatera den Nya minsta kvantiteten till att matcha värdet i Beräknad minsta kvantitet. Om det beräknade minimivärdet är noll, kan du ange önskat framtida värde.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Bokför den nya minsta kvantiteten och verifiera resultatet
1. Klicka på **Bokför**.
2. Klicka på **OK**.
3. Klicka för att följa länken i fältet **Artikelnummer**.
4. Klicka för att följa länken i fältet **Artikelnummer**.
5. Klicka på Plan i **åtgärdsfönstret**.
6. Klicka på **Artikeldisponering**. Observera att den **minsta kvantiteten** har uppdaterats med den nya minsta kvantiteten från säkerhetslagerjournalen.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]