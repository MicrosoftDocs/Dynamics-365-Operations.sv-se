---
title: Konfigurera transportföretag
description: I den här proceduren beskrivs hur du ställer in ett transportföretag och definierar detaljer som tjänster, leveranssätt, transportanbud, transportbegränsningar och leveranskostnader.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "314496"
---
# <a name="set-up-shipping-carriers"></a>Konfigurera transportföretag

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren beskrivs hur du ställer in ett transportföretag och definierar detaljer som tjänster, leveranssätt, transportanbud, transportbegränsningar och leveranskostnader. En transportkoordinator kan sedan tilldela ett transportföretag till en inkommande eller utgående beläggning.


## <a name="create-a-new-shipping-carrier"></a>Skapa ett nytt transportföretag
1. Gå till Transporthantering > Inställningar > Transportföretag > Transportföretag.
2. Klicka på Ny.
3. Skriv ett värde i fältet Transportföretag.
4. Skriv ett värde i fältet Namn.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Metod.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Fyll i den allmänna informationen för transportföretaget
1. Växla expanderingen av avsnittet Översikt.
2. Markera eller avmarkera kryssrutan Aktivera transportföretag.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantör.
    * Välj det leverantörskonto som du vill tilldela transportföretaget till.  
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Välj ett alternativ i fältet Typ av transportanbud.
    * Välj Manuell för att använda sidan Transportanbud eller välj EDI för att uppdatera anbudet med hjälp av EDI (Electronic Data Interchange).  
7. Markera eller avmarkera kryssrutan Aktivera värdering av transportföretag.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Skapa nödvändiga tjänster för det transportföretaget
1. Växla expanderingen av avsnittet Tjänster.
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Skriv ett värde i fältet Transportföretagstjänst.
5. Skriv ett värde i fältet Namn.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transportmetod.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Ställ in för adress för transportföretaget (valfritt)
1. Växla utökningen av avsnittet Adresser.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn eller beskrivning.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Land/region.
5. Klicka på länken på den valda raden i listan.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Postnummer.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.
9. Ange ett värde i fältet Gata.
10. Klicka på OK.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Ställa in bedömningsprofil för transportföretaget
1. Växla expanderingen av avsnittet Bedömningsprofiler.
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Skriv ett värde i fältet Bedömningsprofil.
5. Skriv ett värde i fältet Namn.
6. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
10. Hitta och markera önskad post i listan.
11. Klicka på länken på den valda raden i listan.
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tariffmotor.
    * Välj den tariffmotor som överensstämmer med det kontrakt som du har för transportföretaget.  
13. Hitta och markera önskad post i listan.
14. Klicka på länken på den valda raden i listan.
15. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tariffmall.
16. Hitta och markera önskad post i listan.
17. Klicka på länken på den valda raden i listan.
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transporttidsmotor.
19. Klicka på länken på den valda raden i listan.
20. Klicka på Spara.

