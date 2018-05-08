--- 
title: "Definiera disponeringsregler för artiklar"
description: "Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: fe92393cc264df68f084db6974f7d4607d37d3ab
ms.contentlocale: sv-se
ms.lasthandoff: 11/02/2017

---
# <a name="define-coverage-rules-for-items"></a>Definiera disponeringsregler för artiklar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren visar hur du skapar disponeringsregler och åsidosätter disponeringsinställningar för en specifik artikel. Du ser även hur du anger standardlagerinställningar.


## <a name="create-a-coverage-group"></a>Skapa en disponeringsgrupp
1. Gå till Disponeringsgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Disponeringsgrupp.
4. Skriv ett värde i fältet Namn.
5. Ange ett värde i fältet Kalender.
    * Välj den kalender som huvudplaneringen använder för att skapa återanskaffningsförslag för artiklar i den här gruppen.  
6. Välj ett alternativ i fältet Disponeringskod.
    * Välj Krav för den här proceduren.  
7. Ange "90" i fältet Tidsgräns för disponering (dagar).
    * Huvudplaneringen genererar återanskaffningsförslag för artiklar i den här gruppen i upp till 90 dagar framåt.  
8. Ange "1" i fältet Negativa dagar.
9. Ange "1" i fältet Positiva dagar.
10. Visa eller dölj avsnittet Övrigt.
11. Ange "1" i i fältet Inleveransmarginal som lagts till för behovsdatum.
    * Om inleveransmarginalen till exempel är satt till en dag och en inköpsorderrad har tidsplanerats för inleverans den 15 maj, beräknas i huvudplaneringen det justerade inleveransdatumet till den 16 maj.  
12. Ange "1" i fältet Utleveransmarginal som dragits av från behovsdatum.
    * Om säkerhetsmarginalen till exempel är satt till en dag och en försäljningsorderrad har tidsplanerats för leverans den 15 maj, beräknas i huvudplaneringen det justerade leveransdatumet till den 14 maj.  
13. Ange "1" i fältet Ändra ordning på marginal som lagts till i artikelledtiden.
14. Klicka på Spara.

## <a name="create-a-new-product"></a>Skapa en ny produkt
1. Gå till Frisläppta produkter.
2. Klicka på Ny.
3. Skriv ett värde i fältet Produktnummer.
4. Skriv ett värde i fältet Produktnamn.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmodellgrupp.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelgrupp.
9. Hitta och markera önskad post i listan.
10. Klicka på länken på den valda raden i listan.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagringsdimensionsgrupp.
12. Hitta och markera önskad post i listan.
13. Klicka på länken på den valda raden i listan.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Spårningsdimensionsgrupp.
15. Hitta och markera önskad post i listan.
16. Klicka på länken på den valda raden i listan.
17. Klicka på OK.

## <a name="setup-default-order-settings"></a>Ställ in standardorderinställningar
1. Klicka på Plan i åtgärdsfönstret.
2. Visa standardorderinställningar.
3. Ange den plats som används som standardinställning när inköpsorder skapas i fältet Inköpsplats.
4. Ange den plats där artikeln lagras i fältet Lagerplats.
5. Visa eller dölj avsnittet Lager.
6. Ange Flera som "10".
7. Ange min. orderkvantitet som "10".
8. Ange Max. orderkvantitet som "100".
9. Ange Standardorderkvantitet som "10".
10. Ange ett värde i fältet Ledtid för inköp.
11. Markera eller avmarkera kryssrutan Arbetsdagar.
12. Klicka på Spara.
13. Välj Inköpsorder i fältet Standardordertyp.
14. Klicka på Spara.
15. Stäng sidan.
    * Stäng sidan Standardorderinställningar.  

## <a name="add-an-item-to-a-coverage-group"></a>Lägg till artikel i en disponeringsgrupp
1. Visa eller dölj avsnittet Plan.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Disponeringsgrupp.
3. Sök efter disponeringsgruppen som du skapat i listan.
4. Klicka på länken på den valda raden i listan.

## <a name="create-item-coverage-rules"></a>Skapa artikeldisponeringsregler
1. Klicka på Plan i åtgärdsfönstret.
2. Klicka på Artikeldisponering.
3. Klicka på Ny.
4. Klicka på fliken Allmänt.
5. Markera rutan i rubriken för Åsidosätt inställningar för disponeringsgrupp.
6. Ange "60" i fältet Tidsgräns för disponering (dagar).
    * Även om artiklar i disponeringsgruppen Behov planeras 90 dagar framåt, kommer denna artikel att planeras 60 dagar framåt.  
7. Ange "2" i fältet Negativa dagar.
8. Ange "2" i fältet Positiva dagar.
9. Klicka på fliken Ledtid.
10. Markera rutan i rubriken för Inköp.
11. Ange "5" i fältet Inköpstid.
12. Klicka på Spara.


