---
title: Ställ in ett platsdirektiv för artikelinförsel av inköpsorder
description: Det här avsnittet innehåller information om hur du ställer in ett enkelt platsdirektiv.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b07cd8af0fd619a71d3fe5188f41d0a0ed954f93
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438039"
---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Ställ in ett platsdirektiv för artikelinförsel av inköpsorder

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller information om hur du ställer in ett enkelt platsdirektiv. I exemplet som visas skapas ett platsdirektiv som ska användas för att fastställa var du vill placera artiklar som har tagits emot för en inköpsorder. Du kan spela upp den här uppgiftsguiden med nämnda data med hjälp av demonstrationsdataföretaget USMF. Förutsättningar: Du måste skapa en dispositionskod. I den här proceduren använder vi dispositionskoden Relabel. Om du skapar ett platsdirektiv i dina egna data måste du ha ställt in avancerad lagerhantering för dina lagerställen och artiklar. Den här proceduren är avsedd för lagerchefen.

1. I navigeringsfönstret, gå till **Moduler > Lagerstyrning > Inställningar > Platsdirektiv**.
2. Välj **Inköpsorder** i fältet **Typ av arbetsorder**.

## <a name="create-a-location-directive-header"></a>Skapa en platsdirektivrubrik
1. Välj **Ny**.
2. Ange ett nummer i fältet **Sekvensnummer**. Det här är den ordning som platsdirektiven bearbetas i för vald arbetstyp. Du kan också ändra sekvensen, om det behövs.  
3. Skriv ett värde i fältet **Namn**. Detta är den unika identifieraren för det här direktivet.  
4. Välj **Placera** i fältet **Arbetstyp**. Välj den typ av arbete som ska utföras. För direktiv med arbetsordertypen Inköpsorder är **Placera** det enda värdet som stöds.  
5. Ange ett värde i fältet **Plats**.
6. Ange ett värde i fältet **Lagerställe**. Lämna direktivkoden tom.  Direktivkoder används för att länka en arbetsorderrad av typen Placera till ett visst direktiv. För inköpsorder kommer platsen för den senaste arbetsorderraden av typen Placera att matchas innan arbetsmallen fastställs. Därför går det inte att koppla den sista raden i en arbetsmall till ett visst direktiv.   
7. Skriv ett värde i fältet **Dispositionskod**. Dispositionskoden begränsar användningen av platsdirektivet, så platsdirektivet används bara om lagerställearbetaren anger det specifika värdet under registreringen av artikeln med en mobil enhet.  
8. Välj **Spara**.

## <a name="edit-the-query-for-directive"></a>Redigera frågan för direktiv
1. Välj **Redigera fråga**. Användningen av detta direktiv har redan begränsats för användning för registrerade artiklar i lagerstället som du angav, och med dispositionskoden som du angav. Du kan lägga till andra begränsningar med hjälp av frågan.  
2. Välj **OK**.

## <a name="add-directive-lines"></a>Lägg till direktivrader
1. Välj **Ny**. Det här är den ordning som platsdirektivraderna bearbetas i för vald arbetstyp. Du kan också ändra sekvensen, om det behövs.  
2. Ange ett värde i fältet **Från kvantitet**. Detta är den lägsta kvantitet som direktivraden är giltig för.  
3. Ange ett värde i fältet **Till kvantitet**.
4. Fältet **Enhet** anger du ett värde. Enheten som Från-kvantiteten och Till-kvantiteten uttrycks i. Om du låter det här fältet vara tomt används lagerenheten för artikeln.  
5. Välj ett alternativ i fältet **Hitta kvantitet**.
    - Inga eller registreringsskyltskvantitet: Kvantiteten som har registrerats på respektive registreringsskylt.  
    - Sammansatt kvantitet: Hela kvantiteten som har registrerats.  
    - Resterande kvantitet: Den kvantitet som fortfarande ska registreras från inköpsorderraden.  
    - Förväntad kvantitet: Den totala kvantiteten som anges på inköpsorderraden.  
6. Markera eller avmarkera kryssrutan **Begränsa per enhet**. Om du väljer det här alternativet och anger enheten på sidan **Begränsa per enhet** kan bara artiklar med den måttenheten placeras på platsen. Om till exempel måttenheten är lastpallar kan endast artiklarna på lastpallar placeras på en specifik plats.  
7. Markera eller avmarkera kryssrutan **Tillåt delning**. Detta gör att direktivet kan dela kvantiteten mellan flera platser.  
8. Välj **Spara**.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Begränsa direktivraden till en viss enhet
1. Välj **Begränsa per enhet**. Den här knappen är bara tillgänglig när du trycker på **Spara** efter att du har markerat kryssrutan **Begränsa per enhet**.  
2. Fältet **Enhet** anger du ett värde.
3. Stäng sidan.

## <a name="add-a-location-directive-action-line"></a>Lägg till åtgärdsrad för platsdirektiv
1. Välj **Ny**. Det här är den ordning som platsdirektivåtgärdsraderna bearbetas i för vald arbetstyp. Du kan också ändra sekvensen, om det behövs.  
2. Skriv ett värde i fältet **Namn**. Detta är den unika identifieraren för den här direktivåtgärden.  
3. Välj ett alternativ i fältet **Användning av fast lagerplats**.
    - Fasta och inte fasta lagerplatser: Alla icke-fasta platser är giltiga samt produktens egen fasta plats, inom det intervall som angetts i frågan.  
    - Endast fast lagerplats för produkten: Fasta platser för produkten är giltiga, och alla produktvarianter delar samma uppsättning fasta platser.  
    - Endast fast lagerplats för produktvarianterna: Endast fasta platser som anges för varje produktvariant är giltiga.  
4. Välj ett alternativ i fältet **Strategi**. Arbetsorder av typen inköpsorder stöder följande strategier: 
    - Ingen: artikeln placeras på den första plats som hittas.  
    - Konsolidera: Artikeln placeras på en plats där liknande artiklar redan är tillgängliga.  
    - Tom plats utan inkommande arbete: Artikeln placeras på den första tomma plats som hittas. En plats anses vara tom om den inte har något fysiskt lager och inget förväntat inkommande arbete.  
5. Välj **Spara**.

## <a name="edit-the-query-for-directive-action-line"></a>Redigera frågan för direktivåtgärdsrad
1. Välj **Redigera fråga**.
2. Markera **Lägg till**.
3. I fältet **Fält**, ange `location profile ID`. I det här exemplet ska du begränsa de möjliga platserna med hjälp av ett platsprofil-ID.  
4. I fältet **Kriterier** skriver du ett värde.
5. Välj **OK**. Du kan fortsätta att lägga till direktivrader och direktivåtgärder tills du har täckt alla möjliga scenarier i ditt lagerställe.  

