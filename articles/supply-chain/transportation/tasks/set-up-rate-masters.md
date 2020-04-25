---
title: Ställ in tariffhuvuden
description: I den här proceduren visas hur du ställer in ett tariffhuvud.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
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
ms.openlocfilehash: 91877c777c6f76bd4fcf1c786bd708051c2fcd47
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201466"
---
# <a name="set-up-rate-masters"></a>Ställ in tariffhuvuden

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in ett tariffhuvud. Den logistikansvarige ställer vanligtvis in tariffhuvuden, beroende på vilka kontrakt som har signerats med transportföretagen. I detta scenario ställer du in ett tariffhuvud för ett flygtransportföretag. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="set-up-rate-master"></a>Ställa in tariffhuvud
1. Gå till Transporthantering > Inställningar > Klassificering > Tariffmall.
2. Klicka på Ny.
3. Skriv ett värde i fältet Tariffmall.
4. Skriv ett värde i fältet Namn.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet ID på metadata för bedömning.
    * ID på metadata för bedömning bestämmer vilka data som behövs för tariffhuvudet, eftersom det definierar de metadata som förväntas av TMS-motorn där det här tariffhuvudet används.  
6. Välj alternativet P2P i det här exemplet.
7. Klicka på länken på den valda raden i listan.
8. Klicka på Spara.

## <a name="set-up-rate-base"></a>Ställa in tariffbas
1. Klicka på Tariffbas.
    * Tariffbasen bestämmer tariffen för transportföretaget och kan användas för att ställa in en tariffstruktur, eftersom detta strukturerar upp tarifferna i de brytpunkter som definieras i avbrottsmallen.  
2. Klicka på Ny.
3. Skriv ett värde i fältet Tariffbas.
4. Skriv ett värde i fältet Namn.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avbrottsmall.
    * Avbrottsmallar används för att definiera prissättningsstrukturen och dess brytpunkter. Prissättningsstrukturen använder skiftindelad prissättning som baseras på fysiska dimensioner.  
6. Använd vikt i det här exemplet
7. Klicka på länken på den valda raden i listan.
8. Växla expanderingen av avsnittet Detaljer.
9. Klicka på Ny.
10. Ange "30301" i fältet Postnummer för avlämning från.
11. Skriv "30318" i fältet Postnummer för avlämning till.
12. Skriv "USA" i fältet Avlämningsland/region.
13. Skriv "100" i fältet <1,00 kg.
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 1 kilo.  
14. I fältet <5,00 Lbs, typ "300".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 5 kilo.  
15. I fältet <20,00 Lbs, typ "500".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 20 kilo.  
16. I fältet <100,00 Lbs, typ "1000".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 100 kilo.  
17. I fältet <1000,00 Lbs, typ "3000".
    * Infoga tariffen per kilo om den totala vikten på beläggningen är mindre än 1 000 kilo.  
18. Klicka på Spara.
19. Stäng sidan.

## <a name="assign-rate-base"></a>Tilldela tariffbas
1. Växla expanderingen av avsnittet Tilldelningar av tariffbas.
2. Klicka på Ny.
    * Du kan ha flera tilldelningar av tariffbas för varje tariffhuvud. På så sätt kan du skapa flera olika prispunkter för varje transportföretag beroende på mål, tjänster eller olika tariffbaser. I den här proceduren kommer du endast att skapa en tariffbastilldelning.  
3. Skriv ett värde i fältet Namn.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tariffbas.
5. Klicka på länken på den valda raden i listan.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Tjänst.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.
9. Ange "98052" i fältet Postnummer för upphämtning.
    * Ange vilket postnummer som den här tariffbastilldelningen ska gälla från.    
10. Skriv "USA" i fältet Upphämtningsland/region.
11. Klicka på Spara.

