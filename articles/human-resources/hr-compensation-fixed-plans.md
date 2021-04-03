---
title: Skapa planer för fast kompensation
description: Fast kompensation refererar till en medarbetares vanliga bruttolön eller löner. Det här avsnittet beskriver komponenterna som måste ställas in innan du kan skapa en fast kompensationsplan och anmäla medarbetare.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: cc6a639bd593b9a41217a054023a9de82f373c1f
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465784"
---
# <a name="create-a-fixed-compensation-plans"></a>Skapa planer för fast kompensation

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Fast kompensation refererar till en medarbetares vanliga bruttolön eller löner. Det här avsnittet beskriver komponenterna som måste ställas in innan du kan skapa en fast kompensationsplan och anmäla medarbetare.

Belopp för fast kompensation kan beräknas för dina medarbetare, baserat på faktorer som till exempel prestanda, region och budget. Dynamics 365 Human Resources stöder kompensationstyperna steg, grad och band.

## <a name="fixed-compensation-components"></a>Komponenter i fast kompensation
### <a name="compensation-levels"></a>Kompensationsnivåer

Du kan använda **kompensationsnivåer** för att ange kompensation för olika jobb, detta för att garantera att de medarbetare som innehar dessa jobb betalas rättvist. På sidan **Kompensationsnivåer** kan du skapa kompensationsnivåer som krävs för varje steg-, grad- och bandplan. Använd **uppknappen** och **nedknappen** för att placera nivåerna i rätt ordning enligt deras typ. Genom att ange ersättningsnivåer för ett jobb, kan du att garantera att alla medarbetare som har en befattning för det jobbet betalas på samma nivå.

### <a name="reference-points"></a>Referenspunkter

**Referenspunkter** är kolumnerna som definierar kompensationsintervallen för varje nivå. Kompensationsnivån är raden i tabellen. Typiska referenspunkter för en plan av typen grad är ett minimum, en mittpunkt och ett maximum. Du skapar referenspunkter på sidan **Inställningar för referenspunkter**.

### <a name="compensation-grids"></a>Kompensationsrutnät

När du har ställt in nivåerna referenspunkterna, kan de kombineras för att skapa ett **kompensationsrutnät**. Definiera information om rutnätet på sidan **Kompensationsrutnät**. Exempelvis anger du vad rutnätet ska användas till, vilken typ av plan den används med och vilka referenspunkter eller kolumner som krävs. När du har angett informationen klickar du på **Kompensationsstruktur** för att lägga till nivåerna och beloppet i tabellen. 

**Tips:** Använd funktionen **Massändringar** i kompensationsstrukturen för att ange ursprungliga belopp och öka sedan dessa med procentsatser eller belopp på alla nivåer eller referenspunkter.

### <a name="pay-frequencies"></a>Lönefrekvenser

**Lönefrekvenser** används för att definiera hur en medarbetares lön anges (till exempel 500 per timme eller 350 000 per år), och konverteringen mellan timlön, veckolön, månadslön (tolv månader) och årslöner. Ett företag som exempelvis har en 38-timmarsvecka för de timanställda anger en betalningsfrekvens med timtakten 1, veckotimmarna 38 och månadslön på 164,6666666667 och en årslön på 1 976. Dessa konverteringar används för att beräkna olika lönebetalningar som visas på en medarbetares post för fast kompensation.

## <a name="fixed-compensation-plans"></a>Planer för fast kompensation
Du kan utforma planen för fast kompensations för att kombinera alla komponenter som du har konfigurerat. Skapa en plan för fast kompensation genom att öppna sidan **Planer för fasta kompensationsplaner**. Här kan du ge din plan ett namn och en beskrivning, välja typ av plan (steg, grad eller band), välja betalningsfrekvensen för medarbetarens lön (belopp per timme, belopp per år osv.) och ange några alternativ som styr hur kompensation bearbetas. 

Inställningen **Tolerans utanför intervallet** gör att du kan ange hur sträng du ska vara när du ser till att kompensationsbeloppen ligger mellan maximi- och minimibeloppen. **Hård** tolerans kräver en kompensationen ska vara inom intervallet som har definierats för en viss nivå. **Mjuk** tolerans varnar dig om kompensationsbeloppet hamnar utanför intervallet, men tillåter dig att fortsätta. Om du ställer in toleransen på **Ingen**, kan du ange vilket kompensationsbelopp som helst, utan att få några varningar eller felmeddelanden. 

Inställningen **Anställningsregel** gör att du kan ange om alla medarbetare ska få samma ökning, oavsett det datum då de anställdes (**Anställningsregel** = **Ingen**), eller om medarbetare ska få en procentandel av ökningen, baserat på hur länge han eller hon har varit anställd (**Anställningsregel** = **Procent**). 

En **matris för utnyttjandeintervall** är användbar om du vill antingen minska den tid som krävs för att medarbetare att nå mittpunkten i intervallet eller öka tiden för medarbetare att nå till maximireferenspunkten i intervallet. Du kanske till exempel vill ge medarbetare som ligger i den nedre kvartilen av sitt intervall 110 procent, medan medarbetare i den övre kvartilen bara ska få 80 procent för att hindra att de når maximum för snabbt. 

När du har definierat grunderna av planen för fast kompensation, kan du ställa in en kompensationsstruktur för planen. Klicka på **Ställ in kompensation**. Skjutreglaget för en dialogruta som ger dig tre alternativ öppnas:

-   Skapa ett nytt kompensationsrutnät genom att välja en referenspunktsinställning och att ge rutnätet ett namn.
-   Skapa ett nytt kompensationsrutnät genom att kopiera ett befintligt rutnät som du kan använda som utgångspunkt.
-   Använd ett befintligt kompensationsrutnät som redan har definierats. Alla kompensationsplaner som använder samma rutnät får uppdateringar om rutnätet ändras.

När du har valt ett alternativ öppnas sidan **Kompensationsstruktur** och du kan göra ändringar i det nya kompensationsrutnätet eller det befintliga kompensationsrutnätet.

## <a name="fixed-compensation-enrollment"></a>Anmälan till fast kompensation
### <a name="determine-who-is-eligible-for-the-plan"></a>Bestäm vem som är berättigad till planen

Första steget i att ta med medarbetare till en plan för fast kompensation är att bestämma vem som är berättigad till kompensation som definieras i planen. Innan du har bestämt vem som får, kan du inte koppla planen till någon medarbetare. Öppna sidan **Kvalifikationsregler** för att ställa in tillgängligheten. Här skapar du en ny kvalifikationsregel för din kompensationsplan och definierar de kriterier som en medarbetare måste uppfylla för att kvalificera sig för en plan. Du kan begränsa berättigandet baserat på avdelning, fackförening, kompensationsregion (plats), jobb, jobbfunktion eller kompensationsnivå. Medarbetare kan bara tas med i en kompensationsplan om de uppfyller alla kriterier som angetts i berättiganderegeln. 

**Obs!** Berättiganderegler används till planer för både fast och variabel kompensation. 

Berättiganderegeln tar hänsyn till värdet på specifika fält i jobbet, befattningen och medarbetarposter som fastställer om en medarbetare är berättigad till en kompensationsplan.

-   På sidan **Jobb** tar berättiganderegeln hänsyn till följande fält:
    -   Fältet **Jobb**.
    -   På fliken **Jobbklassificering**, fälten **Funktion** och **Jobbtyp**.
    -   På fliken **Kompensation**, fältet **Nivå**.
-   På sidan **Befattningar**, använder berättiganderegeln värdena i fälten **Avdelning** och **Kompensationsregion**.

Berättiganderegeln tar också hänsyn till fackföreningar som kopplas till medarbetaren (på sidan **Medarbetare**, på fliken **Arbetare**, klicka på **Personlig information** &gt; **Fackföreningar**).

### <a name="define-fixed-compensation-actions"></a>Definiera åtgärder för fast kompensation

**Åtgärder för fast kompensation** används när du ställer in eller använder ändringar i en medarbetares fasta kompensation. Åtgärder för fast kompensation gör att du kan ange beskrivande namn på åtgärdstyperna som en chef över kompensationer och förmåner kan utföra. Olika åtgärdertyper har särskild logik bakom, så att de kan användas vid specifika tidpunkter. 

När till exempel fast kompensation har ställts in för en medarbetare, kan enbart åtgärder, som har typen **Anställ/återanställ** användas. I det här fallet kan du vilja skapa tre olika åtgärder för typen **Anställ/återanställ** och ge dem namnen **Anställ**, **Återanställ** och **Förflytta**. Då har du en mer beskrivande förklaring till varför den fasta kompensationen gavs till en medarbetare eller ändrades.

### <a name="enroll-the-employee"></a>Ta med anställd

Nu kan du koppla en medarbetare till en plan för fast kompensation. Öppna sidan **Medarbetare** och välj den medarbetare som du vill lägga till i kompensationsplanen. Klicka på **Kompensation** &gt; **Fast plan** i åtgärdsfönstret. Du kan nu skapa en ny åtgärd för fast kompensation för denna medarbetare. 

**Obs!** Kompensationsplanfältet visar bara planerna som en medarbetare är berättigad till enligt berättigandereglerna för varje plan. Om ingen berättiganderegel har ställts in för en plan, har ingen anställd rätt till planen. 

Systemet kontrollerar att kompensationsbeloppet som anges för en kompensationsplan av typen grad eller band ligger mellan minimi- och maximireferenspunkterna för en viss kompensationsnivå på medarbetarens jobb. Om kompensationsbeloppet ligger utanför det tillåtna intervallet, visas ett felmeddelande eller varningsmeddela, beroende på den toleransnivå som anges i planen för fast kompensation.



[!INCLUDE[footer-include](../includes/footer-banner.md)]