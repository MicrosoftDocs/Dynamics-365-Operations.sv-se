---
title: Bearbeta kompensation
description: "Kompensationsbearbetning gör att du kan beräkna nya baskompensationsbelopp för personalen utifrån justeringar av eget kapital, meritökningsmål och prestanda."
author: kherr
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 6e30357b0bca8745b69bff19a55828b180c3b829
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Bearbeta kompensation
<a id="process-compensation" class="xliff"></a>
Kompensationsbearbetning gör att du kan beräkna nya baskompensationsbelopp för personalen utifrån justeringar av eget kapital, meritökningsmål och prestanda. I det här blogginlägget beskrivs det grundläggande flödet för kompensationsbearbetning för fasta kompensationsplaner utan att räkna med prestanda.

## Planera det nya kompensationsbeloppet och budgetar
<a id="plan-the-new-compensation-amounts-and-budgets" class="xliff"></a>
Om du vill ge dina anställda en meritökning, måste du konfigurera en fasta ökningsbudgetför var och en av dina avdelningar: Kompensationshantering > Länkar > Meritökningsmål. (Du kan också öppna formuläret via Avdelning: Organisation > Avdelningar.) Här kan du specificera i mer detalj om medarbetare i en viss fackförening eller på en viss plats skulle ha en annan ökningsprocent. Fälten **Budget** och **Valuta** är informativa och kan användas för att anteckna ett valutabelopp för budgeten.

## Ställa in kompensationsprocessen
<a id="set-up-the-compensation-process" class="xliff"></a>
En processhändelse tillåter att du anger parametrar för kompensationsbearbetning. Detta omfattar utvärderingsdatumperioden för att fastställa kompensationsbeloppen.  och det datum då de nya kompensationsbeloppen ska träda i kraft.

Du kan även inkludera en fast lön proportionellt från anställningsdatumet om någon av er fasta kompensationsplaner använder en anställningsregel i procent. För dessa planer kan alla som anställdes efter Cykelns startdatum och före Fast lön proportionellt från anställningsdatumet få 100 % av sin beräknade meritökning eller allmänna ökning. Alla som anställdes efter Fast lön proportionellt från anställningsdatumet och före Cykelns slutdatum får en del av sin beräknade ökning baserat på hur många dagar av det totala antalet cykeldagar de har varit anställda. Till exempel, om vår cykel löper från den 1 januari till den 31 december och vi har en Fast lön proportionellt från anställningsdatumet den 1 April, får en medarbetare som anställts i mars den fullständiga beräknade ökningen medan en medarbetare som anställdes den den 1 juli får ungefär hälften av den beräknade ökningen.

Datumet för processhändelsen **Tidpunkt** används endast för att bearbeta vissa variabla kompensationsplaner och beskrivs inte i det här blogginlägget. **Tidsgräns för granskning** är den tidsgräns då alla rekommendationer måste ha inkommit, så att nya kompensationsbelopp kan läsas in i medarbetarposten. Datumet för granskning är endast för information.

När parametrarna för processhändelsen har sparats kan du klicka på knappen **Inställningar** för att bekräfta vilka planer som ska ingå i den här processkörningen och vilka åtgärder för fast kompensation som ska vidtas för varje plan.

Klicka på knappen **Lägg till** i den övre fliken om du vill lägga till en kompensationsplan i processhändelsen. Kolumnerna **Använd annan påverkan**, **Påverkansfaktor** och **Påverkansbeskrivning** används bara för variabla kompensationsplaner och omfattas inte av det här avsnittet.

Spara posten och klicka sedan på knappen **Lägg till** i den nedre fliken för att lägga till fasta kompensationsåtgärder för den markerade planen. Använd alternativet Aktivera rekommendationer om du vill kunna ange ett annat belopp än den beräknade riktlinjeökningen för åtgärden. Om du vill att en åtgärd ska beräknas baserat på resultatet av den föregående åtgärden och länka flera kompensationsåtgärder, markera alternativet Använd föregående resultat. Fasta kompensationsåtgärder är typer av kompensationslogik som du kan tilldela beskrivande namn till. För Klass- och Band-planer kan du bara lägga till fasta kompensationsåtgärder som är av följande typer:

| Typen Fast kompensationsåtgärd | Funktionalitet                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Eget kapital                        | Eget kapital-åtgärder jämför medarbetarens lönesats per cykelns slutdatum med lägsta referenspunkten för de nivåer som anges för medarbetarens jobb. Om medarbetarens lönesats är lägre än den minsta referenspunkten beräknas ökningen som krävs för att få medarbetaren till den lägsta punkten i listan.                                                                                |
| Merit                         | Meritåtgärder beräknar en ökning baserad på medarbetarens lönesats per cykelns slutdatum och ökningen i procent som finns i den fasta ökningsbudgeten för medarbetarens avdelning, fackförening och plats.                                                                                                                                                                                         |
| Allmänt                       | Allmänna åtgärder beräknar en ökning på grundval av antingen en procentsats eller ger de anställda ett fast belopp. Detta avgörs utifrån inställningarna för den fasta kompensationen på fliken Allmänt.                                                                                                                                                                                                                        |
| Befordran                     | Erbjudandeåtgärder som ger dig en namngiven plats där du kan tilldela ökningen, så kom ihåg att markera alternativet **Aktivera rekommendation** så att du kan skriva en rekommendation för medarbetare som ska ta emot erbjudanden.  Medarbetare utan en rekommenderad ökning kommer inte att ha erbjudandeåtgärden tillagd i sina poster för fast kompensation.                                                                       |
| Annan nivåändring            | I exemplet ovan är Omplacering namnet på vår fasta kompensationsåtgärd med en typ av annan nivåändring. Då skapas en 0-riktlinjeökning (nollökning) så att du kan ange ett rekommendationsbelopp om du vill justera medarbetarens lönesats. (Glöm inte att markera alternativet **Aktivera rekommendation**.) Medarbetare utan en rekommendation har inte den här åtgärden tillagd i sina poster för fast kompensation. |

Du kan bara lägga till Fasta kompensationsåtgärder till typen Steg för steg-plan.

| Åtgärdstypen Fast kompensation | Funktionalitet                                                                                                                                                                                           |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Steg                           | Ange om stegåtgärden ska flytta medarbetaren framåt 0 steg, 1 steg eller två steg på fliken Allmänt.                                                                                  |
|                                | **0 steg** – Medarbetaren får lönesatsen för det aktuella steg som han/hon befinner sig på.                                                                                                                      |
|                                | **1 steg** – Systemet kontrollerar om medarbetaren redan är på sista referenspunkten för nivån.                                                                                             |
|                                | **2 steg** – Systemet flyttar fram medarbetaren två steg i den aktuella nivån. Systemet kanske bara flyttar en medarbetare ett eller noll steg om de uppnår den sista referensenspunkten för nivån. |

## Kör kompensationsprocessen
<a id="run-the-compensation-process" class="xliff"></a>
När processhändelsen har ställts in med nödvändiga datumfält, planer och åtgärder kan du klicka på **Kör process** på händelsesidan Processhändelse. När du gör det öppnas händelsedialogrutan Kör kompensationsprocess. I den här dialogrutan kan du klicka på alternativet **Visa processresultat** för att se hur kompensationsbeloppen beräknades för varje medarbetare. Om du klickar på **OK** körs kompensationsprocessen för alla medarbetare som ingår i de valda kompensationsplanerna för cykelns slutdatum.

## Visa processresultaten
<a id="view-the-process-results" class="xliff"></a>
Om du vill visa processresultaten, öppna sidan **Processresultat**. En ny kompensationshändelse skapas varje gång processhändelsen körs. På så sätt kan du göra testkörningar, justera och köra kompensationshändelsen flera gånger för att se hur olika ändringar påverkar medarbetarkompensation.

Sidan Processresultat innehåller information om processkörningen, inklusive när körningen inträffade, användaren som körde processen och om eventuella fel uppstod när processen körs. Du kan även markera alternativet **Låst** för att inaktivera den knappen **Läs in kompensation** och förhindra ett någon laddar kompensationshändelser till medarbetarposterna. Om du klickar på knappen **Medarbetarresultat** visas listan med medarbetare som ingick i körningen.

Medarbetarresultaten visar information om själva processen samt eventuella kompensationsåtgärder som utfördes i processen. Avsnittet Fast kompensationen innehåller en post för varje åtgärd i processhändelsen för kompensationsplanen. Kolumnerna Aktuell riktlinje och Rekommendation visar mer information för den markerade åtgärden i avsnittet Fast kompensation. Om åtgärden Aktivera rekommendationer är markerad kommer fälten för Rekommendation att vara redigeringsbara. Då kan du justera beloppen för medarbetaren manuellt. Anmärkning: Om du har markerat Använd föregående resultat för åtgärden vid processhändelsen måste du manuellt uppdatera beloppen för de beroende åtgärderna.

När kompensationsbeloppen har granskats för en medarbetare och de rekommenderade värdena har justerats kan du ändra **Status** på raden **Medarbetarhändelse** för att indikera om händelsen har statusen Godkänd eller Ignorera. Du kan även ta bort ändringar gjorda på medarbetarens rekommendation genom att klicka på knappen **Beräkna om**. Då markeras den aktuella medarbetarhändelsen med statusen Ignorera och en ny medarbetarhändelse skapas med värden som beräknats om.

## Hämta godkända kompensationsändringar
<a id="loading-approved-compensation-changes" class="xliff"></a>
När en eller flera medarbetarhändelser har fått sin status uppdaterad till Godkänd, kan de läsas till medarbetarnas fasta kompensationsposter. Detta gör du genom att markera varje Medarbetarhändelse en i taget och klicka på knappen Läs in medarbetarkompensation på resultatsidan Medarbetare eller genom att klicka på **Läs in kompensation** på resultatsidan Processresulta för att läs in alla godkända medarbetarhändelser samtidigt.

Om du klickar på **OK** i dialogrutan **Läs in kompensation** läggs noll kompensationsåtgärdsrader till på sidan **Fast medarbetarkompensation**.
