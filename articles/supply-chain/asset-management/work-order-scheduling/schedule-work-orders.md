---
title: Schemalägg arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du tidsplanerar arbetsorder i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderSchdulePreviewPart, EntAssetWorkOrderScheduleExclusively, EntAssetWorkOrderSchduleInfoPart, EntAssetWorkOrderScheduleListPage, EntAssetWorkOrderSchedule, EntAssetWorkOrderScheduleDelete
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7e7751e3e2f216abf46f02ee0644909c6894c5b2
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020239"
---
# <a name="schedule-work-orders"></a>Schemalägg arbetsorder

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet innehåller förklaringar av hur du tidsplanerar arbetsorder i Tillgångshantering. 

Det antal timmar som krävs för en arbetsorder definieras av summan av prognostiserade timmar minus bokförda timmar. Om det krävs mer tid måste prognosen justeras i enlighet med detta. I **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder** kan du visa eller redigera prognoser för en arbetsorder genom att välja arbetsordern och klicka på **Prognos** på fliken **Arbetsorder**. När du har skapat och uppskattat en arbetsorder är nästa steg att fördela de underhållsarbetare och verktyg som krävs för att slutföra arbetsorderna.

Endast arbetsorder med ett livscykeltillstånd för arbetsorder som tillåter planering kan tidsplaneras. Tillåt tidsplanering ställs in i **Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Livscykeltillstånd** >  fliken **Allmänt** > växlingsknappen **Tillåt tidsplanering**.

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder**.

2. Välj de arbetsorder som du vill tidsplanera i listan. Du kan till exempel sortera listan efter **Aktuellt livscykeltillstånd**.

3. Klicka på **Tidsplan** på fliken **Allmänt**.

4. I dialogrutan **Schemalägg arbetsorder** kan du lägga till alternativ för förväntat startdatum och servicenivå, om det behövs. Om tids planeringsprocessen ska ta hänsyn till kapacitetsbegränsningar för resurser som redan har schemalagts för andra jobb, kontrollera att växlingsknapparna **Tillgång**, **Verktyg** och **Arbetare** är inställda på "Ja".

    [!NOTE]
    Om du ställer in växlingsknapparna **Tillgång**, **Verktyg** och **Arbetare** till "Nej" kommer befintliga reservationer att ignoreras. I informationsloggen visas en lista över överlappande arbetsorderscheman, och du kan klicka på meddelandena för att öppna en arbetsorder och omplanera om det behövs.

5. Om du vill visa detaljerad information om tidsplaneringsprocessen väljer du "Ja"på växlingsknappen **Utförligt**. Det innebär att detaljerad information om de beräknade poängen på arbetsorder och underhållsarbetare visas i informationsloggen.

6. Klicka på **OK** när du vill starta tidsplaneringsprocessen.

7. När planeringen är slutförd visar en informationslogg antalet planerade arbetsorder och också mer detaljerad information om växlingsknappen **Utförligt** är inställd på "Ja".

>[!NOTE]
>Arbetsorder planeras i en cykel per arbetsorder, inte per arbetsorderjobb. Du kan också öppna dialogrutan **Tidsplanera arbetsorder** direkt i **Tillgångshantering** > **Periodisk** > **Arbetsorder** > **Tidsplanera arbetsorder**. Gör dina val och klicka på **OK** för att starta tidsplaneringen för arbetsorder. Det går att ställa in arbetsorderplaneringen som ett batchjobb i dialogrutan **Tidsplanera arbetsorder** > snabbfliken **Kör i bakgrunden**.

*Exempel:* På bilden nedan genererar formeln som infogas i fältet **Förväntad start** tidsplanering av arbetsorder för alla arbetsorder med förväntat startdatum en vecka från och med nu och senare. Den här formeln kan vara användbar när du kör tidsplanering av arbetsorder löpande, men du vill vara säker på att de schemalagda arbetsorderna under de kommande 5-6 dagarna inte har tidsplanerats.

![Figur 1](media/03-work-order-scheduling.png)

Arbetsordertypen som är relaterad till arbetsorder kan ställa in tidsplanering för en underhållsarbetare (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Arbetsordertyper** >  växlingsknappen **En underhållsarbetare** inställd på "Ja"). Detta innebär att om arbetsordertypen används på en arbetsorder, sätts växlingsknappen **En underhållsarbetare** automatiskt till "Ja" på informationssidan **Alla arbetsorder** > vyn **Sidhuvud** > snabbfliken **Tidsplanera**. Under tidsplaneringen av arbetsordern planeras sedan alla arbetsorderjobb som skapats på arbetsordern till samma underhållsarbetare. Om det behövs kan du redigera valet för växlingsknappen **En underhållsarbetare** i **Alla arbetsorder** för att möjliggöra planering av flera arbetare eller en arbetare för arbetsorderjobben.

Planeringsprocessen i Tillgångshantering innehåller flera faktorer i planeringsberäkningen:

- Beräkna poängen för både arbetsorder och underhållsarbetare. Resultat för arbetsorder och underhållsarbetare ställs in **Parametrar för tillgångshantering**. 
- Sökning efter matchande kompetenser, dvs. färdigheter och intyg, som krävs för att utföra jobbet. Kompetenser och intyg ställs in på underhållsarbetare i modulen **Personal** (**Personal** > **Arbetare** > **Arbetare** > välj arbetare i listan > fliken **Arbetare** > avsnittet **Kompetenser** > knapparna **Kompetenser** och **Intyg**). Du kan också lägga till kompetenser och intyg i underhållsjobbtyper och yrkesgrenar för underhållsjobb. Läs mer om kompetenser och underhållsjobbtyper i [Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).  

## <a name="scores-used-in-work-order-scheduling"></a>Poäng som används i tidsplanering för arbetsorder

Beräkning av poängen för ett arbetsorderjobb baseras på förväntat startdatum och servicenivån för arbetsordern.

**Startdatum**-beräkning: För varje framtida datum som beräknas från förväntat startdatum subtraheras startdatumets poäng och multipliceras med poängen, som är "10" i exemplen nedan.

**Allvarlighetsgrad**-beräkning: Allvarlighetsgradpoängen multiplicerat med arbetsorderns allvarlighetsgrad.

**Servicenivå**-beräkning: Servicenivåpoängen delas med servicenivån på arbetsordern.

I exemplen nedan är allvarlighetspoängen "2" och servicenivåpoängen är "5" och "100".

**Exempel 1:**

| Arbetsorder-ID | Förväntat startdatum | Allvarlighetsgrad för arbetsorder | Servicenivå för arbetsorder | Beräkning               | Poäng      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | Imorgon            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | Två dagar från nu   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | Två dagar från nu   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

Arbetsorderna kommer att planeras i följande ordning: WO-000108 **16**, WO-000108 **18**, WO-000108 **17**.

**Exempel 2:**

| Arbetsorder-ID | Förväntat startdatum | Allvarlighetsgrad för arbetsorder | Servicenivå för arbetsorder | Beräkning                 | Poäng    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | Imorgon            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | Två dagar från nu   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | Två dagar från nu   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

Om servicenivåpoängen höjs till "100" i stället för "5" blir planeringsordningen: WO-000108 **18**, WO-000108 **16**, WO-000108 **17**.

Bedömningspoängen för att beräkna vilka underhållsarbetare som ska arbeta med arbetsorderna ställs in som siffror som läggs till i varje underhållsarbetares beräkning under arbetsorderplaneringen. Underhållsarbetaren med högsta poäng väljs för arbetsordern. Här följer en kort beskrivning av underhållsarbetarens poäng:

| Poäng för underhållsarbetare| Beskrivning |
|---|---|
| Ansvarig arbetare | Om underhållsarbetaren väljs som ansvarig arbetare på arbetsordern, läggs poängen till. |
| Ansvarig grupp med underhållsarbetare | Om underhållsarbetaren ingår i den ansvariga underhållsarbetargruppen på arbetsordern, läggs poängen till. |
| Prioriterad underhållsarbetare         | Om arbetaren väljs som prioriterad underhållsarbetare på tillgången, läggs poängen till. |
| Prioriterad grupp med underhållsarbetare   | Om arbetaren ingår i den prioriterade underhållsarbetargruppen på tillgången, läggs poängen till.  |
| Plats  | Om ditt företag använder funktionsplatser får underhållsarbetarna full poäng om de finns på den funktionsplats som är relaterad till tillgången. Om funktionsplatsen för tillgången har en överordnad plats, får underhållsarbetare på funktionsplatsen 1/2 poäng. Om den platsen också har en överordnad, får underhållsarbetare på den platsen 1/3 poäng. Om den platsen också har en överordnad, får underhållsarbetare på den platsen 1/4 poäng, osv. Om ditt företag använder tillgångsplats, som vi inte rekommenderar, används plats, område och zon för att beräkna platspoäng. Arbetare får full poäng om de finns på platsen och området och zonen som är relaterade till tillgången. Om arbetsplatsen endast matchar plats och område, är poängen för underhållsarbetaren 2/3 av hela poängen. Om underhållsarbetarens plats endast matchar plats, är poängen för underhållsarbetaren 1/3 av hela poängen. |
| Arbetarens startdatum  | För varje datum som det schemalagda startdatumet är senare än det förväntade startdatumet subtraheras poängen.  |

>[!NOTE]
>Om poängen är inställd på "0" beräknas inte poängen. Detta är användbart om du t.ex. inte vill inkludera ansvarig arbetare i planeringen.

## <a name="competencies-used-in-work-order-scheduling"></a>Kompetenser som används i tidsplanering för arbetsorder

Kompetenser och intygs krav kan ställas in för underhållsjobbtyper (**Tillgångshantering** > **Inställningar** > **Jobb** > **Underhållsjobbtyper**) och yrkesgrenar för underhållsjobb (**Tillgångshantering** > **Inställningar** > **Jobb** > **Yrkesgren för underhållsjobb**). 

Underhållsjobbtyper och yrkesgrenar för underhållsjobb väljs på arbetsorderjobb. Om kompetenser eller intyg har valts för en underhållsjobbtyp eller yrkesgren för underhållsjobb, och den underhållsjobbtypen eller yrkesgrenen för underhållsjobb används för ett arbetsorderjobb, planeras endast underhållsarbetare med matchande kompetenser och intyg för arbete på arbetsordern.

<a name="gantt"></a>

## <a name="work-with-scheduled-work-orders-using-a-gantt-chart"></a>Arbeta med schemalagda arbetsorder med hjälp av ett Gantt-diagram

**Gantt-diagram för schemalagda arbetsorder** ger ett grafiskt gränssnitt där du kan visa och omplanera dina arbetsorder.

Så här visar och arbetar du med Gantt-diagrammet:

1. Gå till **Tillgångshantering > Arbetsorder > Gantt-diagram för schemalagda arbetsorder**.

1. Använd listrutorna och fälten i området **inställningar** när du vill ange vilken funktionsplats, vilket tidsintervall och vilken tidsskala som ska visas i Gantt-diagrammet.

1. Välj **Tillämpa**.

    - Gantt-diagrammet uppdateras för att visa de schemalagda arbetsorder som matchar dina inställningar. Varje arbetsorder representeras av en blå rektangel.
    - Om du vill omplanera en visad arbetsorder väljer du och drar den till lämpligt nytt datum och aktuell tid.

1. Om du har gjort några ändringar väljer du **Spara** i åtgärdsfönstret för att spara dem.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]