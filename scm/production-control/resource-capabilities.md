---
title: Resurskunskaper
description: "Det här avsnittet innehåller information om resurskapaciteter. En kapacitet är möjligheten hos en verksamhetsresurs att utföra en viss aktivitet. Det här avsnittet ger en beskrivning av hur kapaciteter och relaterade koncept såsom kompetensnivå och prioritet kan används för att välja lämpliga resurser för en aktivitet."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WrkCtrCapability, WrkCtrTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29961
ms.assetid: 30e38233-2a64-4070-911f-8ffd78dd8281
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4463ca8e11115eb83323716faa4ed6b38937a3e4
ms.lasthandoff: 03/31/2017


---

# <a name="resource-capabilities"></a>Resurskunskaper

Det här avsnittet innehåller information om resurskapaciteter. En kapacitet är möjligheten hos en verksamhetsresurs att utföra en viss aktivitet. Det här avsnittet ger en beskrivning av hur kapaciteter och relaterade koncept såsom kompetensnivå och prioritet kan används för att välja lämpliga resurser för en aktivitet.

En kapacitet är möjligheten hos en verksamhetsresurs att utföra en viss aktivitet. Ett resurs kan ha mer än en kapacitet som tilldelats den, och en funktion kan tilldelas mer än en resurs. Du kan tillfälligt tilldela funktioner till resurser genom att definiera ett startdatum och förfallodag på kapacitet. När kapaciteten för en resurs ut resursen kan inte planeras för ett projekt eller en produktion som kräver att kapaciteten. En funktion som har löpt ut kan förnyas. Du kan ta bort kapacitet, förutsatt att de inte på en rutt relation eller en del av en produktion av en aktiv produktionsorder. I allmänhet, var försiktig när du tar bort funktioner. Låt istället justera utgångsdatumet på resurser som har kapacitet. Funktioner kan tilldelas till alla typer av resurser: verktyg, säljaren, maskin, plats, byggnad eller mänskliga resurser.

## <a name="level"></a>Nivå
Flera resurser ofta har samma funktionella kapacitet men på olika nivåer av kunskaper (t.ex. styrka, processorhastighet och noggrannhet). Därför, när du tilldelar en kapacitet till en resurs, kan du ange ett **Nivå** värde. Nivån är en enkel numerisk värde. Om du anger att en funktion är resursbehovet för en produktion rutt kan du även ange en **lägsta nivå som behövs** för funktionen. Det scheduling motor väljer bara de resurser som har behov kapacitet på en nivå som är lika med eller överstiger den miniminivå som anges i resursbehov.

## <a name="priority"></a>Prioritet
Verksamheten resurser att ha samma funktioner kan tilldelas en prioritet. Om flera resurser har funktioner som uppfyller kraven vid den erforderliga nivån schemaläggning och har lediga kapacitet kan planeringsmotorn Markera mellan resurserna. Om **prioritet** väljs i den **primära resursurvalet** på de **planeringsparametrar** sidan, den resurs som har högst prioritet (det lägsta numeriska värdet i den **prioritet** fältet) markeras första under tidsplaneringen.

## <a name="resource-requirements"></a>Resurskrav
När du definierar resursbehov för en produktion rutt kan du specificera en eller flera funktioner såsom krav. Under produktionsplanering, funktioner som definieras i resursbehovet på flödesoperation matchas med funktioner som är definierade för resurser. Resurser som har kapacitet att uppfylla kraven är markerade. Om flera resurser har samma funktionella kapacitet men olika kunskaper (t.ex. styrka, processorhastighet, eller noggrannheten) kan du antingen ange flera funktioner eller använd funktionen för att utvärdera möjligheten till resursen. Här är ett exempel:

-   Om en rutt, borrningen tid är satt till 10 enheter per timme, men kravet är definierad som borrning.
-   Du har två borrmaskiner, M1 och M2.
-   Borrning kapacitet har tilldelats både resurser, M1 och M2-maskinen.
-   M1-maskinen kan borra två enheter per timme och M2-maskinen kan borra 11 enheter per timme.

I detta exempel, båda maskinerna kan väljas av scheduling motor, eftersom både uppfyller grundläggande krav på kapacitet (borrning). Men M1 maskin kan borra endast två enheter per timme. Eftersom det är mycket mindre än 10 enheter per timme som är angivna på rutten, M1-maskinen kommer att orsaka problem om det är valt. Det finns två sätt att lösa det här problemet och se till att M2-maskinen är markerad i stället:

-   Skapa två separata funktioner: Låg hastighet detaljgranskning och hög hastighet detaljgranskning. Definiera lågvarviga borrning som borrning som har en process för en till nio enheter per timme. Definiera höghastighetståg borrning som borrning som har en borrningen tid av 10 till 19 enheter per timme. Sedan tilldelar M1 maskinen långsamma sjöss kapacitet, och tilldelar M2 maskinen snabba sjöss kapaciteten. Ändra slutligen resursbehov kapacitet i flödet till snabb borrning. Det scheduling motor kommer sedan att välja rätt maskin (M2).
-   Använd funktionen för att utvärdera borrning kapacitet som är tilldelad till borrmaskiner. Ange att maskinen M1 har Drilling kapacitet med 2.0 och att maskinen M2 Drilling kapacitet på nivån 11.0. Ange sedan att 10.0 är miniminivå som krävs för Drilling kunskapsbehov i flödet. Det scheduling motor kommer sedan att avgöra att endast M2 maskin uppfyller de krav på resurser.

## <a name="competencies-for-human-resources"></a>Kompetenser för mänskliga resurser
När du har operationer resurser av **mänskliga resurser** som är kopplade till anställda i mänskliga resurser, du kan fattar dessutom fördel av kompetenser för arbetstagare när du definierar resursbehovet för en produktion rutt. Med andra ord kan du också ange krav på specifik kompetens, kurser, certifikat, eller titlar. Det scheduling motor kan sedan välja resurser som är kopplade till arbetstagare, och valet baseras på kompetenser för dessa arbetstagare. De kompetenser som finns i mänskliga resurser, inte på **Resource kapaciteter** . När du definierar färdigheter, kurser, intyg och titlar som resursbehov, måste du använda funktionen personal och länka varje resurs i den **personal** typ till motsvarande arbetaren. Om du inte använder funktionen personal kan du definiera kapacitet på de **resurskunskaper** sida som liknar eller duplicera kompetenser från personalavdelningen. Men **resursen kapacitet** inte sidan innehåller den funktionalitet som krävs för att bibehålla kompetens, kurser, certifieringar, eller titlar.


