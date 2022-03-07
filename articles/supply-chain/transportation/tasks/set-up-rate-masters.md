---
title: Ställ in tariffhuvuden
description: I den här proceduren visas hur du ställer in ett tariffhuvud.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4cca9fd47a5d8c81d7b8a913d0a467bc113b584
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438130"
---
# <a name="set-up-rate-masters"></a>Ställ in tariffhuvuden

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in ett tariffhuvud. Den logistikansvarige ställer vanligtvis in tariffhuvuden, beroende på vilka kontrakt som har signerats med transportföretagen. I detta scenario ställer du in ett tariffhuvud för ett flygtransportföretag. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

## <a name="set-up-break-master"></a>Ställa in en avbrottsmall

1. Gå till **Transporthantering > Inställningar > Klassificering > Rastmall**. Avbrottsmallar används för att definiera prissättningsstrukturen och dess brytpunkter. Prissättningsstrukturen använder skiftindelad prissättning som baseras på fysiska dimensioner.  
1. Välj **Ny**.
1. I fältet **Rastmall** anger du ett värde.
1. I fältet **Namn** anger du ett värde.
1. I fältet **Datatyp** välj datatypen.
1. I fältet **Jämförelse** anger du den typ av jämförelse som begärs (med operatorer).
1. I fältet **Brytenhet** ange brytningsenheten.
1. I avsnittet **Detaljer**, skapa så många raster som behövs för prisstrukturen.
1. Välj **Spara**.

## <a name="set-up-rate-master"></a>Ställa in tariffhuvud

1. Gå till **Transporthantering > Inställningar > Klassificering > Tariffmall**.
1. Välj **Ny**.
1. Skriv ett värde i fältet **Tariffmall**.
1. Skriv ett värde i fältet **Namn**.
1. I fältet **ID på metadata för bedömning** välj rullgardinsmenyn för att öppna sökningen. ID på metadata för bedömning bestämmer vilka data som behövs för tariffhuvudet, eftersom det definierar de metadata som förväntas av transporthantering där det här tariffhuvudet används.  
1. Välj alternativet P2P i det här exemplet. Detta är redan definierat i demonstrationsdata.
1. Klicka på länken på önskad rad i valda listan.
1. Välj **Spara**.

## <a name="set-up-rate-base"></a>Ställa in tariffbas

1. Välj **tariffbasen**.
    * Tariffbasen bestämmer tariffen för transportföretaget och kan användas för att ställa in en tariffstruktur, eftersom detta strukturerar upp tarifferna i de brytpunkter som definieras i avbrottsmallen.  
2. Välj **Ny**.
3. Skriv ett värde i fältet **Tariffbas**.
4. Skriv ett värde i fältet **Namn**.
5. I fältet **Avbrottsmall**, välj rullgardinsmenyn för att öppna sökningen.
    * Avbrottsmallar används för att definiera prissättningsstrukturen och dess brytpunkter. Prissättningsstrukturen använder skiftindelad prissättning som baseras på fysiska dimensioner.  
6. Använd vikt i det här exemplet. Detta är redan definierat i demonstrationsdata.
7. Klicka på länken på markerad rad i den listan.
8. Expandera avsnittet **Detaljer**.
9. Välj **Ny**.
10. Ange "30301" i fältet **Postnummer för avlämning från**.
11. Skriv "30318" i fältet **Postnummer för avlämning till**.
12. Skriv "USA" i fältet **Avlämningsland/region**.
13. I fältet **<1,00 kg** skriv "100".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 1 kilo.  
14. I fältet **<5,00 kg** skriv "300".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 5 kilo.  
15. I fältet **<20,00 kg** skriv "500".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 20 kilo.  
16. I fältet **<100,00 kg** skriv "1000".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 100 kilo.  
17. I fältet **<1 000,00 kg** skriv "3000".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 1 000 kilo.  
18. Välj **Spara**.
19. Stäng sidan.

## <a name="assign-rate-base"></a>Tilldela tariffbas

1. Visa avsnittet **Tilldelningar av tariffbas**.
2. Välj **Ny**.
    * Du kan ha flera tilldelningar av tariffbas för varje tariffhuvud. På så sätt kan du skapa flera olika prispunkter för varje transportföretag beroende på mål, tjänster eller olika tariffbaser. I den här proceduren kommer du endast att skapa en tariffbastilldelning.  
3. Skriv ett värde i fältet **Namn**.
4. I fältet **Tariffbas**, välj rullgardinsmenyn för att öppna sökningen.
5. Klicka på länken på markerad rad i den listan.
6. I fältet **Tjänst** väljer du den nedrullningsbara knappen för att öppna sökningen.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på markerad rad i den listan.
9. Ange "98052" i fältet **Postnummer för upphämtning**.
    * Ange vilket postnummer som den här tariffbastilldelningen ska gälla från.
10. Skriv "USA" i fältet **Upphämtningsland/region**.
11. Välj **Spara**.
