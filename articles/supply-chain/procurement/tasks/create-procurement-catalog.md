--- 
title: Skapa en anskaffningskatalog
description: "Den här guiden visar hur du skapar en anskaffningskatalog."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: df844ba3834972441daa61899294b3e95cac96c1
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-procurement-catalog"></a>Skapa en anskaffningskatalog

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här guiden visar hur du skapar en anskaffningskatalog. Den här uppgiften utförs vanligtvis av ett anskaffningsproffs. Du kan också lära dig om hur medarbetare kan använda katalogen när de skapar en rekvisition. Innan du kan skapa en katalog måste det finnas en anskaffningskategorihierarki i systemet. Hierarkin ärvs från den nya katalogen, tillsammans med alla produkter som finns i hierarkin. Du kan använda den här handboken i demonstrationdataföretaget USMF, där anskaffningskategorihierarkin är tillgänglig, samt i exemplen som används i procedurstegen.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Se till att en anskaffningskategorihierarki finns
1. Gå till Anskaffning och källa > Anskaffningskategorier.
    * En anskaffningskategorihierarki är tillgänglig i demoföretaget USMF och produkter har lagts till i kategorin kontorsmaskiner/datorer. Om du kör den här proceduren som en uppgiftsguide måste du låsa upp guiden om du vill bläddra genom kategorin. Om en hierarki inte är tillgänglig kan du skapa den genom att klicka på Ny. Detta kan bara göras en gång.  
2. Stäng sidan.

## <a name="create-a-catalog"></a>Skapa en katalog
1. Gå till Anskaffning och källa > Kataloger > Anskaffningskataloger.
2. Klicka på Ny anskaffningskatalog om du vill öppna dialogrutan.
3. Skriv ett värde i fältet Namn.
4. Klicka på OK.
5. Expandera ”ANSKAFFNINGSKATEGORIER FÖR FÖRETAG" i trädet.
6. Expandera "KONTORSMASKINER" i trädet.
7. Välj "Datorer" i trädet.
    * Produkterna från anskaffningkategorin visas i listan. Om du vill lägga till en produkt till en kategori måste du göra detta på sidan Anskaffningskategorihierarki eller på sidan Artikeldetaljer.  
    * Standarduppdateringstypen bestämmer om nya produkter som har lagts till i anskaffningskategorihierarkin omedelbart är synliga i katalogen. Om uppdateringstypen är inställd på Dynamisk kommer ändringar att synas på en gång. Om uppdateringstypen är Statisk är nya produkter endast synliga för personer som använder katalogen efter att katalogen har publicerats igen. Åtgärden Publicera är tillgänglig i åtgärdsfönstret överst på sidan. Om produkter tas bort från anskaffningskategorihierarkin är ändringen omedelbart synlig oavsett värdet i fältet Standarduppdateringtyp.  
8. Hitta och markera önskad post i listan.
9. Klicka på Dölj.
10. Klicka på Kategorinavigering i åtgärdsfönstret.
11. Klicka på Avaktivera.
12. Klicka på Kategorinavigering i åtgärdsfönstret.
13. Klicka på Aktivera.
14. Klicka på Aktivera katalog.
15. Stäng sidan.

## <a name="make-the-catalog-visible"></a>Gör katalogen synlig
1. Gå till anskaffning och källa > Inställningar > Policyer > Inköpspolicyer.
2. Välj anskaffningspolicy USMF.
    * Du måste välja inköpspolicyn för den juridiska person som arbetaren kopplade till din användarprofil, som tillåter att beställa in produkter. I USMF-demonstrationdatan är användaren Admin kopplad till arbetaren som kallas Julia Funderburk, och hon beställer produkter i USMF som standard.  
3. Klicka på länken på den valda raden i listan.
4. Välj katalogen som du nyss skapat.
5. Klicka på OK.
6. Stäng sidan.
7. Stäng sidan.

## <a name="use-the-catalog"></a>Använd katalogen
1. Gå till Anskaffning och källa > Inköpsrekvisitioner > Alla inköpsrekvisitioner.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Klicka på OK.
5. Klicka på Lägg till produkter.
6. Hitta och markera önskad post i listan.
    * Du kan använda kategorihierarkin till vänster eller filtret högst upp i listan om du vill filtrera).  
7. Klicka på Lägg till på rader.
8. Hitta och markera önskad post i listan.
9. Klicka på Lägg till på rader.
10. Klicka på OK.


