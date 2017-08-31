--- 
title: "Ställ in avskrivningsregler "
description: "Den här uppgifthandboken ska skapa en ny avskrivningsregel och koppla den till en anläggningstillgångsgrupp."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f8ca9cc59df4eab5a476524e92200687e5979bc9
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-depreciation-books"></a>Ställ in avskrivningsregler  

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här uppgifthandboken ska skapa en ny avskrivningsregel och koppla den till en anläggningstillgångsgrupp.  Här används revisorrollen och demonstrationdata för den juridiska personen USMF.


## <a name="create-a-depreciation-book"></a>Skapa en avskrivningsregel
1. Gå till Anläggningstillgångar > Inställningar > Avskrivningsböcker.
2. Klicka på Ny.
3. Skriv ett värde i fältet Avskrivningsregler.
4. Ange ett värde i fältet Beskrivning.
5. Markera eller avmarkera kryssrutan Beräkna avskrivning.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avskrivningsprofil.
7. Hitta och markera önskad avskrivningsprofil i listan.
8. Klicka på länken på den valda raden i listan.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Alternativ avskrivningsprofil.
10. Hitta och markera önskad avskrivningsprofil i listan.
11. Klicka på länken på den valda raden i listan.
    * Den extraordinära avskrivningsprofilen används för ytterligare avskrivning av en tillgång i ovanliga omständigheter. Du kan till exempel använda det för att registrera den avskrivning på grund av naturkatastrofer.  
12. Markera eller avmarkera kryssrutan Skapa avskrivningsjusteringar med basjusteringar.
13. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kalender.
14. Klicka på länken på den valda raden i listan.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Koppla avskrivningsregler till en anläggningstillgångsgrupp
1. Klicka på Anläggningstillgångsgrupper.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Anläggningstillgångsgrupp.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Välj alternativ i fältet Avskrivningspraxis.
6. I fältet Tjänstelivstid, ange ett tal.
    * Värdet i fältet Avskrivningsperioder beräknas efter att du har angett tjänstelivstid.  


