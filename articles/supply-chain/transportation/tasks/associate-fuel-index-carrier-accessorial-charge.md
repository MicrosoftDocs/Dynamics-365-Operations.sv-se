---
title: Associera ett bränsleindex med ett transportföretag som ett tillägg
description: I den här guiden visas hur du skapar en tilldelning av tillägg, en tilläggsavgift för transportföretag, en tilläggsmall för bränsletillägg och associerar ett transportföretags bränsleindex med ett transportföretag.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c91d49c2ccdc274632e3acf94b836e19dc6cdaa8
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017010"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>Associera ett bränsleindex med ett transportföretag som ett tillägg

[!include [banner](../../includes/banner.md)]

I den här guiden visas hur du skapar en tilldelning av tillägg, en tilläggsavgift för transportföretag, en tilläggsmall för bränsletillägg och associerar ett transportföretags bränsleindex med ett transportföretag. Du måste ha ställt in ett transportföretags bränsleindex innan du kör den här guiden. Du kan använda guiden "Ställa in bränsleindex för transportföretag" för att göra detta. Dessa inställningsuppgifter utförs normalt av en logistikansvarig. De demonstrationsdata som används för att skapa den här proceduren är USMF.


## <a name="create-an-accessorial-master"></a>Skapa en tilläggsmall
1. Gå till Transporthantering > Inställningar > Klassificering > Tilläggsmallar.
2. Klicka på Ny.
3. Skriv ett värde i fältet Tilläggsmall.
4. Skriv ett värde i fältet Namn.
5. Klicka på Spara.

## <a name="create-a-carrier-accessorial-charge"></a>Skapa en tilläggsavgift för transportföretag
1. Gå till Transporthantering > Inställningar > Klassificering > Tilläggsavgifter för transportföretag.
2. Klicka på Ny.
3. Skriv ett värde i fältet Transportföretagets tilläggs-ID.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transportföretag.
5. Hitta och markera önskad post i listan.
    * Välj Lastbilstransportföretag i det här exemplet.  
6. Klicka på länken på den valda raden i listan.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transportföretagstjänst.
8. Klicka på länken på den valda raden i listan.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tilläggsmall.
10. Hitta och markera önskad post i listan.
    * Välj den tilläggsmall som nyligen har skapats i det här exemplet.  
11. Klicka på Spara.

## <a name="create-an-accessorial-assignment"></a>Skapa en tilldelning av tillägg
1. Visa Tilldelningar av tillägg.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Växla expanderingen av avsnittet Kriterier.
    * I villkoren kan du välja alltid att tillämpa bränsletillägget, eller för det här exemplet välja att det gäller bara inom en viss region.  
5. Skriv ett värde i fältet Postnummer från.
6. Skriv ett värde i fältet Postnummer till.
7. Växla expanderingen av avsnittet Beräkning.
    * I beräkningsavsnittet kan du ange hur du beräknar bränsletillägget. Beräkningen beror på den tilläggsenhet som du valde som bas för beräkningen.  
8. Välj "Bränsletillägg" i fältet Typ av tilläggsavgift.
9. Välj "Körsträcka" i fältet Tilläggsenhet.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Region.
11. Klicka på länken på den valda raden i listan.
12. Klicka på Spara.

## <a name="update-the-carrier-rating-profile"></a>Uppdatera bedömningsprofilen för transportföretag
1. Gå till Transporthantering > Inställningar > Transportföretag > Transportföretag.
2. Hitta och markera önskad post i listan.
3. Växla expanderingen av avsnittet Bedömningsprofiler.
4. Klicka på Redigera.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Transportföretagets bränsleindex.
6. Klicka på länken på den valda raden i listan.
7. Klicka på Spara.

