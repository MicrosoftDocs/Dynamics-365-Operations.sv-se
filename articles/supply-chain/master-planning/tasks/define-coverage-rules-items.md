---
title: Definiera disponeringsregler för artiklar
description: Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.
author: ShylaThompson
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11d92185bdbcf7aa1a668b6d2aa311805e42293c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437685"
---
# <a name="define-coverage-rules-for-items"></a>Definiera disponeringsregler för artiklar

[!include [banner](../../includes/banner.md)]

Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren visar hur du skapar disponeringsregler och åsidosätter disponeringsinställningar för en specifik artikel. Du ser även hur du anger standardlagerinställningar.


## <a name="create-a-coverage-group"></a>Skapa en disponeringsgrupp
1. Gå till **navigeringsfönstret > moduler > huvudplanering > Inställningar > disponeringsgrupper**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Disponeringsgrupp**.
4. Skriv ett värde i fältet **Namn**.
5. Ange ett värde i fältet **Kalender**. Välj den kalender som huvudplaneringen använder för att skapa återanskaffningsförslag för artiklar i den här gruppen.  
6. Välj ett alternativ i fältet **Disponeringskod**. Välj Krav för den här proceduren.  
7. Ange "90" i fältet **Tidsgräns för disponering (dagar)**. Huvudplaneringen genererar återanskaffningsförslag för artiklar i den här gruppen i upp till 90 dagar framåt.  
8. Ange "1" i fältet **Negativa dagar**.
9. Ange "1" i fältet **Positiva dagar**.
10. Visa eller dölj avsnittet **Övrigt**.
11. Under avsnittet **säkerhetsmarginaler i dagar** i fältet **Inleveransmarginal som lagts till för behovsdatum** anger du "1". Om inleveransmarginalen till exempel är satt till en dag och en inköpsorderrad har tidsplanerats för inleverans den 15 maj, beräknas i huvudplaneringen det justerade inleveransdatumet till den 16 maj.  
12. Ange "1" i fältet **Utleveransmarginal som dragits av från behovsdatum**. Om säkerhetsmarginalen till exempel är satt till en dag och en försäljningsorderrad har tidsplanerats för leverans den 15 maj, beräknas i huvudplaneringen det justerade leveransdatumet till den 14 maj.  
13. Ange "1" i fältet **Ändra ordning på marginal som lagts till i artikelledtiden**.
14. Klicka på **Spara**.

## <a name="create-a-new-product"></a>Skapa en ny produkt
1. Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Produktnummer**.
4. Skriv ett värde i fältet **Produktnamn**.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelmodellgrupp**.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelgrupp**.
9. Hitta och markera önskad post i listan.
10. Klicka på länken på den valda raden i listan.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.
12. Hitta och markera önskad post i listan.
13. Klicka på länken på den valda raden i listan.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.
15. Hitta och markera önskad post i listan.
16. Klicka på länken på den valda raden i listan.
17. Klicka på **OK**.

## <a name="setup-default-order-settings"></a>Ställ in standardorderinställningar
1. Klicka på **Plan** i **åtgärdsfönstret**.
2. Under **Orderinställningar**, klicka på **Standardorderinställningar**.
3. Under **Inköpsorder**, i fältet **Standardplats** anger du den plats som används som standardinställning när inköpsorder skapas.
4. Ange den plats där artikeln lagras i fältet **Standardlagerställe**.
5. Visa eller dölj avsnittet **Lager**.
6. I fältet **Flera** skriver du "10".
7. I fältet **min. orderkvantitet** skriver du "10".
8. I fältet **max. orderkvantitet** skriver du "100".
9. I fältet **standardorderkvantitet** skriver du "10".
10. Ange ett värde i fältet **Ledtid för inköp**.
11. Markera eller avmarkera kryssrutan **Arbetsdagar**.
12. Klicka på **Spara**.
13. Välj Inköpsorder i fältet **Standardordertyp**.
14. Klicka på **Spara**.
15. Stäng sidan. Stäng sidan Standardorderinställningar.  

## <a name="add-an-item-to-a-coverage-group"></a>Lägg till artikel i en disponeringsgrupp
1. Visa eller dölj avsnittet **Plan**.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Disponeringsgrupp**.
3. Sök efter **disponeringsgruppen** som du skapat i listan.
4. Klicka på länken på den valda raden i listan.

## <a name="create-item-coverage-rules"></a>Skapa artikeldisponeringsregler
1. Klicka på **Plan** i **åtgärdsfönstret**.
2. Under **disponering**, klicka på **artikeldisponering**.
3. Klicka på **Ny**.
4. Klicka på fliken **Allmänt**.
5. Markera rutan i rubriken för **Åsidosätt inställningar för disponeringsgrupp**.
6. Ange "60" i fältet **Tidsgräns för disponering (dagar)**. Även om artiklar i disponeringsgruppen Behov planeras 90 dagar framåt, kommer denna artikel att planeras 60 dagar framåt.  
7. Ange "2" i fältet **Negativa dagar**.
8. Ange "2" i fältet **Positiva dagar**.
9. Klicka på fliken **Ledtid**.
10. Markera rutan i rubriken för **Inköp**.
11. Ange "5" i fältet **Inköpstid**.
12. Klicka på **Spara**.

