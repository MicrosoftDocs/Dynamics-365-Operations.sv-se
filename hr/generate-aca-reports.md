---
title: Generera Affordable Care Act-rapporter
description: "Funktionen är tillgänglig för att underlätta för arbetsgivare som behöver följa upp information rapporterad i formulären 1095 B och 1095-C för att stödja delen Arbetsgivarfullmakt inom Affordable Care Act. Observera att den här funktionen endast är aktiverad för juridiska personer i USA."
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
ms.search.scope: AX 7.0.0, Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 61fa5dd3580c769457ea2cfdc669f68bd3b30980
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---
# Generera Affordable Care Act-rapporter
<a id="generate-affordable-care-act-reports" class="xliff"></a>
Funktionen är tillgänglig för att underlätta för arbetsgivare som behöver följa upp information rapporterad i formulären 1095 B och 1095-C för att stödja delen **Arbetsgivarfullmakt** inom Affordable Care Act. Observera att den här funktionen endast är aktiverad för juridiska personer i USA.

## Komma igång
<a id="getting-started" class="xliff"></a>
När du börjar spåra information att rapportera i formulär 1095 B och 1095 C, måste du skapa minst en Affordable Care-försäkringsskyddsgrupp. Dessa Affordable Care-försäkringsskyddsgrupper används för att visa täckningserbjudandet för en anställd, den anställdes andel av den lägsta månadspremien (om kostnaden överstiger den federala fattigdomsgränsen) samt den Safe Harbor som används av arbetsgivaren, i tillämpliga fall. Med Affordable Care Act-grupper kan du hantera information för dessa fält utan att behöva vidröra varje enskild medarbetarpost där villkoren är desamma. Dessutom kan Affordable Care-försäkringsskyddsgrupper enkelt tilldelas till en eller flera anställda med hjälp av funktionen för masstilldelning på sidan.

## Underhålla flera versioner av en försäkringsskyddsgrupp
<a id="maintaining-multiple-versions-of-a-coverage-group" class="xliff"></a>
Du kan underhålla flera versioner av en försäkringsskyddsgrupp, vilket för att du kan genomföra ändringar som håller gruppens information aktuell utan att behöva skapa en ny grupp och tilldela anställda till den när en ändring sker i organisationen, eller i de förmåner som erbjuds. 

När du har skapat de Affordable Care-försäkringsskyddsgrupper som du behöver, kan du välja att masstilldela grupperna till medarbetarna med hjälp av funktionen **Masstilldelning** på sidan, eller gå till varje medarbetare och ange om ACA-information ska spåras och rapporteras för denna medarbetare, samt tilldela medarbetaren till Affordable Care-försäkringsskyddsgrupp.

Om omfattningsinformation för Affordable Care inte behöver spåras och rapporteras för en medarbetare - till exempel om dessa är deltidsmedarbetare - kan fältet **Rapportomfattning** anges som Nej. Även om varje enskild anställd för vilken ACA-information behöver spåras måste tilldelas till en Affordable Care-försäkringsskyddsgrupp, kan du ändra alternativet för **Erbjudande om täckning**, **Medarbetarens kostnadsandel** och **Safe Harbor** för varje månad - eller månader - som behöver andra värden än de som angetts i Affordable Care-försäkringsskyddsgruppen.

Om du vill ange undantag för något av Affordable Care-försäkringsskyddsgruppens värden klickar du på länken Affordable Care-täckning som finns på informationssidan för arbetstagare, som finns under avsnittet Ytterligare information på fliken Anställning.

## Rapportering av hälsovårdstäckning
<a id="reporting-health-care-coverage" class="xliff"></a>
Förutom att spåra vad händer om någon sjukförsäkringstäckning erbjudits till en heltidsanställd, måste ytterligare information redovisas på 1095-C om arbetsgivaren erbjuder arbetsgivarsponsrad, självförsäkrad hälsotäckning som medarbetaren är anmäld för (oavsett om deras anställningsstatus är heltid eller deltid). Varje medarbetare (inklusive beroende) som omfattas av arbetsgivarsponsrade förmånsplaner måste inkluderas i rapporten för de månader som de omfattades. 

Du kan ange huruvida varje förmånsplan måste rapporteras genom att välja kryssrutan **ACA-pliktig**.

Om medarbetare har valt att låta någon beroende saka omfattas av en förmån som anger du dessutom de datum då Beroenden omfattades för samtliga anställda på sidan Underhåll förmåner. Klicka på knappen Redigera i åtgärdsfönstret på snabbfliken Beroenden om du vill ange att beroenden täcks av förmånen.

På sidan **Datumhanterare för beroendetäckning** anger du de datum då beroenden omfattades av förmånen. Om du anger datum på den här sidan kommer kryssrutan **Täckning** automatiskt att markeras på sidan **Bibehåll förmåner**.

## Generera 1095B- och 1095C-formulär
<a id="generate-1095b-and-1095c-forms" class="xliff"></a>
Du kan också generera 109-B- och 1095-C-formulär i själva produkten och distribuera dessa till var och en av dina medarbetare. Elektroniskt genererade 1095-C- och motsvarande 1094-C-överföringsfiler som kan användas för att skicka till IRS kan också genereras från systemet.  

När formuläret 1095-C genereras, ange då i lämplig kalender eller lämpligt beskattningsår om du vill skriva ut formuläret med två eller tre sidor. Det tresidiga formuläret behövs bara om arbetsgivaren tillhandahöll självförsäkrad täckning och en medarbetare har fler än sex omfattade beroenden, inklusive sig själva. När du genererar tvåsidorsformuläret kommer systemet automatiskt att identifiera om en medarbetare har mer än 6 täckta beroenden, och inkluderar inte denna anställde vid generering av formuläret. Systemet kommer dessutom endast att omfatta de medarbetare som har fler än sex dolda beroenden när det genererar det tresidiga formuläret.

## Visa information
<a id="viewing-information" class="xliff"></a>
Du kan använda sidan **Affordable Care-täckning för arbetstagare** om du vill se vilka medarbetare som har tilldelats respektive försäkringsskyddsgrupp, vilka medarbetare som inte behöver ingå i en rapport, samt vilka medarbetare som inte har tilldelats.

Om något av standardvärdena från Affordable Act-försäkringsskyddsgruppen har åsidosatts, visas en asterisk bredvid värdet som har ändrats. Om värdena för alla 12 månader är desamma och inte har åsidosatts, anges värdet i kolumnen **Samtliga 12 månader**.

Du kan också använda fönstret för förfrågan om du vill se vilka medarbetare som har flaggats som inte icke-ACA-rapporteringsbara, vilket innebär att du inte behöver spåra huruvida täckning erbjudits dem och heller inte behöver utfärda en 1095-C till dem i slutet av året. Genom att markera **Ej ACA-pliktig** i fältet **Filtrera efter** kan du skapa en lista över alla medarbetare som har flaggats att inte erhålla en 1095-C.

Förutom att visa en lista med medarbetare som inte är ACA-pliktiga kan du också visa alla medarbetare som inte har tilldelats (fältet **ACA-rapporttäckning** är tomt) eller som har tilldelats till en Affordable Care-försäkringsskyddsgrupp som har upphört att gälla för det år som har valts i fältet **År**.

Du kan exportera listor över medarbetare som har skapats med något av filtreringsalternativen till Excel.

Om du vill rapportera omfattade personer eftersom du som arbetsgivare tillhandahåller egenförsäkrade täckning, kan du även visa alla beroende personer som täcks av förmånsplaner markerade som **ACA-pliktiga** genom att välja åtgärden Visa beroendetäckning via fliken i åtgärdsfönstret.

**Obs!** Bara förmåner vars plan har markerats som **ACA-pliktig** visas i frågefönstret.

