---
title: Ställ in regler för försäljningsprovision
description: I den här proceduren visas om hur du ställer in och aktiverar försäljningsprovisionsberäkning och knipning.
author: omulvad
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended, CommissionEmplSalesGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a109ca5cfaeb031b3b114bccca53804045f3101
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830045"
---
# <a name="set-up-sales-commission-rules"></a>Ställ in regler för försäljningsprovision

[!include [banner](../../includes/banner.md)]

I den här proceduren visas om hur du ställer in och aktiverar försäljningsprovisionsberäkning och knipning. Proceduren visas hur du skapar både kund- och artikelprovisionsgrupper, och hur du sedan kopplar en vald kund och produkt till respektive grupp. Grupperna används sedan i inställningarna för provisionsberäkningen för att skapa en kombination av kund, artikel och en säljare som måste matchas med försäljningsordern som berättigar säljaren till provision. Det är valfritt att skapa kund- och artikelprovisionsgrupper, eftersom beräkningen av provision också kan göras för en enskild kund eller artikel. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="set-up-commission-groups-and-commission-rates"></a>Ställ in provisionsgrupper och provisioner
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Provisioner > Kundgrupper för provision**.
2. Välj **Ny**.
3. Ange ett värde i fältet **Grupp**.
4. Skriv ett värde i fältet **Namn**.
5. Välj **Spara**.
6. Stäng sidan.
7. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Provisioner > Artikelgrupper**.
8. Välj **Ny**.
9. Ange ett värde i fältet **Grupp**.
10. Skriv ett värde i fältet **Namn**.
11. Välj **Spara**.
12. Stäng sidan.
13. Gå till **Försäljning och marknadsföring > Provisioner > Säljgrupper**.
    - En provisionsförsäljningsgrupp anger medarbetarna i säljarrollerna som är berättigade till en provision när en kund som associeras med relevant försäljningsgrupp köper vissa artiklar.  
    - I demonstrationsföretaget USMF finns det en försäljningsgrupp som kallas Säljare USA.  
14. Välj **Allmänt** i **åtgärdsfönstret**.
15. Klicka på **Säljare**. Sidan Säljare visar en lista över företagets säljare som har associerats med en specifik provisionsgrupp. Du kan tilldela flera säljare till samma grupp och definiera deras respektive andel av det totala värdet för provisionstillägget som en procentsats. Den totala provisionsandelen för alla medarbetare får inte överstiga 100. 
16. Markera vald rad i listan.
17. Välj **Redigera**.
18. Ställ in **provisionsandel** på 50.
19. Klicka på **Ny**.
20. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.
21. Använd **snabbfiltret** för att söka efter poster. Filtrera till exempel fältet Namn på värdet Susan Burk.
22. Klicka på **Välj**.
23. Ställ in **provisionsandel** på 50.
24. Klicka på **Spara**.
25. Gå till **Försäljning och marknadsföring > Provisioner > Beräkna provision**. På sidan för **beräkning av provision** definierar du provisionen som medarbetaren ska få för en försäljningstransaktion, när den innehåller den förinställda kombinationen av kund och produkt. Som en del av inställningen av provisionen måste du ange grunden för provisionsberäkningen och om den ska inkludera eller exkludera rabatter. Du kan även ange en för giltighetsperiod då provisionen ska vara aktiv.  
26. Klicka på **Ny**.
27. Välj Grupp i fältet **Artikelkod**.
28. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelrelation**.
29. I listan söker du efter och väljer den grupp som du skapade tidigare.
30. Välj Grupp i fältet **Kundkod**.
31. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kundrelation**.
32. I listan väljer du den grupp som du ställde in tidigare.
33. I fältet **Säljarrelation** klickar du på den nedrullningsbara knappen för att öppna sökningen.
34. Hitta och markera önskad post i listan.
    - Behåll alternativet Före radrabatt.  
    - Behåll alternativet Intäkt som grund för beräkningen av provisionen.    
35. Ange ett nummer i fältet Provisionsprocent.
36. Klicka på **Spara**.

## <a name="setting-up-commission-posting"></a>Ställ in provisionsbokföring
1. Gå till **Navigeringsfönstret > Försäljning och marknadsföring > Provisioner > Provisionsbokföring**. Provision är betalning till medarbetarna och därför måste de ställas in för att säkerställa korrekt redovisning på rätt konton i **redovisning**. Du gör detta på sidan **Provisionsbokföring**. Granska upplägget för det aktuella företaget. Vanligtvis bokförs provisionsbeloppen på ett dedicerad utgiftskonto och avräknas mot ett dedicerat dedikerat skuldkonto. Om du inte har lagt upp bokföringsreglerna för provision kan inte systemet slutföra faktureringen av en försäljningsorder som har provisioner.  
2. Stäng sidan.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Koppla en provisionssäljgrupp till en kund och en produkt
1. Gå till **Navigeringsfönstret > Moduler > Försäljning och marknadsföring > Kunder > Alla kunder**.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på **Redigera**.
5. Expandera avsnittet med **försäljningsorderstandarder**.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Provisionsgrupp**.
7. I listan väljer du den grupp som du skapade tidigare.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Säljgrupp**.
9. Hitta och markera önskad post i listan.
10. Klicka på **Spara**.
11. Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.
12. Använd **Filter** för att söka efter poster. Filtrera till exempel i fältet Artikelnummer med värdet T0020.
13. Klicka på länken på den valda raden i listan.
14. Klicka på **Redigera**.
15. Expandera avsnittet **Sälj**.
16. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Provisionsgrupp**.
17. I listan väljer du den provisionsgrupp som du skapade tidigare.
18. Välj **Spara**.

