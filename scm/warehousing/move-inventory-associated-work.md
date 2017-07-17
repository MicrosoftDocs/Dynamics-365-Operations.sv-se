---
title: "Lagerrörelse med tillhörande arbete i lagerstyrning"
description: "Det här avsnittet beskriver hur du ställer in och använder bekräftelse av komponentplockning från en mobil enhet."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: d2db0431a3f749cbdaf35cc5108851f1e116bc96
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017


---

# Lagerrörelse med tillhörande arbete i lagerstyrning
<a id="movement-of-inventory-with-associated-work-in-warehouse-management" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Med hjälp av rörligt lager kan du bestämma vilka lagerarbetare som ska kunna flytta reserverat lager. Detta ger en flexibilitet i reglerade lagerställen där du kan välja att inte tillåta en arbetare kan välja en ny plockningsplats för plockningsarbete som redan har skapats. Det gör det också möjligt för en lagerchef att kontrollera vilka funktioner som ska mer ovana arbetare bör ha.

Möjligheten att hantera lagerarbetares dagliga verksamhet kan vara användbar i situationer som dessa:

## Scenario 1
<a id="scenario-1" class="xliff"></a>
Ett företag har ett relativt litet mottagnings område som är överbelastat med lastpallar och kartonger som väntar på att förflyttas. En stor försändelse förväntas den aktuella dagen, varför mottagande lageransvarige beslutar sig för att rensa inleveransområdet genom att flytta några lastpallar till ett sekundärt inkommande mellanlagringsområde.

## Scenario 2
<a id="scenario-2" class="xliff"></a>
En erfaren lagerarbetare upptäcker en möjlighet att på ett lager konsolidera artiklar på en och samma plats, i stället för att sprida ut dem över tre närliggande platser med liten mängd på respektive plats. Arbetaren vill konsolidera kvantiteten genom att flytta artiklar från var och en av dessa platser till samma plats och samma registreringsskylt.

## Scenario 3
<a id="scenario-3" class="xliff"></a>
En pall inväntar leverans på en lagringsplats, till exempel STAGE01 som ligger nära BAYDOOR01. På grund av ändrade planer kommer dock trucken att anlända till BAYDOOR04. Den leveransansvarige är medveten om detta och måste säkerställa att trucken inte behöver vänta på att lastas från STAGE01. Den leveransansvarige bestämmer sig för att flytta artiklar i den sändningen från STAGE01 till STAGE04, vilket ligger närmare den nya destinationen.

### Aktuella begränsningar
<a id="current-limitations" class="xliff"></a>

De arbetsreservationer som du kan flytta begränsas till försäljningsorder, problem med överföringsorder, överföringsorderkvitto, inköpsorder och lagerpåfyllnadsarbete.

Att flytta objekt begränsas i syfte att förhindra delning av arbetsrader. Detta innebär att om du har en arbetsrad på 100 enheter av artikel A från platsen Loc1, så kan du inte flytta endast 30 stycken av artikel A därifrån till en annan plats. Detta skulle leda till en delning av den befintliga arbetsraden till 30 och 70, detta eftersom platserna nu skiljer sig åt.

I syfte att inte dela upp målregistreringsskylten medges endast förflyttning av hela registreringsskylten på de lagringsplatser där den registreringsskylt som du flyttar varor från eller till anges som målregistreringsskylt för en arbetsorder.
Endast ad hoc-transport stöds i nuläget. Det innebär att du inte kan flytta reserverat lager genom förflyttning via mallmenyalternativen för mobil enhet.

### Ställa in behörighet för att flytta reserverat lager för enskilda arbetstagare
<a id="set-up-the-permission-to-move-reserved-inventory-for-individual-workers" class="xliff"></a>

För den arbetare som ska kunna flytta reserverat lager väljer du kryssrutan **Tillåt flytt av lager med associerat arbete** under **Lagerstyrning** > **Inställningar** > **Arbetstagare**.  

### Anpassning i efterhand
<a id="backported" class="xliff"></a>

Denna funktion har också anpassats i efterhand för Microsoft Dynamics AX 2012 R3 och blir tillgänglig som en del av CU12.
Den kan också hämtas separat via KB-nummer 3192548. 


