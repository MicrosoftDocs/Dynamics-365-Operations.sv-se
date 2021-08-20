---
title: Manuellt skapade arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder manuellt i Tillgångshantering.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a755fa579d929056296c5512f976d15c4808c336b6688b891a4712051e15e9a1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750110"
---
# <a name="manually-created-work-orders"></a>Manuellt skapade arbetsorder

[!include [banner](../../includes/banner.md)]


Du kan skapa arbetsorder manuellt på två sätt:

- På sidan **Alla arbetsorder** eller **Aktiva arbetsorder** 
- PÅ sidan **Alla underhållsbegäranden**, **Aktiva underhållsbegäranden** eller **Mina underhållsbegäranden för funktionsplats**. 

## <a name="create-work-order"></a>Skapa arbetsorder

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj **Ny**.

3. I dialogrutan **Skapa arbetsorder** väljer du en arbetsordertyp i fältet **arbetsordertyp**.

4. Ange en **beskrivning** om det krävs.

5. Välj tillgången i fältet **Tillgång**.

>[!NOTE]
>När du väljer en tillgång kan det hända att tre flikar är tillgängliga i listrutan **tillgång**: 

- **Aktiva tillgångar** - Den här fliken innehåller en lista över alla tillgångar som har livscykelstatus "aktiv". 
- **Tillgångsvisning** - Den här fliken visar en trädvy över funktionsplatser och tillgångar som är installerade på dem.
- **Mina tillgångar** – Den här fliken innehåller tillgångar som är relaterade till de funktionella platser som du (som är inloggade på systemet) kan fördelas på. (Mer information om inställningarna finns i [underhållsarbetare och arbetsgrupper](../setup-for-objects/workers-and-worker-groups.md).) Om inga funktionella platser har ställts in för en arbetare [underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md) är fliken **mina tillgångar** inte tillgängliga. 

6. I fältet **typ av underhållsjobb**, välj en typ av underhållsjobb för arbetsordern.

7. Välj vid behov **Variant av underhållsjobbtyp** och **Yrkesgren**.

8. Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.

9. Välj datum för **Förväntad start** och **Förväntad slut** i de relaterade fälten.

10. Klicka på **OK** för att skapa arbetsordern.

11. På listsidan **Alla arbetsorder** kan du redigera arbetsordern som du behöver.

Observera följande:

- I informationsvyn på listsidan **Alla arbetsorder** kan du lägga till flera tillgångar i en arbetsorder genom att lägga till rader på snabbfliken **Underhållsjobb för arbetsorder**. För en tillgång kan du bara välja de typer av underhållsjobb som är definierade för den tillgångstyp som valts för tillgången.  

- Om du ändrar en tillgångs tjänstenivån eller allvarlighetsgrad är den här tillgången på arbetsorder, tjänstenivå eller allvarlighetsgrad på allvarlighetsgraden på arbetsordern i enlighet med detta. Mer information om tjänstenivåer och allvarlighetsgrad finns i [Tillgångs tjänstenivå](../setup-for-objects/object-priorities.md) och [Allvarlighetsgradtyper för tillgång](../setup-for-objects/object-criticalities.md).

- Allvarlighetsgraden på en arbetsorder beräknas om varje gång en arbetsorderjobb läggs till eller tas bort från arbetsordern.

- I informationsvyn **Alla arbetsorder** > fliken **Sidhuvud** > snabbfliken **Tidsplanera** i **Ansvarig grupp** eller **Ansvarig** kan du välja en ansvarig underhållsgrupp för arbetare eller en ansvarig underhållsarbetare. Dessa inställningar kan ändras när arbetsordern är aktiv. De kan till exempel ändras när arbetsorderns livscykeltillstånd. Det automatiskt val som görs när arbetsordern skapas baseras på inställningarna på sidan **Ansvariga underhållsarbetare**. Om du lägger till eller tar bort arbetsorderjobb efter att du har skapat en arbetsorder och fältet **Ansvarig grupp** och fältet **Ansvarig** är tomt när du uppdaterar arbetsordern, söker Tillgångshantering efter en möjlig matchning i inställningsformuläret för en ansvarig underhållsarbetargrupp eller ansvarig underhållsarbetare. Om **Ansvarig grupp** eller **Ansvarig** redan är ifyllt när du uppdaterar arbetsordern, görs inga ändringar. För mer information om ansvariga underhållsarbetare och arbetargrupper, se [Ansvariga underhållsarbetare](../setup-for-maintenance-requests/responsible-workers.md).

- Från sidan [Underhållsstatus](../controlling-and-reporting/maintenance-status.md) kan du göra en beräkning för att få en översikt över belastningen på inkommande och slutförda arbetsorder.  

- I detaljvyn på sidan **Alla arbetsorder** på snabbfliken **Raddetaljer** kan du använda fälten **Latitud** och **Longitud** för att lägga till geografiska koordinater för den anläggnings tillgång som valts för arbetsorderjobbet.  


## <a name="create-related-work-order"></a>Skapa relaterad arbetsorder

Du kan skapa en arbetsorder som är relaterad till en befintlig arbetsorder. Den här funktionen är användbar om du till exempel vill arbeta med primära och sekundära arbetsordrar. En ny arbetsorder baseras på ett arbetsorderjobb från en befintlig arbetsorder.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder för att skapa en relaterad arbetsordning för.

3. I åtgärdsfönstret, på fliken **Arbetsorder**, i gruppen **New**, väljer du **Relaterad arbetsorder**.

4. I listrutan **Skapa relaterad arbetsorder** i fältet **arbetsorderjobb** välj arbetsordern att skapa en relaterad arbetsorder för.

5. Välj underhållsjobbtyp i fältet **Underhållsjobbtyp**.

6. I fälten **Variant av underhållsjobbtyp** och **Yrkesgren** väljer varianten av underhållsjobbtypen och en yrkesgren för underhållsjobbtypen.

7. Gör så här om denna arbetsorder är den första relaterade arbetsorder som har skapats för den valda arbetsordern:
    1. Välj alternativet **ny arbetsorder**.
    2. I fältet **arbetsordertyp** väljer du en arbetsorder.
    3. Ange en beskrivning i **beskrivning**.
    4. Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.
    5. I fälten **Förväntad start** and **Förväntad slut** välj förväntade start- och slutdatum.
    6. Välj **OK**. Den nya relaterade arbetsordern visas på listsidan **Alla arbetsorder**.  

8. Om arbetsordern som du skapar den relaterade arbetsordern för redan har relaterade arbetsorder, följer du dessa steg för att lägga till ett nytt arbetsorderjobb i en befintlig relaterad arbetsorder:
    1. Välj alternativet **Lägg till i relaterade arbetsorder**.
    2. I fältet **arbetsorder** väljer du den relaterade arbetsorder som du vill lägga till ett nytt arbetsorderjobb till.
    3. Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.
    4. I fälten **Förväntad start** and **Förväntad slut** ändra förväntade start- och slutdatum efter behov.
    5. Välj **OK**. Arbetsorderjobbet läggs till i befintlig relaterad arbetsorder.

I bilden nedan visas ett exempel på sidan dialogrutan **Skapa relaterad arbetsorder**.

![Figur 1.](media/03-work-orders.png)

>[!NOTE]
>Om du har angett en relaterad arbetsordermask i **Parametrar för tillgångshantering** fliken  > **Arbetsorder** > fältet **Relaterad arbetsordermask** skapas arbetsorder-ID enligt inställningen för masken. Om ingen relaterad arbetsordermask ställs in används nästa tillgängliga arbetsorder-ID för relaterade arbetsorder.

## <a name="copy-a-work-order"></a>Kopiera arbetsorder

Det är möjligt att snabbt skapa en ny arbetsorder utifrån en befintlig arbetsorder. Det här sättet att arbeta med arbetsorder skiljer sig från att skapa arbetsorder utifrån [underhållsplaner](../preventive-and-reactive-maintenance/maintenance-plans.md). Det är användbart om du till exempel har en arbetsorder som innehåller många arbetsorderjobb med olika jobb för olika till gångar som ska slutföras med jämna mellanrum.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj den arbetsorder från vilken du vill kopiera innehållet.

3. I åtgärdsfönstret, på fliken > **Arbetsorder**, i gruppen **New**, väljer du **Kopiera arbetsorder**.

4. Inställningarna för arbetsorder från den valda arbetsordern visas. Om det behövs kan du redigera vissa av fälten.

5. Klicka på **OK** för att skapa den nya arbetsordern.

6. På listsidan **Alla arbetsorder** kan du redigera arbetsordern som du behöver.

>[!NOTE]
>När den nya arbetsordern skapas kopieras viss information direkt från den befintliga arbetsordern. Information om prognoser, verktyg, underhållschecklistor, funktionella platser, adresser och tidsplanering kopieras inte. I stället initieras den från de aktuella inställningarna i tillgångshantering. Om informationen ändras mellan den tidpunkt då den första arbetsordern skapades och den tidpunkt då du gjorde en kopia av arbetsordern, inkluderas därför ändringarna i den nya arbetsordern. Exempel är ändringar i prognoser eller uppdaterade underhållschecklistor.

Illustrationen nedan visar ett exempel på dialogrutan **Kopiera arbetsorder**.

![Figur 2.](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a>Skapa en arbetsorder baserad på en underhållsbegäran

1. Klicka på **Tillgångshantering** > **Allmänt** > **Underhållsbegäranden** > **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden**.

2. Välj den underhållsbegäran som du vill skapa en arbetsorder för och klicka på **Redigera**.

3. I åtgärdsfönstret, på fliken > **Underhållsbegäran**, i gruppen **New**, väljer du **Arbetsorder**.

4. Ställ in fälten i dialogrutan **Arbetsorder**. Om en underhållsjobbtyp har valts i underhållsbegäran kan du välja en annan underhållsjobbtyp om det behövs, när du skapar arbetsordern.

5. Välj **OK**. Meddelandet informerar dig om att en arbetsorder har skapats.

6. Om du vill se vilka arbetsorder som är kopplade till en underhållsbegäran väljer du **Alla underhållsbegäran** i listan **Aktiva underhållsbegäran** och underhållsbegäran. Sedan i åtgärdsfönstret på fliken **Underhållsbegäran** i gruppen **Vy** väljer du **Arbetsorder**.


Illustrationen nedan visar ett exempel på dialogrutan **Skapa arbetsorder**.

![Figur 3.](media/05-work-orders.png)


>[!NOTE]
>Om du vill att arbetsordrar ska skapas automatiskt kan du schemalägga underhållsplanjobb eller så kan du ställa in "Skapa automatiskt" [underhållsplaner](../preventive-and-reactive-maintenance/maintenance-plans.md) eller [underhållsrundor](../preventive-and-reactive-maintenance/maintenance-rounds.md) på en tillgång. Arbetsorder som skapas från underhållsbegäranden på listsidan **All underhållsschema** har samma underhållsjobbtyper som väljs i underhållsbegärandena.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]