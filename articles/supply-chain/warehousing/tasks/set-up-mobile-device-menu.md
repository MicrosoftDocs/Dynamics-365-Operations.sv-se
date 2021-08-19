---
title: Ställ in ett menyalternativ för mobila enheter för att utföra arbete av typen Inköpsorder
description: I det här avsnittet visas hur du ställer in ett menyalternativet för mobila enheter.
author: ShylaThompson
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFAutoConfirm, WHSRFMenu
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5df02b1ab1ac5531d54641fd523e3e671d83395ec3d627a0aaf7b1f783e9ad24
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735049"
---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order"></a>Ställ in ett menyalternativ för mobila enheter för att utföra arbete av typen Inköpsorder

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du ställer in ett menyalternativet för mobila enheter. I det här exemplet används menyalternativet för att utföra arbete av typen Inköpsorder. Arbetsklassen som associeras med menyalternativet bestämmer vilket arbete som är giltigt. Du kan använda den här guiden i demonstrationsföretaget USMF. Vanligtvis utförs den här proceduren av en lagerchef.


## <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter
1. Gå till **Menyalternativ på mobil enhet** genom att ange det i sökfältet.
2. Välj **Ny**.
3. Ange ett värde i fältet **Menyalternativnamn**. Ange ett unikt värde. Du kan exempelvis skriva `POMove`. Kom ihåg värdet, du behöver det senare.  
4. Ange ett värde i fältet **Rubrik**. Detta är den rubrik som visas för användaren på den mobila enheten. Du kan exempelvis skriva `PO Move`.  
5. Välj **Arbete** i fältet **Läge**.
6. Välj **Ja** i fältet **Använd befintligt arbete**.
    - Menyobjektet för den här mobila enheten används för att utföra befintligt arbete. Du måste därför ange värdet till **Ja**.  
    - Statusfältet **Visa lagerstatus** avgör om lagerstatusen för lagerbehållningen visas för lagerarbetare på den mobila enheten.  
7. Välj **Systemgruppering** i fältet **Dirigerad av**. När du väljer något i fältet **Dirigerad av** visas ytterligare fält avsnittet **Allmänt** på den här sidan. Fälten som visas beror på vad du har valt. När du väljer **Systemgruppering** läggs två nya fält till. Dessa beskrivs nedan.  
8. I fältet **Systemgruppering** välj **WorkPoolId**. När lagerarbetare öppnar den här menyartikeln uppmanas de att skanna ett arbetspool-ID. Alla arbetsorder med detta arbetspool-ID och öppna arbetsorderrader med en av arbetsklasserna som läggs till i det här menyalternativet kommer att skickas till användaren.  
9. Skriv ett värde i fältet **Etikett för systemgruppering**. Den här är texten som visas för användaren på den mobila enheten Du kan exempelvis skriva **Arbetspool**.  
10. Välj **Ja** i fältet **Åsidosätt registreringsskylt under placering**. Det här alternativet kan lagerarbetare använda för att åsidosätta målregistreringsskylten när artiklar placeras på en registreringsskyltsstyrd plats.  
11. Välj **Ja** i fältet **Grupplats**.
    - Om alla inleveransrader på arbetsordern delar samma plats får användaren en kombinerad placeringsinstruktion för alla rader. 
    - ID för granskningsmall: med hjälp av en arbetsgranskningsmall kan du ange hur arbetsprocessen för ett menyalternativ ska avbrytas så att en annan åtgärd kan utföras. Om till exempel det här menyalternativet är till för inkommande arbete kan granskningsmallen kräva att arbetstagaren kontrollerar temperaturen. Den punkt som processen avbryts vid anges på revisionsmallen och kan vara, till exempel, när jobbet har påbörjats eller avslutats, eller när dess status ändras.  
12. Expandera avsnittet **Arbetsklasser**.
13. Välj **Ny**.
14. I fältet **Arbetsklass-ID**, skriv `Purchase`. Arbetspoolen begränsar det arbete menyalternativet kan användas för. I det här fallet kommer den att användas för öppna orderrader som har inköpsarbetsklass-ID.  
15. Välj **Spara**.

## <a name="set-up-work-confirmation"></a>Ställ in arbetsbekräftelse
1. Välj **Inställning av arbetsbekräftelse**.
2. I fältet **Arbetstyp**, välj **Välj**.
3. Markera kryssrutan **Bekräfta automatiskt**. Arbetsinstruktionen med arbetstypen Plockning kommer att bekräftas automatiskt. Denna instruktion visas inte för användaren.  
4. Välj **Ny**.
5. Välj Placera i fältet **Arbetstyp**.
6. Markera kryssrutan **Platsbekräftelse**. Lagerarbetaren kommer att uppmanas att utföra en bekräftelsescanning av platsen när artikeln införs.  
7. Välj **Spara**.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Lägg till menykommandot på en meny för mobila enheter
1. Gå till menyn **Mobil enhet** genom att ange det i sökfältet.
2. Välj **Redigera**.
3. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet **Namn** med värdet **inkommande**. Du vill söka efter på menyn som du använder för inkommande menyalternativ. I USMF kallas detta **Inkommande**.  
4. Välj **ett värde** i trädet.
5. Välj pilen som pekar åt höger.
6. Välj **Spara**.
7. Stäng sidan.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]