--- 
title: "Registrera försäljningsprovisioner"
description: "I den här proceduren visas hur försäljningsprovisioner beräknas och registreras."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 5535f1627526b97ddc9ca2c210db4e332782d656
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="register-sales-commissions"></a>Registrera försäljningsprovisioner

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur försäljningsprovisioner beräknas och registreras. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Innan du startar guiden kör du guiden ”Ställ in regler för försäljningsprovision” för att vara säker på att alla nödvändiga inställningar för provisionsberäkningen har gjorts.

Skriv upp kundnumren och artikelnumret du har valt för provisionsprocessen, och använd dem när du ska skapa en försäljningsorder i den här guiden.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Fakturera en försäljningsorder som kvalificerar en säljare för provision
1. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Klicka på OK.
7. Klicka på Alternativ i åtgärdsfönstret.
8. Klicka på Ändra vy.
9. Klicka på Huvudvy.
10. Expandera avsnittet Inställningar.
    * Värdet i försäljningsgruppfältet representerar en grupp med en eller flera säljare som har kopplats till det. Människorna i gruppen är de som ska få provision när ordern är fakturerad enligt fördefinierade frekvenser och distribution.   Värdet kopieras från kund-kort, men du kan ändra det om du vill.  Försäljningsgruppen finns också kopieras till kundorderraden. Du kan ändra den, så att den kan skilja sig från den i huvudet och/eller mellan raderna.  
    * Värdet i provisiongruppsfältet representerar en grupp som du har skapat för en eller flera kunder med syftet att spåra provisioner.   Värdet kopieras från kund-kort, men du kan ändra det om du vill.   
11. Klicka på Alternativ i åtgärdsfönstret.
12. Klicka på Ändra vy.
13. Klicka på Radvy.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
15. Välj den artikel som du har ställt in för provisioner i listan. 
16. Ange ett tal i fältet Kvantitet.
    * Observera radens nettobelopp. Det representerar försäljningsintäkten, som i det här exemplet är grunden för provisionsberäkningen.  
17. Klicka på Spara.
18. Klicka på Faktura i åtgärdsfönstret.
19. Klicka på Faktura.
20. Expandera avsnittet Parametrar.
21. Välj Alla i fältet Kvantitet.
22. Välj Ja i fältet Bokför.
23. Klicka på OK.
24. Klicka på OK.
    * Den kan ta minut eller så att bokföra transaktionen. Tillåt processen att slutföras och stäng inte sidan.  

## <a name="review-the-registered-sales-commissions"></a>Granska de registrerade försäljningsprovisionerna
1. Klicka på Faktura i åtgärdsfönstret.
2. Klicka på Faktura.
3. Klicka på Faktura i åtgärdsfönstret.
4. Klicka på Provisionstransaktioner.
    * På fliken Översikt visas raderna med provisionsbeloppen som är betalning till säljare som är kopplade till den fakturerade försäljningsordern. Vi tar en titt på detaljerna.     
    * Om du använde guiden ”Ställ in regler för försäljningsprovision” när du ställde in försäljningsprovisionsgruppen, finns det två säljare som får provision och provisionen fördelas lika mellan dem.  
    * I det här exemplet beräknas provisionens totala belopp som procent av försäljningsintäkten (nettobeloppet på orderraden).   
5. Stäng sidan.
6. Klicka på Verifikation.
    * Du kan granska de verifikationstransaktionerna för provisionsbeloppen som har bokförts på de fördefinierade kontona för provisionsutgiften och provisionsskulden.  


