---
title: Ställ in bränsleindex för transportföretag
description: I den här handboken visas hur du skapar en bränsleindexregion, ett bränsleindex och ett transportföretags bränsleindex.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69bf6e3a896e560b1dbb96c8f997f6ee8dbb9ec1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214928"
---
# <a name="set-up-a-carrier-fuel-index"></a>Ställ in bränsleindex för transportföretag

[!include [banner](../../includes/banner.md)]

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

