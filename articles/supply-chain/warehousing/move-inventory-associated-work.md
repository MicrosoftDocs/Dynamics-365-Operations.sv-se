---
title: Lagerrörelse med tillhörande arbete i lagerstyrning
description: Det här avsnittet beskriver hur du ställer in och använder bekräftelse av komponentplockning från en mobil enhet.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2aee3af8da6610c16fc2d98091bfa3f01f1bd0f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437632"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>Lagerrörelse med tillhörande arbete i lagerstyrning

[!include [banner](../includes/banner.md)]

Med hjälp av rörligt lager kan du bestämma vilka lagerarbetare som ska kunna flytta reserverat lager. Detta ger en flexibilitet i reglerade lagerställen där du kan välja att inte tillåta en arbetare kan välja en ny plockningsplats för plockningsarbete som redan har skapats. Det gör det också möjligt för en lagerchef att kontrollera vilka funktioner som ska mer ovana arbetare bör ha.

Möjligheten att hantera lagerarbetares dagliga verksamhet kan vara användbar i situationer som dessa:

## <a name="scenario-1"></a>Scenario 1
Ett företag har ett relativt litet mottagnings område som är överbelastat med lastpallar och kartonger som väntar på att förflyttas. En stor försändelse förväntas den aktuella dagen, varför mottagande lageransvarige beslutar sig för att rensa inleveransområdet genom att flytta några lastpallar till ett sekundärt inkommande mellanlagringsområde.

## <a name="scenario-2"></a>Scenario 2
En erfaren lagerarbetare upptäcker en möjlighet att på ett lager konsolidera artiklar på en och samma plats, i stället för att sprida ut dem över tre närliggande platser med liten mängd på respektive plats. Arbetaren vill konsolidera kvantiteten genom att flytta artiklar från var och en av dessa platser till samma plats och samma registreringsskylt.

## <a name="scenario-3"></a>Scenario 3
En pall inväntar leverans på en lagringsplats, till exempel STAGE01 som ligger nära BAYDOOR01. På grund av ändrade planer kommer dock trucken att anlända till BAYDOOR04. Den leveransansvarige är medveten om detta och måste säkerställa att trucken inte behöver vänta på att lastas från STAGE01. Den leveransansvarige bestämmer sig för att flytta artiklar i den sändningen från STAGE01 till STAGE04, vilket ligger närmare den nya destinationen.

### <a name="current-limitations"></a>Aktuella begränsningar

De arbetsreservationer som du kan flytta begränsas till försäljningsorder, problem med överföringsorder, överföringsorderkvitto, inköpsorder och lagerpåfyllnadsarbete.

Att flytta objekt begränsas i syfte att förhindra delning av arbetsrader. Detta innebär att om du har en arbetsrad på 100 enheter av artikel A från platsen Loc1, så kan du inte flytta endast 30 stycken av artikel A därifrån till en annan plats. Detta skulle leda till en delning av den befintliga arbetsraden till 30 och 70, detta eftersom platserna nu skiljer sig åt.

I syfte att inte dela upp målregistreringsskylten medges endast förflyttning av hela registreringsskylten på de lagringsplatser där den registreringsskylt som du flyttar varor från eller till anges som målregistreringsskylt för en arbetsorder.
Endast ad hoc-transport stöds i nuläget. Det innebär att du inte kan flytta reserverat lager genom förflyttning via mallmenyalternativen för mobil enhet.

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>Ange behörighet för att flytta reserverade varor för individuella medarbetare

För den arbetare som ska kunna flytta reserverat lager väljer du kryssrutan **Tillåt flytt av lager med associerat arbete** under **Lagerstyrning** > **Inställningar** > **Arbetstagare**.  

### <a name="backported"></a>Anpassning i efterhand

Denna funktion har också anpassats i efterhand för Microsoft Dynamics AX 2012 R3 och blir tillgänglig som en del av CU12.
Den kan också hämtas separat via KB-nummer 3192548. 

