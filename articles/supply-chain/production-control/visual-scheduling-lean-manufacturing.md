---
title: "Visuell tidsplanering för lean manufacturing"
description: "Det här avsnittet innehåller information om kanban-schematavlan som produktionsplaneraren kan använda för att styra och optimera produktionsplanen för kanban-jobb."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 6218f54364e096bdd718ea35edb0b3666e65f2c1
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="visual-scheduling-for-lean-manufacturing"></a>Visuell tidsplanering för lean manufacturing

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om kanban-schematavlan som produktionsplaneraren kan använda för att styra och optimera produktionsplanen för kanban-jobb.

Det här avsnittet innehåller information om kanban-schematavlan som produktionsplaneraren kan använda för att styra och optimera produktionsplanen för kanban-jobb.

Kanban-schematavlan tillåter produktionsplaneraren att styra och optimera produktionsplanen för kanban-jobb. Det gör flödet för kanban-jobb transparent och ger produktionsplaneraren ett verktyg som optimerar och justerar produktionsplanen för arbetsgruppen för lean manufacturing.

## <a name="visual-scheduling-of-kanban-jobs"></a>Visuell tidplanering av kanban-jobb
Ett kanban-jobb kan bestå av en eller flera kanban-jobb. Det finns två typer av kanban-jobb:

-   Bearbeta
-   Överför

Du kan bara tidsplanera jobb av typen **Process**. Kanban-jobbet och dess egenskaper, till exempel aktivitetstid, har definierats i produktionsflödet kanban. Vid produktionen av kanban-flödet tilldelas även en arbetsgrupp till kanban-jobbet. Arbetsgruppens dagliga kapacitet beräknas utifrån arbetsgruppens kapacitet som har angetts för resursgruppen. Den har justerats efter den dagliga arbetstid i den relaterade kalendern. När ett kanban-jobb tidsplaneras laddar jobbet kapaciteten för arbetsgruppen. Kanban-schematavlan ger följande huvudfunktioner:

-   En grafisk översikt över produktionsplanen i en resurssnål arbetsgrupp. Den här översikten visar planerade kanban-processjobb i angivna perioder.
-   Ett verktyg som gör att du kan tidsplanera oplanerade kanban-jobb och tidsplanera om tidigare schemalagda jobb.

## <a name="kanban-schedule-board"></a>Kanban-schematavla
Sidan **Kanban-schematavla** innehåller sju huvudelement som visas på bilden nedan. 

![Kanban-schematavla](./media/kanban-schedule-board-1024x554.png)
1.  Åtgärdsfönster
2.  Filtrera fält
3.  Knapp för oförutsedda jobb
4.  Periodnod
5.  Kanban-jobb
6.  Kapacitetsstapel
7.  Tidsskala

### <a name="view-the-time-scale"></a>Visa tidsskalan

Tavlan är indelad i perioder som var och en representeras av en nod (4). Periodens noder visas på den lodräta axeln och den vågräta åtkomsten representerar en tidsskala (7) som visar periodens längd. En period är antingen en dag eller en vecka. Periodens längd fastställs av konfigurationen av den arbetsgrupp som valts för kanban-schematavlan (2). Kanban-schematavlan anger hur många planerade kanban-jobb som läser in under perioden för varje periodnod. Det finns även en indikation på maximalt flöde under perioden. Om det planerade flödet överskrider det maximala flödet, anses perioden vara överbelastad och en röd varningssymbol visas. Ett tidsplanerat kanban-jobb visas under en period som har tidsplanerade start- och sluttider (5). Jobbets varaktighet motsvarar aktivitetstiden. Kanban-jobb visas som överlappning under en period om deras aktivitetstider överskrider takttiden för arbetsgruppen.

### <a name="view-job-status"></a>Visa jobbstatus

Mer information om ett kanban-jobb finns i knappbeskrivningen som visas när du för pekaren över jobbet. En symbol innehåller information om statusen på jobbet. Exempelvis indikerar en klocksymbole att kanban-jobbet har förfallit.

### <a name="use-colors-to-view-the-kanban-schedule-board"></a>Använda färger för att visa kanban-schematavlan

Du kan använda färger för att förbättra översikten över kanban-schematavlan och särskilja kanban-jobb. Färgen på kanban-jobb konfigureras i den resurssnåla schemagruppen där du kan aggregera produkter som ska produceras i samma ordning. Med knappen **Använd temafärger** i fliken **Tavla** i åtgärdsfönstret kan du växla mellan programmets temafärger och färgerna som har konfigurerats i den resurssnåla schemagruppen. För varje period visar en kapacitetsstapel (6) hur många av antalet tillgängliga timmar för perioden som har lästs in med kanban-jobb. Om perioden är överbelastad är kapacitetsstapeln tjockare och röd. Alla dessa funktioner är tillgängliga i fliken **Tavla** i åtgärdsfönstret (1) högst upp på sidan **Kanban-schematavla**.

## <a name="plan-unplanned-jobs"></a>Planera oplanerade jobb
Du kan schemalägga oplanerade kanban-jobb från dialogrutan **Planera oförutsedda jobb**. Om du vill öppna den här dialogrutan, klicka på knappen **Oplanerade jobb** som visar det aktuella antalet oplanerade jobb. Alternativt kan du klicka på **Planera oplanerade jobb** i fliken **Tavla** i åtgärdsfönstret. I dialogrutan visas en lista med oplanerade kanban-jobb för arbetsgruppen. Du kan använda fältet **Filter** för att filtrera efter alla fält i rutnätet. Du kan till exempel filtrera på kanban-jobb för en viss produkt. När du har skapat en filtrerad lista över de jobb som du vill tidsplanera markerar du dem i listan och klickar sedan på **OK**. Om du vill använda automatisk planering för att tidsplaner, ställ in alternativet **Automatisk planering** på **Ja**. I detta fall tidsplaneras jobben till en period efter sina förfallodatum. Du kan också tidsplanera jobb per period. Välj bara en period i fältet **Period**. Följande bild visar ett exempel på dialogrutan **Planera oplanerade jobb**. 

![Dialogrutan Planera oplanerade jobb](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a>Sekvensen kanban-jobb inom samma period
Du kan ändra ordningen på en eller flera valda jobb inom en period. Detta kan vara användbart om du vill prioritera vissa jobb under perioden. Alternativt kan behöva du ordna jobb som har samma produktattribut i sekvens för att optimera körningen. Du kan ändra ordningen genom att dra och släppa eller genom att använda menyalternativen **Bakåt** och **Framåt** på fliken **Tavla** i åtgärdsfönstret.

## <a name="reassign-kanban-jobs-across-periods"></a>Tilldela om kanban-jobb över perioder
Jobb kan tilldelas om från en period till en annan. Den här funktionen kan vara användbar om en period är överbelastad och du vill utjämna belastningen för perioder som har ledig kapacitet. Du kan tilldela om jobb genom att dra och släppa eller genom att använda menyalternativen **Nästa period** och **Föregående period** på fliken **Tavla** i åtgärdsfönstret.

## <a name="open-the-kanban-schedule-board"></a>Öppna kanban-schematavlan
Du kan öppna kanban-schematavlan genom att använda menyalternativet på följande sidor:

-   Sidan **Produktionsområde**
-   Sidan **Planering av kanban-jobb**
-   Sidan **Visualisering av produktionsflöde**


<a name="see-also"></a>Se även
--------

[Lean manufacturing – Kanban-jobbplanering](lean-manufacturing-kanban-job-scheduling.md)


