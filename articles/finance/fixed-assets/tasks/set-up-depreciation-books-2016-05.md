---
title: Ställ in avskrivningsregler (maj 2016)
description: Den här uppgifthandboken ska skapa en ny avskrivningsregel och koppla den till en anläggningstillgångsgrupp.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6840e211847494598a81cd3228dbd3796447e18c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186910"
---
# <a name="set-up-depreciation-books-may-2016"></a>Ställ in avskrivningsregler (maj 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

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
