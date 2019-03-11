---
title: Ställ in hubbens tilläggsavgifter och tilläggsmallar
description: I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
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
ms.openlocfilehash: 9959c20f9a8fd07cbf0cfd76f7760b44d7b5cae1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "331907"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Ställ in hubbens tilläggsavgifter och tilläggsmallar

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben. Proceduren använder USMF-datauppsättningen. Den här inställningen görs vanligtvis av en transportkoordinator.


## <a name="set-up-a-hub-master"></a>Ställa in ett hubbhuvud
1. Gå till Transporthantering > Inställningar > Klassificering > Tilläggsmallar.
2. Klicka på Ny.
3. Skriv ett värde i fältet Tilläggsmall.
4. Skriv ett värde i fältet Namn.
5. Välj "Hubb" i fältet Tilläggstyp.
6. Klicka på Spara.
7. Stäng sidan.

## <a name="set-up-a-hub-accessorial-charge"></a>Ställa in en tilläggsavgift för hubb
1. Gå till Transporthantering > Inställningar > Klassificering > Hubbens tilläggsavgifter.
2. Klicka på Ny.
3. Skriv ett värde i fältet Hubbens tilläggs-ID.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Hubb.
5. Hitta och markera önskad post i listan.
6. Välj ett alternativ i fältet Hubbplats.
    * Du kan antingen skapa tillägget som en hämtning eller lämning. Beroende på ditt val ska tillägget tillämpas på motsvarande transportsegmentet i ditt flöde.  
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tilläggsmall.
8. Klicka på länken på den valda raden i listan.
    * Välj den mall du precis har skapat.  
9. Klicka på Spara.
10. Stäng sidan.

