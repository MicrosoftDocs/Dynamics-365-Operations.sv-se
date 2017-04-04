---
title: "Åtgärdssökning"
description: "I artikeln beskrivs sökfunktionen i Microsoft Dynamics 365 för åtgärden. Åtgärden Sök hjälper dig hitta och köra åtgärder på en sida."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 689d8f9fb0501c5007db21d41f126737af77b89e
ms.lasthandoff: 03/31/2017


---

# <a name="action-search"></a>Åtgärdssökning

I artikeln beskrivs sökfunktionen i Microsoft Dynamics 365 för åtgärden. Åtgärden Sök hjälper dig hitta och köra åtgärder på en sida.

<a name="introduction"></a>Introduktion
------------

Sidor i Microsoft Dynamics 365 för operationer visas främst kommandon i åtgärdsfönster som visas i olika delar av sidan verktygsfälten och standard åtgärdsfönstret som visas högst upp på en sida. I tidigare versioner kan ett Tips för funktionen du snabbt komma åt knapparna i ett åtgärdsfönster genom att trycka på ALT och en serie bokstäver. 

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) dock Tips för i den aktuella versionen av Dynamics 365 för operationer är inte längre tillgängliga men har ersatts av funktionen Sök åtgärd. Den här nya funktionen kan du snabbt söka efter och kör en knapp från synliga rutan Åtgärd.

## <a name="using-action-search"></a>Med hjälp av action sök
För att använda åtgärden sökfunktionen, följ dessa steg.

1.  I åtgärdsrutan, klicka i **sökfältet** . ( **åtgärden sökfältet** innehåller en förstoringsglaset).
2.  Skriv hela eller en del av namnet på den knapp som du vill köra. Du kan också söka genom att använda ord från knappens "sökväg". (Mer information finns i nästa avsnitt i den här artikeln.) Vanligtvis visas en knapp längst upp i resultatlistan när du har skrivit två till fyra tecken.
3.  Hitta och köra i resultatlistan (genom att använda din mus eller tangentbord).

När du kör, fokus återgår till din senaste position på sidan, så att du kan fortsätta att arbeta. 

[![åtgärden sökfältet](./media/action-search-field.png)](./media/action-search-field.png)

Du kan också starta åtgärden sökning, genom att pressa Ctrl+/- eller Alt+Q. Tryck på kortkommandot igen för att återgå till din senaste position på sidan.

## <a name="understanding-the-results-list"></a>Förstå resultaten förteckning
I Dynamics 365 för operationer, måste du ofta veta både på platsen och i samband med en knapp för att förstå syftet med den här knappen. Därför visas ytterligare information för varje post i resultatlistan som hjälper dig att förstå exakt vilka knappar som visas i listan. I synnerhet "sökväg" på knappen visas. Den här sökvägen kan inkludera etiketter av följande UI-beståndsdelar:

-   Rutan åtgärd flik
-   Knappgrupp
-   Knappen meny (om knappen är placerad inuti en meny-knapp)
-   Menyn separator (om knappen är placerad inuti en namngiven grupp inuti en meny-knapp)
-   Grupp eller flik på sidan (t.ex. namnet på en snabbfliken)

Exempelvis du maskinskrev **tot** i **sökfältet** och granskar nu resultat listan. Den första transaktionen för en knapp som heter **summor**, markeras. En knapp sökväg till **försäljningsorder**&gt;**visa** visas också. Den **försäljningsorder** delen i sökvägen som motsvarar den **försäljningsorder** flik i åtgärdsfönstret, och **visa** delen i sökvägen som motsvarar den **visa** gruppen på fliken. Dessutom sökvägen till den **totalrabatt** knappen (**säljer**&gt;**beräkna**) informerar dig om att den här knappen finns i den **beräkna** på de **säljer** fliken i åtgärdsfönstret. Därför kan hjälper den här informationen dig att förstå exakt vilken knapp som utlöser åtgärden Sök (om du väljer knappen i resultatlistan). 

[![åtgärden Sök-fältet-med-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png) 

I föregående exempel visade åtgärdsökningen resultat från det vanliga åtgärdsfönstret överst på sidan. Men action sök visar också resultaten från synligt verktygsfält som finns på andra ställen på sidan. Till exempel söker efter den **lagerbehållning** som finns på den **försäljningsorderrader** på snabbfliken. I det här fallet knappen sökvägen i resultatlistan (**försäljningsorderrader**&gt;**lager**&gt;**visa**) informerar dig om att den här knappen finns under den **visa** rubrik på de **lager** menyknappen på den **försäljningsorderrader** på snabbfliken. 

[![i lager](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Åtgärd söka vs. navigation sökningen
Åtgärden Sök har till syfte att hitta och köra åtgärder på en sida, finns en separat sökfunktionen för att söka efter och navigera till sidor i Dynamics 365 för operationer. Mer information om funktionen finns på [navigering Sök](navigation-search.md) artikel.


