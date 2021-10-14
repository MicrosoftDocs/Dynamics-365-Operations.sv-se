---
title: Definiera disponeringsregler för artiklar
description: Den här proceduren visar hur du skapar disponeringsregler och åsidosätter disponeringsinställningar för en specifik artikel. Du ser även hur du anger standardlagerinställningar.
author: ChristianRytt
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15b0ad9faf2bcac25dec01a7ab44f804ad2345cd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567233"
---
# <a name="define-coverage-rules-for-items"></a>Definiera disponeringsregler för artiklar

[!include [banner](../../includes/banner.md)]

Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren visar hur du skapar disponeringsregler och åsidosätter disponeringsinställningar för en specifik artikel. Du ser även hur du anger standardlagerinställningar.

## <a name="create-a-coverage-group"></a>Skapa en disponeringsgrupp

Skapa en disponeringsgrupp genom att göra följande:

1. Gå till **navigeringsfönstret > moduler > huvudplanering > Inställningar > disponeringsgrupper**.
1. Välj **Ny**.
1. Skriv ett värde i fältet **Disponeringsgrupp**.
1. Skriv ett värde i fältet **Namn**.
1. Ange ett värde i fältet **Kalender**. Välj den kalender som huvudplaneringen använder för att skapa återanskaffningsförslag för artiklar i den här gruppen.  
1. Välj ett alternativ i fältet **Disponeringskod**. Välj Krav för den här proceduren.  
1. Ange "90" i fältet **Tidsgräns för disponering (dagar)**. Huvudplaneringen genererar återanskaffningsförslag för artiklar i den här gruppen i upp till 90 dagar framåt.  
1. Ange "1" i fältet **Negativa dagar**.
1. Ange "1" i fältet **Positiva dagar**.
1. Visa eller dölj avsnittet **Övrigt**.
1. Under avsnittet **säkerhetsmarginaler i dagar** i fältet **Inleveransmarginal som lagts till för behovsdatum** anger du "1". Om inleveransmarginalen till exempel är satt till en dag och en inköpsorderrad har tidsplanerats för inleverans den 15 maj, beräknas i huvudplaneringen det justerade inleveransdatumet till den 16 maj.
1. Ange "1" i fältet **Utleveransmarginal som dragits av från behovsdatum**. Om säkerhetsmarginalen till exempel är satt till en dag och en försäljningsorderrad har tidsplanerats för leverans den 15 maj, beräknas i huvudplaneringen det justerade leveransdatumet till den 14 maj.  
1. Ange "1" i fältet **Ändra ordning på marginal som lagts till i artikelledtiden**.
1. Välj **Spara**.

## <a name="create-a-new-product"></a>Skapa en ny produkt

Skapa en ny produkt genom att göra följande:

1. Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.
1. Välj **Ny**.
1. Skriv ett värde i fältet **Produktnummer**.
1. Skriv ett värde i fältet **Produktnamn**.
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelmodellgrupp**.
1. Hitta och markera önskad post i listan.
1. Klicka på länken på önskad rad i valda listan.
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelgrupp**.
1. Hitta och markera önskad post i listan.
1. Klicka på länken på önskad rad i valda listan.
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**.
1. Hitta och markera önskad post i listan.
1. Klicka på länken på önskad rad i valda listan.
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**.
1. Hitta och markera önskad post i listan.
1. Klicka på länken på önskad rad i valda listan.
1. Välj **OK**.

## <a name="set-up-default-order-settings"></a>Ställ in standardorderinställningar

Ställ in standardorderinställningar genom att göra följande:

1. I **åtgärdsfönstret**, välj **Plan**.
1. Under **Orderinställningar**, klicka på **Standardorderinställningar**.
1. Under **Inköpsorder**, i fältet **Standardplats** anger du den plats som används som standardinställning när inköpsorder skapas.
1. Ange den plats där artikeln lagras i fältet **Standardlagerställe**.
1. Visa eller dölj avsnittet **Lager**.
1. I fältet **Flera** skriver du "10".
1. I fältet **min. orderkvantitet** skriver du "10".
1. I fältet **max. orderkvantitet** skriver du "100".
1. I fältet **standardorderkvantitet** skriver du "10".
1. Ange ett värde i fältet **Ledtid för inköp**.
1. Markera eller avmarkera kryssrutan **Arbetsdagar**.
1. Välj **Spara**.
1. Välj Inköpsorder i fältet **Standardordertyp**.
1. Välj **Spara**.
1. Stäng sidan. Stäng sidan Standardorderinställningar.  

## <a name="add-an-item-to-a-coverage-group"></a>Lägg till artikel i en disponeringsgrupp

Lägg till ett objekt i en disponeringsgrupp genom att göra följande:

1. Visa eller dölj avsnittet **Plan**.
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Disponeringsgrupp**.
1. Sök efter **disponeringsgruppen** som du skapat i listan.
1. Klicka på länken på önskad rad i valda listan.

## <a name="create-item-coverage-rules"></a>Skapa artikeldisponeringsregler

Skapa artikeldisponeringsregler genom att göra följande:

1. I **åtgärdsfönstret**, välj **Plan**.
1. Under **disponering**, klicka på **artikeldisponering**.
1. Välj **Ny**.
1. Välj fliken **Allmänt**.
1. Markera rutan i rubriken för **Åsidosätt inställningar för disponeringsgrupp**.
1. Ange "60" i fältet **Tidsgräns för disponering (dagar)**. Även om artiklar i disponeringsgruppen Behov planeras 90 dagar framåt, kommer denna artikel att planeras 60 dagar framåt.  
1. Ange "2" i fältet **Negativa dagar**.
1. Ange "2" i fältet **Positiva dagar**.
1. Klicka på fliken **Ledtid**.
1. Markera rutan i rubriken för **Inköp**.
1. Ange "5" i fältet **Inköpstid**.
1. Välj **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]