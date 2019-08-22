---
title: Ställ in ett menyalternativ för mobila enheter för att utföra arbete av typen Inköpsorder
description: I den här proceduren visas hur du ställer in ett menyalternativet för mobila enheter.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFAutoConfirm, WHSRFMenu
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 707fc9c798da8eac30cc9f56c158be3d96b271d6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847121"
---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order"></a>Ställ in ett menyalternativ för mobila enheter för att utföra arbete av typen Inköpsorder

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du ställer in ett menyalternativet för mobila enheter. I det här exemplet används menyalternativet för att utföra arbete av typen Inköpsorder. Arbetsklassen som associeras med menyalternativet bestämmer vilket arbete som är giltigt. Du kan använda den här guiden i demonstrationsföretaget USMF. Vanligtvis utförs den här proceduren av en lagerchef.


## <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter
1. Gå till Menyalternativ på mobil enhet.
2. Klicka på Ny.
3. Skriv ett värde i fältet Menyalternativ.
    * Ange ett unikt värde. Du kan exempelvis skriva POMove. Kom ihåg värdet, du behöver det senare.  
4. Ange ett värde i fältet Titel.
    * Detta är den rubrik som visas för användaren på den mobila enheten. Du kan exempelvis skriva PO Move.  
5. Välj Arbete i fältet Läge.
6. Välj Ja i fältet Använd befintligt arbete.
    * Menyobjektet för den här mobila enheten används för att utföra befintligt arbete. Du måste därför ange värdet Ja.  
    * Statusfältet Visa lagerstatus avgör om lagerstatusen för lagerbehållningen visas för lagerarbetare på den mobila enheten.  
7. Välj Systemgruppering i fältet Dirigerad av.
    * När du väljer något i fältet Dirigerad av visas ytterligare fält avsnittet Allmänt på den här sidan. Fälten som visas beror på vad du har valt. När du väljer Systemgruppering läggs två nya fält till. Dessa beskrivs nedan.  
8. Välj "WorkPoolID" i fältet Fält för systemgruppering.
    * När lagerarbetare öppnar den här menyartikeln uppmanas de att skanna ett arbetspool-ID. Alla arbetsorder med detta arbetspool-ID och öppna arbetsorderrader med en av arbetsklasserna som läggs till i det här menyalternativet kommer att skickas till användaren.  
9. Skriv ett värde i fältet Etikett för systemgruppering.
    * Den här är texten som visas för användaren på den mobila enheten Du kan exempelvis skriva Arbetspool.  
10. Välj Ja i fältet Åsidosätt registreringsskylt under placering.
    * Det här alternativet kan lagerarbetare använda för att åsidosätta målregistreringsskylten när artiklar placeras på en registreringsskyltsstyrd plats.  
11. Välj Ja i fältet Grupplats.
    * Om alla inleveransrader på arbetsordern delar samma plats får användaren en kombinerad placeringsinstruktion för alla rader.  
    * ID för granskningsmall: med hjälp av en arbetsgranskningsmall kan du ange hur arbetsprocessen för ett menyalternativ ska avbrytas så att en annan åtgärd kan utföras. Om till exempel det här menyalternativet är till för inkommande arbete kan granskningsmallen kräva att arbetstagaren kontrollerar temperaturen. Den punkt som processen avbryts vid anges på revisionsmallen och kan vara, till exempel, när jobbet har påbörjats eller avslutats, eller när dess status ändras.  
12. Expandera arbetsklassavsnittet.
13. Klicka på Ny.
14. Skriv "Inköp" i fältet Arbetsklass-ID.
    * Arbetspoolen begränsar det arbete menyalternativet kan användas för. I det här fallet kommer den att användas för öppna orderrader som har inköpsarbetsklass-ID.  
15. Klicka på Spara.

## <a name="set-up-work-confirmation"></a>Ställ in arbetsbekräftelse
1. Klicka på Inställning av arbetsbekräftelse.
2. Välj Välj i fältet Arbetstyp.
3. Markera kryssrutan Bekräfta automatiskt.
    * Arbetsinstruktionen med arbetstypen Plockning kommer att bekräftas automatiskt. Denna instruktion visas inte för användaren.  
4. Klicka på Ny.
5. Välj Placera i fältet Arbetstyp.
6. Markera kryssrutan Platsbekräftelse.
    * Lagerarbetaren kommer att uppmanas att utföra en bekräftelsescanning av platsen när artikeln införs.  
7. Klicka på Spara.
8. Stäng sidan.
9. Stäng sidan.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Lägg till menykommandot på en meny för mobila enheter
1. Gå till Meny på mobil enhet.
2. Klicka på Redigera.
3. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Namn med värdet inkommande.
    * Du vill söka efter på menyn som du använder för inkommande menyalternativ. I USMF kallas detta Inkommande.  
4. Välj ett värde i trädet.
5. Klicka på pilen som pekar åt höger.
6. Klicka på Spara.
7. Stäng sidan.

