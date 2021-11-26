---
title: Översikt över produktionsprocess
description: Det här ämnet innehåller en översikt över produktionsprocesserna. Den beskriver de olika stegen i produktionsorder, batchorder och kanbans, från orderns skapande till stängningen av den ekonomiska perioden.
author: johanhoffmann
ms.date: 09/13/2019
ms.topic: article
ms.search.form: JmgShopSupervisorWorkspace, Kanban, ProdTable, ProdTableOverview, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, OpResLifecycleManagementWorkspace, ProdParmCostEstimation, ProdParmRelease, ProdSchedule, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19832"
- intro-internal
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a07733f7e1e830fa1c1c4c8e0cfdc5b41d10750
ms.sourcegitcommit: efccf0838c74cf65382bb6cd852f9bc30ca69230
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2021
ms.locfileid: "7727345"
---
# <a name="production-process-overview"></a>Översikt över produktionsprocess

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller en översikt över produktionsprocesserna. Den beskriver de olika stegen i produktionsorder, batchorder och kanbans, från orderns skapande till stängningen av den ekonomiska perioden.

Produktionen av produkter, en process som ibland också kallas produktionslivscykeln, följer specifika steg som behövs för att slutföra tillverkningen av en artikel. Livscykeln börjar med genereringen av en produktionsorder, batchorder, eller kanban. Den avslutas med en slutförd, tillverkad artikel som antingen är klar för kunden eller för en annan fas i produktionen. Varje steg i livscykeln kräver olika typer av information för att processen ska kunna slutföras. När varje steg har slutförts visar produktionsordern, batchordern eller kanban en ändring i produktionsstatus. Andra typer av produkter kräver olika tillverkningsprocesser.

Modulen **Produktionskontroll** är kopplad till andra moduler, som t.ex. **Produktinformationshantering**, **Lagerhantering**, **Redovisning**, **Lagerstyrning**, **Projektredovisning**, och **Organisationsadministration**. Denna integration stödjer informationsflödet som krävs för att en artikel ska kunna färdigställas.

Produktionsprocessen påverkas vanligtvis av kostnadsredovisning och lagervärderingmetoderna som väljs för en viss produktionsprocessen. Supply Chain Management stöder både faktisk kostnad (först-in-först-ut \[FIFO\]; sist in, först ut \[LIFO\]; rörligt genomsnitt, periodiskt och viktat medelvärde) och standardkostnadsmetoder. Lean manufacturing implementeras baserat på kostnadskalkylering med automatisk lageravräkningprincip.

Valet av de kostnadsmätningsmetoder anger även kraven för att rapportera om material- och resursförbrukning under produktionsprocessen. Normalt kräver faktiska kostnadsredovisningsmetoder exakt rapportering på jobbnivå, medan periodiska kostnadsredovisningmetoder tillåter mindre finmaskig rapportering av material- och resursförbrukning.

## <a name="mixed-mode-manufacturing"></a>Tillverkning med blandat läge

Olika produkter och produktionstopologier kräver tillämpning av olika ordertyper. Supply Chain Management kan använda olika ordertyper i ett blandat läge. Med andra ord kan alla ordertyper ske under slutpunktsprocessen för produktionen av en färdig produkt.

- **Produktionsorder** – Detta är den klassiska ordertypen som producerar en specifik produkt eller produktvariant i en given kvantitet på ett visst datum. Produktionsorder baseras på strukturlistor och flöden.
- **Batchorder** – Denna ordertyp används för processbranscher och diskreta processer där tillverkningskonverteringen baseras på en formel, eller där samprodukter och biprodukter kan vara slutprodukter, antingen utöver eller i stället för huvudprodukten. Batchordeer använder strukturlistor och flöden av typen **Formel**.
- **Kanban** – Kanban används för lean manufacturingprocesser som baseras på produktionsflöden, kanban-regel och strukturlistor.
- **Projekt** – Ett tillverkningsprojekt kombinerar produkter och tjänster med en viss tidsplan och budget. Tillverkningsdelen av ett projekt kan levereras via någon av de andra ordertyperna.

## <a name="manufacturing-principles"></a>Tillverkningsprinciper

Om du vill välja den tillverkningsprincip som stämmer bäst för en viss produkt och en relaterad marknad, måste du ta hänsyn till kraven för produktion och logistik och också till kundens förväntningar om ledtiderna för leveranser.

- **Gör till lager** – Detta är den klassiska tillverkningsprincipen där produkter produceras för lager, baserat på prognos eller minsta lagerpåfyllning (det senare beräknas normalt baserat på prognos eller historisk förbrukning).
- **Tillverka mot beställning** – Standardprodukter tillverkas mot beställning eller avslutar beställning. Även om förproduktion kan göras genom att använda Gör till lager-principen, utlöses kostsamma steg i värdekedjan, eller steg som skapar varianter av en försäljningsorder eller en överföringsorder.
- **Konfigurera till order** – På samma sätt som för Tillverka mot beställning-principen, görs de sista operationerna i värdekedjan mot beställning. Den verkliga produktvarianten som tillverkas är inte fördefinierad men skapas vid tidpunkten för orderregistreringen, baserat på försäljningsproduktens konfigurationsmodell. Konfigurera till order-principen kräver en viss nivå av processammanslagning för en viss produktserie.
- **Tillverka vid order** – Tillverka vid order-processer, behandlas normalt av ett projekt och som vanligtvis ska startas med teknikfasen. Under teknikfasen, uppfyller de faktiska produkterna som krävs, den order som utformats och beskrivs. Produktionsorder, batchorder eller kanban kan sedan skapas för att producera produkterna.

## <a name="overview-of-the-production-life-cycle"></a>Översikt över produktionslivscykeln

Följande steg i tillverkningslivscykeln kan genereras för alla ordertyper av tillverkning som görs i blandat läge. Alla av dem representeras dock inte av en uttrycklig orderstatus.

1. **Skapad** – Du kan skapa en produktionsorder, batch order eller en kanban manuellt, eller så kan du konfigurera systemet för att generera dem baserat på olika efterfrågansignaler. Huvudplanering skapar produktionsorder, batchorder eller kanban, genom att bekräfta planerade order. Andra efterfrågansignaler är försäljningsorder eller peggad leveranssignaler från andra produktionsorder eller kanban. För kanbana med fasta kvantiteter skapas efterfrågansignaler när kanban registreras som tomma.
1. **Uppskattad** – Du kan göra uppskattningar för material- och resursförbrukning. Uppskattningen genererar lagertransaktioner för råmaterial som har statusvärdet **Har beställts**. Inleveranser för huvudprodukter, samprodukter och biprodukter genereras när produktionsorder eller batchorder beräknas. Om strukturlistan innehåller rader av typen **Peggad leverans** genereras inköpsorder för material eller legotillverkningsoperationen och knyts till en produktionsorder eller batchorder. Artiklar eller order reserveras enligt produktionsorderns reservationstrategin och priset på de färdiga varorna beräknas baserat på parameterinställningarna.
1. **Tidsplan** – Du kan schemalägga produktion baserat på operationer, enskilda jobb eller båda.

    - **Grovplanering** – Denna planeringsmetod ger en grov, långsiktig plan. Genom att använda den här metoden kan du tilldela start- och slutdatum till produktionsorder. Om produktionsorder kopplas till flödesoperationer kan du tilldela dem till grupper för kostnadsställen.
    - **Finplanering** – Denna planeringsmetod ger en detaljerad plan. Varje operation delas upp i enskilda jobb med specifika datum, tider och tilldelade verksamhetsresurser. Om begränsad kapacitet används tilldelas jobb till verksamhetsresurser baserat på tillgänglighet. Du kan visa och ändra planen i ett Gantt-diagram.
    - **Kanban-tidsplan** – Kanban-jobb planeras på det kanban-schematavla eller planeras automatiskt baserat på den automatiska planläggningskonfigurationen av kanban-reglerna.

1. **Frisläppt** – Du kan frisläppa produktionsordern eller batchordern, när tidsplanen är avslutad, och materialet är tillgängligt att plockas eller förberedas. Kontrollera materialtillgänglighet hjälper produktionslagerarbetsledaren att bedöma materialtillgänglighet för produktionsordern eller batchordern. Du kan även skriva ut produktionsorderdokument som plocklistor, jobbkort, flödeskort och flödesjobb. När produktionsordern frisläpps ändras statusen för ordern för att indikera att produktionen kan börja. När lagerstyrning används, frisläpper produktionsordern eller batchordern produktionsstrukturlistaraderna till lagerstyrning. Påfyllnad av lagerstället och lagerställearbete genereras enligt inställningarna för lagerstället.
1. **Förberedd**/**Plockad** – När alla material och resurser har mellanlagrats på produktionsplatsen, uppdateras produktionsstrukturlisteraderna eller kanbanraderna till statusen **Plockad**. Peggade leveransordrar och relaterat lagerställearbete är vanligtvis på den här fasen. De Kanban-kort eller jobbkort som krävs för att rapportera produktionsförloppet, ska tilldelas och skrivas ut.
1. **Startad** – När en produktionsorder, en batchorder eller en kanban har startats, kan du rapportera material- och resursförbrukning mot ordern. Systemet kan konfigureras för att automatiskt bokföra förbrukning av material och resurser som tilldelas ordern när den startas. Denna allokering kallas för föravräkning, framavräkning eller autoförbrukning. Du kan manuellt allokera material till produktionesorder eller batchorder genom att skapa ytterligare plocklistejournaler. Du kan också manuellt allokera arbete och andra flödekostnader till ordern. Om du använder grovplanering kan du allokera dessa kostnader genom att skapa en flödeskortjournal. Om du använder finplanering kan du allokera dessa kostnader genom att skapa en jobbkortsjournal. Produktionsorder eller batchorder kan startas i batchar av den senaste begärda slutkvantiteten. Inom en produktionsorder, en batchorder eller kanban kan jobben som skapas startas och rapporteras separat genom journaler, den tillverkade utförandeterminalen (MES-terminal) eller kanban-tavlor.
1. Rapportförlopp **Slutför** jobb – Använd MES-terminal, produktionsjournaler, kanban-tavlor eller mobil skanning för att rapportera produktionsförloppet per jobb eller resurs. Kostnader för material- och resursförbrukning bokförs, och statusvärdet för de relaterade kanbans, produktionsorder och batchorder kan uppdateras till **Inlevererat** eller **Rapporterat som färdigt**. Inlagrat arbete för lagerstället kan skapas, beroende på lagerställekonfigurationen.
1. **Rapporterad som avslutad** (produktinleveransen) – När en produktionsorder eller batchorder rapporters som färdig, uppdateras kvantiteten av de slutförda varorna som har avslutats i Lager. Den här kvantiteten inkluderar kvantiteten för relevanta samprodukter och biprodukter. Om du använder PIA-redovisning skapas en redovisningsjournal för att minska PIA-kontona och öka lagret av färdiga varor. När kostnaden för en produktionsorder beräknas, bokförs den faktiska kostnaden för produktionen. Om de material- och arbetskostnader som är associerade med en produktion inte redan har tilldelats i en journal eller via föravräkning, kan de tilldelas automatiskt via bakåtavräkning. Allokeringen via bakåtavräkning gäller avdrag av lagertransaktionsprocesser. Om produktionsordern har slutförts ska du markera kryssrutan **Avsluta jobb** för att ändra återstående status till **Avslutad**. Annars lämnas fältet tomt om du vill tillåta rapporteringen för alla ytterligare kvantiteter som tillverkas.
1. **Kvalitetsbedömning** – En produktinleverans kan utlösa generering av kvalitetsorder, beroende på konfigurationen för testprocesser de kvalitetsgrupper och reglerna som är upprättade för specifika produkter. Eftersom en kvalitetsorder kan uppdatera lagerstatus eller batchattributen av de testade produkterna, är kvalitetsbedömning en obligatorisk process i många branscher.
1. **Inlagra** och **Leverera till order** Efter produktinleverans och kvalitetsbedömning, styr valfritt inlagringsarbete de inlevererade produkterna till nästa förbrukningspukt,, till ett lagerställe för färdiga varor eller till en försändelsezon, om det finns Leverera till order-krav.
1. **Avslutad** – Innan produktionen avslutas beräknas faktiska kostnader för den kvantitet som producerats. Alla uppskattade kostnader för material, arbete och omkostnader återställs och ersätts med faktiska kostnader. Om du markerar kryssrutan **Avsluta jobb** när du kör kostnadsberäkningen, ändras produktionsorderns status till **Avslutad**. Denna status förhindrar att ytterligare kostnader bokförs på en slutförd produktionsorder.
1. **Stängning av period** – En del kostnadsredovisningprinciper som periodiskt genomsnitt, kostnadsredovisning med bakåtavräkning, FIFO eller LIFO, kräver periodiska aktiviteter för att stänga lagret eller den finansiella perioden. Vanligtvis försöker systemet att rapportera all material- och resursförbrukning och även korrigeringar av lagret och kassering innan perioderna stängs. Detta görs normalt genom att använda lagerrörelsejournaler, eller justering av journaler. Målet är att bedöma ekonomisk prestanda för driftenheter per period. I vissa fall används när avancerade produktionsorder används som sträcker sig över perioder för ekonomisk rapportering, används produktionsjournaler för att rapportera produktionsförlopp och resursförbrukning i slutet av perioden.

## <a name="additional-resources"></a>Ytterligare resurser

- [Produktionsåterrapportering](production-feedback.md)
- [Översikt över produktkonfigurationsmodeller](../pim/product-configuration-models.md)
- [Lean manufacturing – översikt](lean-manufacturing-overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
