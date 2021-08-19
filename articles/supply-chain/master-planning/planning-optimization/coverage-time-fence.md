---
title: Tidsgräns för disponering
description: I det här avsnittet beskrivs hur du ställer in stängsel för täckningstid när du använder Planeringsoptimering. En tidsgräns för disponering indikerar din planering horisont och gräns.
author: ChristianRytt
ms.date: 01/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-18
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f32c3fd523c3272665b4b45b6d3e136591d12cda191766970ebfaf74b81f0558
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726876"
---
# <a name="coverage-time-fences"></a>Tidsgräns för disponering

I det här avsnittet beskrivs hur du ställer in *Tidsgräns för disponering* när du använder Planeringsoptimering. Planerare kan definiera planeringshorisonten (täckningstidens stängsel i dagar) och utesluta tillgång och efterfrågan som faller bortom den horisonten. Därför hjälper tidsgräns för disponering till att förhindra "buller" som orsakas av leverans förslag som du inte behöver reagera på i månader. Exempel är nästa års prognos och kundorder som läggs långt utöver den normala ledtiden.

En tidsgräns för disponering är antalet dagar efter dagens datum (eller, mer exakt, det datum då du gör planeringskörningen) som tillgång och efterfrågan exkluderas. För att undvika förseningar måste du se till att tidsgräns för disponering är längre att den totala ledtiden. Systemets standardvärde är 100 dagar.

Du kan ange en tidsgräns för disponering på var och en av följande nivåer:

- **Disponeringsgrupp** – Du kan ange en standardtidsgräns för disponering för varje disponeringsgrupp.
- **Artikeldisponering** – Du kan åsidosätta tidsgräns för disponering som ärvs från disponeringsgruppen som har tilldelats en artikel.
- **Huvudplan** – Du kan åsidosätta tidsgräns för disponering som ärvs från disponeringsgruppen och inställningar för artikeldisponering.

I följande avsnitt förklaras hur du anger en disponeringsgrupp på varje nivå.

## <a name="set-a-coverage-time-fence-for-a-coverage-group"></a>Ange en tidsgräns för disponering för en disponeringsgrupp

När du anger en tidsgräns för disponering för en disponeringsgrupp gäller inställningen för alla artiklar (produkter) som tillhör den gruppen. Du kan dock åsidosätta inställningen för specifika artiklar eller specifika huvudplaner.

Gör så här om du vill ange en tidsgräns för disponering för en disponeringsgrupp.

1. Gå till **huvudplanering \> inställningar \> täckning \> disponeringsgrupper**.
1. Välj en befintlig disponeringsgrupp eller lista eller skapa en ny disponeringsgrupp.
1. På snabbfliken **Allmänt** ställer du in fältet **Tidsgräns för disponering (dagar)** till det antal dagar som du vill använda som tidsgräns för disponering för disponeringsgruppen.

## <a name="set-a-coverage-time-fence-for-a-specific-item"></a>Ange en tidsgräns för disponering för en specifik artikel

Varje artikel (produkt) tillhör en disponeringsgrupp. Om ingen disponeringsgrupp uttryckligen tilldelas en artikel gäller en standarddisponeringsgrupp. Varje artikel ärver tidsgräns för disponering från sin disponeringsgrupp. Du kan dock åsidosätta denna tidsgräns för disponering för specifika objekt som du kräver.

Gör så här om du vill ange en tidsgräns för disponering för en specifik artikel.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. I rutnätet väljer du en produkt.
1. I åtgärdsfönstret, på fliken **Plan** i gruppen **Disponering** väljer du **Artikeldisponering**.
1. På sidan **Artikeldisponering** på fliken **Översikt** väljer eller skapar du en rad för den webbplats där du vill ange en tidsgräns för disponering.
1. Välj fliken **Allmänt** om du vill öppna inställningarna för den valda webbplatsen.
1. Markera kryssrutan **Åsidosätt inställningar för disponeringsgrupp**.
1. Ställ in fältet **Tidsgräns för disponering (dagar)** till det antal dagar som du vill använda som tidsgräns för disponering för artikeln.

## <a name="set-a-coverage-time-fence-for-a-specific-master-plan"></a>Ange en tidsgräns för disponering för en huvudplan

Du kan ange en tidsgräns för disponering på huvudplannivå. På så sätt definierar du antalet dagar som huvudplaneringsberäkningen täcker för en huvudplan. Den här inställningen åsidosätter eventuella inställningar för disponeringstid som har definierats för varje relevant artikel och disponeringsgrupp.

Gör så här om du vill ange en tidsgräns för disponering för en huvudplan.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj en befintlig huvudplan i listan, eller skapa en ny huvudplan.
1. På snabbfliken **Tidsgräns i dagar** anger du alternativet **Disponering** till *Ja*. Gå sedan in i fältet under alternativet, ange det antal dagar som du vill använda som tidsgräns för disponering för huvudplanen.

## <a name="considerations-for-coverage-time-fences"></a>Överväganden för tidsgräns för disponering

När du ställer in tidsgräns för disponering bör du överväga följande punkter:

- Tidsgräns för disponering påverkar endast indata för huvudplanering. Om förseningar inträffar kan de resulterande planerade orderna ha ett datum som är efter dagens datum plus tidsgräns för disponering.
- Tidsgräns för disponering anges i kalenderdagar. Kalendrar som använder arbetsdagar påverkar inte beräkningen av tidsgränsen. En vecka betraktas till exempel alltid som sju dagar, även om helger ställs in som stängda dagar i arbetstidskalendern.
- Kravtransaktioner kommer inte att genereras för alla utbud och efterfrågan som faller utanför tidsgräns för disponering.
- Om någon godkänd tillgång och efterfrågan faller utanför tidsgräns för disponering, kommer det inte att laddas i motorn. Därför utlöser det inte någon påfyllning och förseningar beräknas inte. Trots detta bör detta utbud och efterfrågan inte utplånas från systemet.
- Variationer i säkerhetslagermängder (från miniminycklar) kommer att ignoreras om de faller utanför tidsgräns för disponering.
- Den koncerninterna efterfrågan ignoreras om det begärda leveransdatumet som beräknas inte finns innanför tidsgräns för disponering. Observera att, för inbyggd huvudplanering, är koncernintern efterfrågan inte begränsas av tidsgräns för disponering.
- Behovsprognoser ignoreras om budgetdatumet inte finns innanför tidsgräns för disponering. Observera att, för inbyggd huvudplanering, är efterfrågeprognoser inte begränsade av tidsgräns för disponering.
- Planeringsoptimering är tidszon–medveten. Den betraktar tidszonen vid tillgångs- och efterfrågeplatserna, och tidpunkten för planeringskörningen. Till exempel, huvudplanering utlöses 11:00 den 15 oktober från en plats i Danmark (GMT +1 tidszon), och en tidsgräns för disponering på tio dagar används. I det här fallet ingår tillgång och efterfrågan från en plats i Seattle (GMT-8 tidszon) fram till 02:00 den 25 oktober (= tio 24-timmars dagar efter att huvudplanering utlöstes, minus tidszonsskillnaden på nio timmar). Observera att den inbyggda huvudplaneringsmotorn endast beaktar datumet för tidsgränsen. Därför kan resultatet skilja sig åt.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]