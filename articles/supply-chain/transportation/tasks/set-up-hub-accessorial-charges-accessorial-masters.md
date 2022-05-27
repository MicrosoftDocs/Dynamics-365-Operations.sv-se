---
title: Ställ in hubbens tilläggsavgifter och tilläggsmallar
description: I den här proceduren visas hur du skapar en tilläggsmall för en hub och använder den mallen för att skapa en tilläggsavgift för hubben.
author: Weijiesa
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ae7580e0c2a2f776512a7cf4c378266f1a878e9
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672638"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Ställ in hubbens tilläggsavgifter och tilläggsmallar

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]