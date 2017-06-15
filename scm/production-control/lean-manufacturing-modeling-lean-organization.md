---
title: Utforma en smidig organisation
description: "Det här avsnittet innehåller information om nyckelkoncepten för modellering av en lean organisation."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ec9191054a1b3587ebbde16acf278084cbd22660
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="modeling-a-lean-organization"></a>Utforma en smidig organisation

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om nyckelkoncepten för modellering av en lean organisation. 

Ett lean manufacturing-scenario är mer än bara en samling orelaterade kanban-regler eller policyer för materialleverans. Flödet av material och produkter genom hela arbetsgrupper och platser för ett visst produktions- eller leveransscenario kan beskrivas som en sekvens eller ett litet nätverk av process- eller överföringsaktiviteter. Sekvensen eller nätverket kallas för produktionsflöde.

## <a name="production-flows-in-lean-manufacturing"></a>Produktionsflöden i lean manufacturing
I produktionsscenarier baserade på produktionsorder tilldelas material till en specifik produktionsorder. Under en sekvens av operationer som baseras på en strukturlista (BOM) och flöden skapas produkter som sedan tas emot på den angivna platsen. Ledtiden för produktionsorder varierar från minuter till veckor. Alla relaterade kostnader, material och arbetskraft ackumuleras i produktionsordern. 

Lean manufacturing stöder kanban-lagerpåfyllnad och storlager för tillverknings- och lagerpåfyllnad för att minska de leveransledtider och överskottslager mellan resurser som orsakas av batchproduktion. De här funktionerna stör vanligtvis produktionen av delvis oberoende kanban-cykler. Lagerpåfyllnad av en kanban för en halvfärdig produkt utlöses inte längre av en order för en färdig produkt. 

Aktivitetsbaserade produktionsflöden utgör nu en grund för lean manufacturing och används för att återupprätta ett produktions- och kostnadssammanhang för de olika kanban-scenarier som föreslås i Microsoft Dynamics AX. Alla kanbankort regler se här fördefinierade struktur. Den aktivitetsbaserade modellen stöder inställning av ett bredare spektrum av scenarier än tidigare versioner av lean manufacturing för Dynamics AX gav stöd för. Den här modellen försvårar dock inte arbetet för medarbetarna i butiken eftersom alla scenarier använder samma aktivitetsbaserade användargränssnittet.

## <a name="semi-finished-products-non-bom-levels"></a>Halvfabrikat (icke-BOM-nivåer)
Lean manufacturing för Microsoft Dynamics AX integrerar kanban för inventerade och halvfärdiga produkter inom ett och samma ramverk och ger därför en enhetlig användarupplevelse för samtliga fall. Tack vare denna arkitektur behöver inga ytterligare strukturlistenivåer längre införas för att kanban ska kunna användas för halvfärdiga produkter. Arkitektur bidrar även till att minska lagertransaktionerna till ett minimum.

## <a name="products-and-material-in-work-in-progress"></a>Produkter och material i pågående arbete
Minskningen av batchstorlekar till det ideala tillståndet för ett engångsflöde i lean manufacturing kan orsaka en dramatisk ökning av lagertransaktioner om varje plockningsprocess eller kanban-registrering orsakar transaktioner för förbrukade artiklar. Produktionsflödets arkitektur tillåter överföring av material till produktionsflödet tillsammans med tillbakadragandet av kanban i lagrings- eller transporthanteringsenhetsstorlekar. Värdet av uttaget material läggs till i kontot för produkter i arbete (PIA) som är kopplat till produktionsflödet. Det här beteende liknar beteendet för material som tilldelas till en produktionsorder. Samma princip kan tillämpas för produkter och halvfärdiga produkter. Om de här produkterna skapas, överförs eller förbrukas inom ett produktionsflöde är lagertransaktioner valfria. När produkter har bokförts till lager minskas PIA-kontot för produktionsflödet genom avdrag av relaterad standardkostnad.

## <a name="value-streams-and-value-stream-mapping"></a>Värdeströmmar och mappning av värdeström
Arkitekturen i lean manufacturing för Microsoft Dynamics AX är inspirerad av fem lean-principer som utformades av Womack och Jones: kundnytta, värdeström, flöde, hämtning och perfektion. En godkänd metod för att implementera lean manufacturing-lösningar i den fysiska världen för tillverkningen är mappning av värdeströmmen (VSM). Den här metoden introducerades av Rother och Shook i deras publikation "Att lära sig att se" på Lean Manufacturing-institutet. 

En framtida värdeström kan modelleras i Microsoft Dynamics AX som en produktionsflödesversion. Alla processer av värdet stream är modellerade som bearbetar verksamheter. Rörelser eller överföringar kan modelleras som överföringsaktiviteter om överföringsstatusen måste vara registrerad eller om en integrering med lagerplockning eller konsoliderade leveranser krävs. 

Värdetströmmen i sig modelleras som en driftenhet i Microsoft Dynamics AX. Värdeströmmen kan därför användas som en ekonomisk dimension.

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>Kostnadsredovisning för lean manufacturing baseras på produktionsflödet.
Den periodiska sammanställningen av kostnaden för ett produktionsflöde korrigerar det relaterade PIA-kontot och möjliggör att varianser kan fastställas för de produkter som levereras via produktionsflödet.

## <a name="continuous-improvement"></a>Kontinuerlig förbättring
För att bättre stödja kontinuerlig förbättring, produktionsflöden genomförs i tid och versioner. En befintlig produktionsflödesversion kan av den anledningen, tillsammans med alla relaterade kanban-regler, kopieras till en kommande version av produktionsflödet. Dessutom kan det framtida tillståndet för produktionsflödet modelleras innan det valideras och aktiveras för produktion. Befintliga kanban från gamla produktionsflödesversioner är automatiskt kopplade till den nya versionen för att säkerställa ett sömlöst materialflöde på övergångsdatumet och därefter.

## <a name="simplicity"></a>Enkelhet
För genomförandet av Lean Manufacturing för Dynamics AX har vi valt ett produktionsflöde och en aktivitetsmetod som möjliggör modellering av enkla och komplexa scenarier i en enda skalbar arkitektur. En närmare titt på aktivitetskonceptet avslöjar en ny enkelhet för de användarna som verkligen behöver det: butiksgolvet och logistikpersonalen. Genom att rapportera mot verksamhetsbaserad jobb istället för lagertransaktioner, ett enhetligt användargränssnitt för alla lean manufacturing varianter överför företag komplexitet från användargränssnittet där det hör hemma: produktionsflödet som ryggraden i lean manufacturing.



