--- 
title: "Ordningsföljd för produktionsjobb för processtillverkning"
description: "Den här proceduren använder målarfärgprodukter som ett exempel för att visa hur du ordnar planerade order enligt prioritet för färg och paketstorlek."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f37b561188cf9c6d90c25e395ba30aa979136590
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>Ordningsföljd för produktionsjobb för processtillverkning

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren använder målarfärgprodukter som ett exempel för att visa hur du ordnar planerade order enligt prioritet för färg och paketstorlek. Det demonstrationsdataföretag som används för att skapa den här proceduren är USPI. Den här proceduren är avsedd för produktionsplaneraren.


## <a name="run-master-planning-for-uspi"></a>Kör huvudplanering för USPI
1. Gå till Huvudplanering > Huvudplanering > Kör > Huvudplanering.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Huvudplan.
3. Klicka på länken på den valda raden i listan.
    * Välj MasterPlan.  
4. Klicka på OK.
    * Detta startar huvudplanering, inklusive sekvensprocessen. Den här processen kan ta några minuter.  

## <a name="view-planned-orders-for-the-paint-products"></a>Visa planerade order för målarfärgprodukterna
1. Gå till Huvudplanering > Huvudplanering > Planerade order.
2. Visa faktaboxen Artikeldetaljer.
3. Visa faktaboxen Detaljer om tidsplan.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.
5. Hitta och markera önskad post i listan.
    * Välj MasterPlan.  
6. Klicka på länken på den valda raden i listan.
7. Använd snabbfiltret för att filtrera på fältet Artikelnummer med värdet P300.
    * Lås upp för att bläddra till höger för att se orderdatum och leveransdatum. Observera att dessa artiklar har ett orderdatum för idag och leveransdatum för de planerade order ordnas inte efter prioritet för färg och paketstorlek, som visas i produktnamnet. Du kan hovra över ett artikelnummer om du vill se produktnamnet och prioriteten.  

## <a name="sequence-planned-orders-for-paint"></a>Ordna planerade order för målarfärg
1. Stäng sidan.
2. Gå till Huvudplanering > Huvudplanering > Sekventiellt planerade order.
3. Visa faktaboxen Artikeldetaljer.
4. Visa faktaboxen Detaljer om tidsplan.
    * Obs! Här ser du att Startdatum/tid för planerade order ordnas efter färg och paketstorlek inom en gruppsperiod på 28 dagar. Dessa perioder definieras av ett nummer i fältet Kampanj. Det sekventiellt planerade orderformuläret fungerar som det vanliga planerade orderformuläret och produktionsplaneraren kan bekräfta planerade order här.  
5. Markera alla rader.
6. Klicka på Godkänn.
    * Detta kommer att uppdatera alla planerade order med den valda sekvensåtgärden av antingen Senarelägg eller Förskott.  

## <a name="verify-the-sequence-of-the-planned-orders"></a>Kontrollera sekvensen av de planerade order
1. Stäng sidan.
2. Gå till Huvudplanering > Huvudplanering > Planerade order.
3. Visa faktaboxen Artikeldetaljer.
4. Visa faktaboxen Detaljer om tidsplan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.
6. Hitta och markera önskad post i listan.
    * Välj MasterPlan.  
7. Klicka på länken på den valda raden i listan.
8. Använd snabbfiltret för att filtrera på fältet Artikelnummer med värdet P300.
    * Observera att order grupperas nu enligt prioritet för färg och storlek och planerade order börjar på det tidigaste order- och leveransdatumet. Validera orderdatumkolumnen eller startdatumet i faktaboxen Detaljer om tidsplan.  

