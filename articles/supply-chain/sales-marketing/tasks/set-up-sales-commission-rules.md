---
title: Ställ in regler för försäljningsprovision
description: I den här proceduren visas om hur du ställer in och aktiverar försäljningsprovisionsberäkning och knipning.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ed7ec4ca74e4b6863ab2feff7f20de319789038
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "334230"
---
# <a name="set-up-sales-commission-rules"></a>Ställ in regler för försäljningsprovision

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas om hur du ställer in och aktiverar försäljningsprovisionsberäkning och knipning. Proceduren visas hur du skapar både kund- och artikelprovisionsgrupper, och hur du sedan kopplar en vald kund och produkt till respektive grupp. Grupperna används sedan i inställningarna för provisionsberäkningen för att skapa en kombination av kund, artikel och en säljare som måste matchas med försäljningsordern som berättigar säljaren till provision. Det är valfritt att skapa kund- och artikelprovisionsgrupper, eftersom beräkningen av provision också kan göras för en enskild kund eller artikel. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="set-up-commission-groups-and-commission-rates"></a>Ställ in provisionsgrupper och provisioner
1. Gå till Försäljning och marknadsföring > Provisioner > Kundgrupper för provision.
2. Klicka på Ny.
3. Ange ett värde i fältet Grupp.
4. Skriv ett värde i fältet Namn.
5. Klicka på Spara.
6. Stäng sidan.
7. Gå till Försäljning och marknadsföring > Provisioner > Artikelgrupper.
8. Klicka på Ny.
9. Ange ett värde i fältet Grupp.
10. Skriv ett värde i fältet Namn.
11. Stäng sidan.
12. Gå till Försäljning och marknadsföring > Provisioner > Säljgrupper.
    * En provisionsförsäljningsgrupp anger medarbetarna i säljarrollerna som är berättigade till en provision när en kund som associeras med relevant försäljningsgrupp köper vissa artiklar.  
    * I demonstrationsföretaget USMF finns det en försäljningsgrupp som kallas Säljare USA.  
13. Klicka på Allmänt i åtgärdsfönstret.
14. Klicka på Säljare.
    * Sidan Säljare visar en lista över företagets säljare som har associerats med en specifik provisionsgrupp. Du kan tilldela flera säljare till samma grupp och definiera deras respektive andel av det totala värdet för provisionstillägget som en procentsats. Den totala provisionsandelen för alla medarbetare får inte överstiga 100.  
15. Markera vald rad i listan.
16. Klicka på Redigera.
17. Ställ in provisionsandel på 50.
18. Klicka på Ny.
19. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
20. Använd snabbfiltret för att söka efter poster. Filtrera till exempel fältet Namn på värdet Susan Burk.
21. Klicka på Välj.
22. Ställ in provisionsandel på 50.
23. Klicka på Spara.
24. Gå till Försäljning och marknadsföring > Provisioner > Beräkna provision.
    * På sidan för beräkning av provision definierar du provisionen som medarbetaren ska få för en försäljningstransaktion, när den innehåller den förinställda kombinationen av kund och produkt. Som en del av inställningen av provisionen måste du ange grunden för provisionsberäkningen och om den ska inkludera eller exkludera rabatter. Du kan även ange en för giltighetsperiod då provisionen ska vara aktiv.  
25. Klicka på Ny.
26. Välj Grupp i fältet Artikelkod.
27. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelrelation.
28. I listan söker du efter och väljer den grupp som du skapade tidigare.
29. Klicka på länken på den valda raden i listan.
30. Välj Grupp i fältet Kundkod.
31. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundrelation.
32. I listan väljer du den grupp som du ställde in tidigare.
33. I fältet Säljarrelation klickar du på den nedrullningsbara knappen för att öppna sökningen.
34. Hitta och markera önskad post i listan.
    * Behåll alternativet Före radrabatt.  
    * Behåll alternativet Intäkt som grund för beräkningen av provisionen.    
35. Ange ett nummer i fältet Provisionsprocent.
36. Klicka på Spara.

## <a name="setting-up-commission-posting"></a>Ställ in provisionsbokföring
1. Gå till Försäljning och marknadsföring > Provisioner > Provisionsbokföring.
    * Provisionser är betalning till medarbetarna och därför måste de ställas in för att säkerställa korrekt redovisning på rätt konton. Du gör detta på sidan Provisionsbokföring. Granska upplägget för det aktuella företaget. Vanligtvis bokförs provisionsbeloppen på ett dedicerad utgiftskonto och avräknas mot ett dedicerat dedikerat skuldkonto. Om du inte har lagt upp bokföringsreglerna för provision kan inte systemet slutföra faktureringen av en försäljningsorder som har provisioner.  
2. Stäng sidan.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Koppla en provisionssäljgrupp till en kund och en produkt
1. Gå till Försäljning och marknadsföring > Kunder > Alla kunder.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på Redigera.
5. Expandera avsnittet med försäljningsorderstandarder.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Provisionsgrupp.
7. I listan väljer du den grupp som du skapade tidigare.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Säljgrupp.
9. Hitta och markera önskad post i listan.
10. Klicka på Spara.
11. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
12. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Artikelnummer med värdet T0020.
13. Klicka på länken på den valda raden i listan.
14. Klicka på Redigera.
15. Expandera avsnittet Sälj.
16. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Provisionsgrupp.
17. I listan väljer du den provisionsgrupp som du skapade tidigare.

