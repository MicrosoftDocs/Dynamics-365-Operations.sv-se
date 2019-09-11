---
title: Manuellt skapade arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder manuellt i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875902"
---
# <a name="manually-created-work-orders"></a>Manuellt skapade arbetsorder

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Du kan skapa arbetsorder manuellt på två sätt:

- i **Alla arbetsorder** eller **Aktiva arbetsorder**  
- i **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden** eller **Mina underhållsbegäranden för funktionsplats**.  

## <a name="create-work-order"></a>Skapa arbetsorder

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Klicka på knappen **Nytt**.

3. I listrutan **Skapa arbetsorder** väljer du en arbetsordertyp.

4. Ange en beskrivning om det krävs.

5. Välj till gången för arbetsordern samt en underhållsjobbtyp.

>[!NOTE]
>När du väljer en tillgång är tre flikar tillgängliga: fliken **Mina tillgångar** innehåller tillgångar som är relaterade till de funktionsplatser som du (arbetaren som är inloggad på systemet) kan allokeras till (ställs in i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md)). Om inga funktionsplatser ställs in för en underhållsarbetare i formuläret [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md) kommer fliken **Mina tillgångar** inte att visas. Fliken **aktiva tillgångar** innehåller en lista över alla tillgångar med livscykelstatus "aktiv". Fliken **tillgångsvisning** visar en trädvy över funktionsplatser och tillgångar som är installerade på dessa platser.

6. Välj vid behov **Variant av underhållsjobbtyp** och **Yrkesgren**.

7. Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.

8. Välj förväntade start- och slutdatum i de relaterade fälten.

9. Klicka på **OK** för att skapa en ny arbetsorder.

10. Redigera arbetsordern i **Alla arbetsorder** om det behövs.

- I **Alla arbetsorder** kan du lägga till flera tillgångar i en arbetsorder i informationsvyn genom att lägga till rader på snabbfliken **Underhållsjobb för arbetsorder**. För en tillgång kan du bara välja de typer av underhållsjobb som är definierade för den tillgångstyp som valts för tillgången.  
- Om du har ändrat en tillgångs servicenivå eller en tillgångs allvarlighetsgrad efter att du har använt dem på en arbetsorder (se [Tillgångs tjänstenivå](../setup-for-objects/object-priorities.md) och [Allvarlighetsgrad för tillgång](../setup-for-objects/object-criticalities.md)) är servicenivån eller den allvarlighetsgraden för arbetsordern inte uppdaterad därefter.
- Allvarlighetsgraden på en arbetsorder beräknas om varje gång en arbetsorderrad läggs till eller tas bort från arbetsordern.
- I informationsvyn **Alla arbetsorder** > vyn **Sidhuvud** > snabbfliken **Tidsplanera** kan du välja en ansvarig underhållsgrupp för arbetare eller en ansvarig underhållsarbetare i fälten **Ansvarig grupp** eller **Ansvarig**. Dessa inställningar kan ändras så länge arbetsordern är aktiv, t.ex. när arbetsorderns livscykeltillstånd ändras. Det automatiskt val som görs när arbetsordern skapas baseras på inställningarna i **Ansvariga underhållsarbetare**. Om du lägger till eller tar bort arbetsorderjobb efter att du har skapat en arbetsorder och fältet **Ansvarig grupp** och fältet **Ansvarig** är tomt när du uppdaterar arbetsordern, söker Tillgångshantering efter en möjlig matchning i inställningsformuläret för en ansvarig underhållsarbetargrupp eller ansvarig underhållsarbetare. Om fältet **Ansvarig grupp** eller fältet **Ansvarig** redan är ifyllt när du uppdaterar arbetsordern, görs inga ändringar. 

- I **Underhållsstatus** kan du göra en beräkning för att få en översikt över belastningen på inkommande och slutförda arbetsorder.  

- På snabbfliken **Radinformation** kan du använda fälten **Latitud** och **Longitud** för att lägga till geografiska koordinater för den tillgång som valts i arbetsorderjobbet.  

## <a name="create-related-work-order"></a>Skapa relaterad arbetsorder

Du kan skapa en relaterad arbetsorder till en befintlig arbetsorder om du t.ex. vill arbeta med primära och sekundära arbetsorder. En ny arbetsorder baseras på ett arbetsorderjobb från en befintlig arbetsorder.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj den arbetsorder för vilken du vill skapa en relaterad arbetsorder.

3. Klicka på **Relaterad arbetsorder**.

4. I listrutan **Skapa relaterad arbetsorder** väljer du arbetsorderjobbet som du vill skapa en relaterad arbetsorder för i fältet **Arbetsorderjobb**.

5. Välj en underhållsjobbtyp i fältet **Underhållsjobbtyp** och om det behövs en relaterad variant av underhållsjobbtyp och yrkesgren i **Variant av underhållsjobbtyp** och fältet **Yrkesgren**.

6. Om detta är den första relaterade arbetsorder som du gör, klickar du på alternativknappen **Ny arbetsorder**.

7. Välj en **Arbetsordertyp** och en **Beskrivning** i de relaterade fälten.

8. Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.

9. Ange förväntade start- och slutdatum i de relaterade fälten.

10. Klicka på **OK**. Den nya relaterade arbetsordern visas i listan **Alla arbetsorder**.

11. Om du skapar en relaterad arbetsorder för en arbetsorder som redan har relaterade arbetsorder, kan du lägga till arbetsorderjobbet till en redan relaterad arbetsorder. Detta gör du genom att klicka på alternativknappen **Lägg till i relaterad arbetsorder** i steg 6. Sedan väljer du den relaterade arbetsorder som du vill lägga till ett nytt arbetsorderjobb i. Redigera fälten **Servicenivå**, **Förväntad start** och **Förväntat slut** och klicka på **OK**. Arbetsorderjobbet läggs till i befintlig relaterad arbetsorder.


![Figur 1](media/03-work-orders.png)

**Obs!** Om du har angett en relaterad arbetsordermask i **Parametrar för tillgångshantering** >  länken **Arbetsorder** > fältet **Relaterad arbetsordermask** skapas arbetsorder-ID enligt inställningen för masken. Om ingen relaterad arbetsordermask ställs in används nästa tillgängliga arbetsorder-ID för relaterade arbetsorder.

## <a name="copy-work-order"></a>Kopiera arbetsorder

Det är möjligt att snabbt skapa en ny arbetsorder utifrån en befintlig arbetsorder. Det här sättet att arbeta med arbetsorder skiljer sig från att skapa arbetsorder utifrån underhållsplaner. Det är användbart om du till exempel har en arbetsorder som innehåller många arbetsorderjobb med olika jobb för olika till gångar som ska slutföras med jämna mellanrum.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj den arbetsorder från vilken du vill kopiera innehållet.

3. Klicka på **Kopiera arbetsorder**. Inställningarna för arbetsorder från den valda arbetsordern visas. Om det behövs kan du redigera vissa av fälten.

4. Klicka på **OK** för att skapa den nya arbetsordern.

5. Redigera arbetsordern i **Alla arbetsorder** om det behövs.

>[!NOTE]
>När den nya arbetsordern skapas kopieras viss information direkt från den befintliga arbetsordern. Information om prognoser, verktyg, underhållschecklistor, funktionsplatser, adresser och tidsplanering kopieras inte, utan initieras från de aktuella inställningarna i Tillgångshantering. Det innebär att om ändringar har gjorts i dessa data från tidpunkten för skapandet av den första arbetsordern tills du gjorde en kopia av arbetsordern, inkluderas dessa ändringar i den nya arbetsordern som du har skapat. Exempel är ändringar i prognoser eller uppdaterade underhållschecklistor.


![Figur 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a>Skapa en arbetsorder baserad på en underhållsbegäran

1. Klicka på **Tillgångshantering** > **Allmänt** > **Underhållsbegäranden** > **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden**.

2. Välj den underhållsbegäran som du vill skapa en arbetsorder för och klicka på **Redigera**.

3. I **Alla begäranden**, klicka på **Arbetsorder**.

4. Fyll i listrutan **Arbetsorder**. Om en underhållsjobbtyp har valts i underhållsbegäran kan du välja en annan underhållsjobbtyp om det behövs, när du skapar arbetsordern.

5. Klicka på **OK**. Ett meddelande visas som informerar dig om att arbetsordern har skapats.

6. Om du vill se vilka arbetsorder som är kopplade till en underhållsbegäran väljer du underhållsbegäran i listan **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden** och klickar på knappen **Arbetsorder**.


![Figur 3](media/05-work-orders.png)


>[!NOTE]
>Arbetsorder kan också skapas automatiskt genom planering av underhållsplanjobb, eller genom att ställa in underhållsplaner eller underhållsomgångar för Autoskapa på en tillgång. Arbetsorder som skapas från underhållsbegäranden i **Underhållsschema** skapas med de underhållsjobbtyper som väljs i underhållsbegärandena.

