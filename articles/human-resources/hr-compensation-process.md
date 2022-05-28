---
title: Bearbeta kompensation
description: Kompensationsbearbetning gör att du kan beräkna nya baskompensationsbelopp för personalen utifrån justeringar av eget kapital, meritökningsmål och prestanda.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e4aa910d92c2905d54d96f656e1d3d1c36388636
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693876"
---
# <a name="process-compensation"></a>Bearbeta kompensation


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Kompensationsbearbetning gör att du kan beräkna nya baskompensationsbelopp för personalen utifrån justeringar av eget kapital, meritökningsmål och prestanda. Det här ämnet beskriver det grundläggande flödet för kompensationsbearbetning för fasta kompensationsplaner utan att räkna med en medarbetares prestanda.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Planera det nya kompensationsbeloppet och budgetar
Om du vill ge dina anställda en meritökning, måste du konfigurera en fasta ökningsbudgetför var och en av dina avdelningar: **Kompensationshantering** > **Länkar** > **Meritökningsmål**. (Du kan också öppna sidan via Avdelning: **Organisation** > **Avdelningar**.) Här kan du specificera om medarbetare i en viss fackförening eller på en viss plats skulle ha en annan ökningsprocent. Fälten **Budget** och **Valuta** är informativa och kan användas för att anteckna ett valutabelopp för budgeten.

## <a name="set-up-the-compensation-process"></a>Ställa in kompensationsprocessen
På sidan **Kompensationsprocesser** kan du ange parametrar för kompensationsbearbetningen. Detta inkluderar tidsperioden för utvärdering för att bestämma kompensationsbelopp och det datum då nya kompensationsbelopp ska träda i kraft.

Du kan även inkludera en **fast lön proportionellt från anställningsdatumet** om någon av er fasta kompensationsplaner använder en anställningsregel i procent. För dessa planer kan alla som anställdes efter **Cykelns startdatum** och före **Fast lön proportionellt från anställningsdatumet** få 100 % av sin beräknade meritökning eller allmänna ökning. Alla som anställdes efter **Fast lön proportionellt från anställningsdatumet** och före **Cykelns slutdatum** får en del av sin beräknade ökning baserat på hur många dagar av det totala antalet cykeldagar de har varit anställda. Till exempel, om vår cykel löper från den 1 januari till den 31 december och vi har en Fast lön proportionellt från anställningsdatumet den 1 April, får en medarbetare som anställts i mars den fullständiga beräknade ökningen medan en medarbetare som anställdes den den 1 juli får ungefär hälften av den beräknade ökningen.

Datumet för processhändelsen **Tidpunkt** används endast för att bearbeta vissa variabla kompensationsplaner och beskrivs inte här. **Tidsgräns för granskning** är den tidsgräns då alla rekommendationer måste ha inkommit, så att nya kompensationsbelopp kan läsas in i medarbetarposten. Datumet för granskning är endast för information.

När parametrarna för processhändelsen har sparats kan du klicka på knappen **Inställningar** för att bekräfta vilka planer som ska ingå i den här processkörningen och vilka åtgärder för fast kompensation som ska vidtas för varje plan.

Klicka på knappen **Lägg till** i fliken **Planer** om du vill lägga till en kompensationsplan i processhändelsen. Kolumnerna **Använd annan påverkan**, **Påverkansfaktor** och **Påverkansbeskrivning** används bara för variabla kompensationsplaner och omfattas inte av det här avsnittet.

Spara posten och klicka sedan på knappen **Lägg till** i fliken **Åtgärder** för att lägga till fasta kompensationsåtgärder för den markerade planen. Använd alternativet **Aktivera rekommendationer** om du vill ange ett annat belopp än den beräknade riktlinjeökningen för åtgärden. Om du vill beräkna en åtgärd som baseras på resultatet av den föregående åtgärden för att koppla flera kompensationsåtgärder markerar du alternativet **Använd tidigare resultat**. Fasta kompensationsåtgärder är typer av kompensationslogik som du kan ge beskrivande namn till. För **Klass**- och **Band**-planer kan du bara lägga till fasta kompensationsåtgärder som är av följande typer:

| Åtgärdstypen Fast kompensation | Funktionalitet                  |
|-------------------------------|-------------------------------------------------------------------------|
| Eget kapital                        | Eget kapital-åtgärder jämför medarbetarens lönesats per cykelns slutdatum med lägsta referenspunkten för de nivåer som anges för medarbetarens jobb. Om medarbetarens lönesats är lägre än den minsta referenspunkten beräknas ökningen som krävs för att få medarbetaren till den lägsta punkten i listan.                                                                                |
| Merit                         | Meritåtgärder beräknar en ökning baserad på medarbetarens lönesats per cykelns slutdatum och ökningen i procent som finns i den fasta ökningsbudgeten för medarbetarens avdelning, fackförening och plats.                                                                                                                                                                                         |
| Allmänt                       | Allmänna åtgärder beräknar en ökning på grundval av antingen en procentsats eller ger de anställda ett fast belopp. Detta avgörs utifrån inställningarna för **Fast kompensation** på fliken **Allmänt**.                                                                                                                                                                                                                        |
| Befordran                     | Med erbjudandeåtgärder får du ett namngivet ställe där du kan få belöningsökningar. Markera alternativet **Aktivera rekommendation** om du vill ange en rekommendation för medarbetare som ska ta emot erbjudanden.  Medarbetare utan en rekommenderad ökning kommer inte att ha åtgärden **erbjudande** tillagd i sina poster för fast kompensation.                                                                       |
| Annan nivåändring            | I exemplet ovan är **Omplacering** namnet på vår **fasta kompensationsåtgärd** med en typ av **annan nivåändring**. Då skapas en 0-riktlinjeökning (nollökning) så att du kan ange ett rekommendationsbelopp om du vill justera medarbetarens lönesats. (Markera alternativet **Aktivera rekommendation**.) Medarbetare utan en rekommendation har inte den här åtgärden tillagd i sina poster för fast kompensation. |

Du kan bara lägga till **Fasta kompensationsåtgärder** ill typen Steg för steg-plan.

| Åtgärdstypen Fast kompensation | Funktionalitet                |
|--------------------------------|------------------------------|
| Steg                           | Ange om stegåtgärden ska flytta medarbetaren framåt 0 steg, 1 steg eller två steg på fliken **Allmänt**.                                                                                  |
|                                | **0 steg** – Medarbetaren får lönesatsen för det aktuella steg som han/hon befinner sig på.                                                                                                                      |
|                                | **1 steg** – Systemet kontrollerar om medarbetaren redan är på sista referenspunkten för nivån.                                                                                             |
|                                | **2 steg** – Medarbetaren flyttar fram två steg i den aktuella nivån. Medarbetaren kanske bara flyttar ett eller noll steg om de uppnår den sista referensenspunkten för nivån. |

## <a name="run-the-compensation-process"></a>Kör kompensationsprocessen
När processhändelsen har ställts in med nödvändiga datumfält, planer och åtgärder kan du klicka på **Kör process** på sidan **Processhändelse**, detta öppnar dialogrutan **Kör kompensationsprocess**. Klicka på alternativet **Visa processresultat** för att se hur kompensationsbeloppen beräknades för varje medarbetare. Om du klickar på **OK** körs kompensationsprocessen för alla medarbetare som ingår i de valda kompensationsplanerna för cykelns slutdatum.

## <a name="view-the-process-results"></a>Visa processresultaten
Om du vill visa processresultaten, öppna sidan **Processresultat**. En ny kompensationshändelse skapas varje gång processhändelsen körs. På så sätt kan du göra testkörningar, justera och köra kompensationshändelsen flera gånger för att se hur olika ändringar påverkar medarbetarkompensation.

Sidan **Processresultat** innehåller information om processkörningen, inklusive när körningen inträffade, användaren som körde processen och om eventuella fel uppstod när processen körs. Markera alternativet **Låst** för att inaktivera den knappen **Läs in kompensation** och förhindra ett någon laddar kompensationshändelser till medarbetarposterna. Om du klickar på knappen **Medarbetarresultat** visas listan med medarbetare som ingick i körningen.

Alternativet **Medarbetarresultat** visar information om själva processen samt eventuella kompensationsåtgärder som utförs i processen. Avsnittet **fast kompensation** ska innehålla en post för varje åtgärd som är inkluderad i processhändelsen för kompensationsplanen. Kolumnerna **Aktuell riktlinje** och **Rekommendation** visar mer information för den markerade åtgärden i avsnittet **Fast kompensation**. Om **Aktivera rekommendationer** är markerad kommer fälten för **Rekommendation** att vara redigeringsbara. Då kan du justera beloppen för medarbetaren manuellt. Observera att om du har markerat **Använd föregående resultat** för åtgärden vid processhändelsen måste du manuellt uppdatera beloppen för de beroende åtgärderna.

När kompensationsbeloppen har granskats för en medarbetare och de rekommenderade värdena har justerats kan du ändra **Status** på raden **Medarbetarhändelse** för att indikera om händelsen har statusen Godkänd eller Ignorera. Du kan även ta bort ändringar gjorda på medarbetarens rekommendation genom att klicka på knappen **Beräkna om**. Då markeras den aktuella medarbetarhändelsen med statusen Ignorera och en ny medarbetarhändelse skapas med värden som beräknats om.

## <a name="loading-approved-compensation-changes"></a>Hämta godkända kompensationsändringar
När en eller flera medarbetarhändelser har fått sin status uppdaterad till **Godkänd**, kan de läsas till medarbetarnas fasta kompensationsposter. Detta gör du genom att markera varje Medarbetarhändelse en i taget och klicka på knappen **Läs in medarbetarkompensation** på resultatsidan **Medarbetarresultat** eller genom att klicka på **Läs in kompensation** på sidan **Processresultat** för att läs in alla godkända medarbetarhändelser samtidigt.

Om du klickar på **OK** i dialogrutan **Läs in kompensation** läggs noll kompensationsåtgärdsrader till på sidan **Fast medarbetarkompensation**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
