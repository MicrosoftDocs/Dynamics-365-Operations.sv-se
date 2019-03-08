---
title: Ställ in bränsleindex för transportföretag
description: I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex.
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
ms.openlocfilehash: b6f72de7ad54a2b2dc1bf40fd8cb86d8b055e2d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "366591"
---
# <a name="set-up-a-carrier-fuel-index"></a>Ställ in bränsleindex för transportföretag

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex. Bränsleindexregionen anger vilken region som bränsleindexet ska gälla för och bränsleindexet anger ett bränslepris för en viss tidsperiod. För att återspegla ändringen i bränslepriser över tid kan du associera flera bränsleindex med en transportör.  Dessa uppgifter utförs normalt av en transportkoordinator. Du kan använda den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.


## <a name="create-a-fuel-index-region"></a>Skapa en bränsleindexregion.
1. Gå till Transporthantering > Inställningar > Bränsleindex > Bränsleindexregioner.
    * Först måste du skapa de olika regioner där du arbetar och beräkna olika bränsletillägg.  
2. Klicka på Ny.
3. Skriv ett värde i fältet Region.
4. Skriv ett värde i fältet Namn.
5. Klicka på Spara.

## <a name="create-a-fuel-index"></a>Skapa ett bränsleindex
1. Gå till Transporthantering > Inställningar > Bränsleindex > Bränsleindex.
    * Du måste ange aktuella priser för bränslet för de regioner som du har ställt in.  
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Region.
4. Klicka på länken på den valda raden i listan.
5. Ange ett nummer i fältet Pris per liter.
6. Ange datum och tid i fältet Giltighetsdatum och giltighetstid.
7. Klicka på Spara.

## <a name="create-a-carrier-fuel-index"></a>Skapa ett bränsleindex för transportföretag
1. Gå till Transporthantering > Inställningar > Bränsleindex > Transportföretagets bränsleindex.
2. Klicka på Ny.
3. Skriv ett värde i fältet Transportföretagets bränsleindex.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Ny.
6. Ange datum och tid i fältet Giltighetsdatum och giltighetstid.
7. Ange ett nummer i fältet Pris/l från.
    * I det här exemplet kan du ange 1,95 i fältet Pris/l från.  
8. Ange ett nummer i fältet Pris/l till.
    * I det här exemplet kan du ange 2 i fältet Pris/l till.  
9. Välj ett tal i fältet Procent.
    * I det här exemplet kan du ange procentsatsen till 3.  
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.
11. Hitta och markera önskad post i listan.
12. Klicka på länken på den valda raden i listan.
13. Klicka på Spara.

