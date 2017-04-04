---
title: "Översikt för Lean manufacturing"
description: "Denna artikel ger en översikt och beskrivning av lean manufacturing-funktioner i Microsoft Dynamics AX."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19371
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3c608f13c93446329702f07ef7e8bb08a29d87b9
ms.lasthandoff: 03/31/2017


---

# <a name="lean-manufacturing-overview"></a>Översikt för Lean manufacturing

Denna artikel ger en översikt och beskrivning av lean manufacturing-funktioner i Microsoft Dynamics AX.

Lean manufacturing erbjuder verktyg som du kan använda för att modellera resurssnåla åtgärder. Dessa verktyg främjar och stöder följande de koncept och affärsaktiviteter:
-   Skapa en lean manufacturing-grund genom att modellera tillverknings- och logistikprocesser som produktionsflöden.
-   Implementera ett resurssnålt hämtningssystem genom att använda kanban för att signalera efterfrågekrav.
-   Övervaka och underhåll kanban-jobb.

Lean manufacturing-arkitekturen i Microsoft Dynamics AX 7 består av produktionsflöden, aktiviteter och kanban-regler. Dessa strukturer är helt integrerade med Microsoft Dynamics AX 7-processer. Du kan använda lean manufacturing i en tillverkningsmiljö för blandat läge som kombinerar olika leverans-, produktion- och sourcing-strategier. Dessa strategier inkluderar tillverkningsorder, batchorder för processbranscher, inköpsorder och överföringsorder.
| **Viktigt! **                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Du kan använda Microsoft Dynamics AX 7 för att stödja implementeringen av lean manufacturing med kanban. En lyckad implementering av resurssnåla principer beror dock på vilka interna affärsprocesser du använder, och på själva produktionsvillkoren och produktionsmiljön. |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a> Modellera tillverknings- och logistikprocesser som produktionsflöden
Du skapar en lean manufacturing-grund genom att modellera tillverknings- och logistikprocesser som produktionsflöden. Aktiviteten består av följande uppgifter:
1.  Identifiera processerna som du vill implementera en resurssnål återanskaffningsstrategi för och modellera sedan dessa processer som produktionsflöden. Du kan sedan analysera och förenkla processen. Ett av målen med en resurssnål implementering är att reducera spill genom att förbättra flödet av material och information.
2.  Definiera ett produktionsflöde som en sekvens av aktiviteter som beskriver flödet av material. En överföringsaktivitet definierar förflyttningen av en produkt eller produkter från en plats till en annan. En processaktivitet som definierar en mervärdesåtgärd som tillämpas på en produkt.
3.  Skapa en version av produktionsflödet som definierar kraven för takttid. Dessa krav används för att beräkna cykeltiderna för varje aktivitet i produktionsflödet. Du kan skapa flera versioner av produktionsflöden och sedan använda dessa versioner för att förbättra processer.

## <a name="using-kanbans-to-signal-demand-requirements"></a> Använda kanban för att signalera efterfrågebehov
Ett hämtningssystem producerar bara varor när varorna behövs. Denna metod minskar ledtiderna för leveranser och överflödigt lager. Du kan använda kanban att planera, följa och bearbeta krav som baseras på produktionsflöden. Om du vill skapa ett kanban-ramverk skapar du kanban-regler som definierar när kanban skapas och hur behoven uppfylls. Du kan skapa två typer av kanban-regler. Tillverkningsregler skapar kanban-jobb för processer och kanban-regler för tillbakadragande skapar kanban-jobb för överföringar. Du kan ställa in betalningstyper på lagerpåfyllnadsstrategier:
-   Kanban-regler av typen **Fast kvantitet** är relaterade till ett fast antal hanteringsenheter, vilket innebär att antalet aktiva kanban är konstant. När alla produkter från en Kanban förbrukas och hantera enheter manuellt är tomma, skapas en ny kanban av samma typ.. Du kan beräkna optimal kanban-kvantiteter och produktkvantiteter som används när du skapar fast antal kanban-regler. Beräkningen tar hänsyn till kontoprognosen, faktisk efterfrågan från öppna order, ledtid för att fylla på artiklar och historisk efterfrågan.
-   Kanban-regler av typen **Schemalagda** fyller på behov som beräknas från huvudplaneringen. Huvudplaneringen genererar planerade kanban som kan kopplas till kanban.
-   Kanban-regler av typen **Händelse** fyller på behov som kommer från försäljningsorderrader, rader i produktionsstrukturlista, kanban-rader och minimilagerinställningar. När händelse-kanban skapas kopplas de till källbehoven.

När en kanban skapas genereras ett eller flera kanban-jobb baserat på kanban-flödesaktiviteterna som definierats i kanban-reglerna.

## <a name="monitoring-and-maintaining-kanban-jobs"></a> Övervaka och underhålla kanban-jobb
Lean manufacturing ger insyn i den aktuella statusen för tillverknings- och logistikaktiviteter som regleras av kanban-reglerna. Som ett resultat kan du planera och prioritera följande uppgifter:

-   Få en översikt över schemat med aktuella kanban-jobb.
-   Planera och tidsplanera om kanban-jobb.
-   Följ och registrera statusen för kanban-jobb.

I listan nedan beskrivs de specialiserade kanban-tavlorna:
-   Tidsplanering av Kanban-jobb – Ger en översikt över kanban-jobb. Tavlan visar kanban-jobb och deras status för en eller flera arbetsgrupper. Jobben anges enligt planeringsperioderna (dagar eller veckor) som definierats i produktionsflödesmodellen. Tavlan visar också kapacitetsförbrukningen för varje planeringsperiod så att du kan övervaka den schemalagda beläggningen. Du kan ändra status för kanban-jobb, tidsomplanera kanban-jobb till andra planläggningsperioder och utföra andra uppgifter.
-   Kanban-tavla för överföringsjobb – Den här tavlan ger en översikt över aktuella överföringsjobb. Du kan uppdatera och registrera plocklistor, starta och slutföra överföringsjobb och utföra andra uppgifter.
-   Kanban-tavla för processjobb – Den här tavlan har utformats för att stödja det normala produktionsflödet och för att ge en översikt över den aktuella situationen i en eller flera arbetsgrupper. Från den här tavlan kan kanban prioriteras, väljas eller tillverkas. Tavlan har också utformats för att stödja skanning av streckkoder för rapporteringen av kanban.

## <a name="kanban-jobs-and-integration-with-microsoft-dynamics-ax-processes"></a> Kanban-jobb och integration med Microsoft Dynamics AX-processer
Kanban-jobb är helt integrerade med aktuella processer för lagertransaktioner i Microsoft Dynamics AX.
-   Du kan utföra plockningsaktiviteter för att fylla på material som används för att uppfylla behoven i kanban-jobb.
-   Du kan skriva ut kanban-kort, cirkulerande kanban-kort och plocklistor för att stödja användningen av kanban. Dessa dokument används för att representera, spåra och registrera kanban-jobb på lagerstället och på produktionsgolvet.
-   Du kan registrera plockning och överföringsaktiviteter i lagret genom att skanna streckkoder.

Dessutom stöder lean manufacturing inköps- och faktureringsprocesser för tjänster som är relaterade till aktiviteter som utförs av underleverantörer.
-   Du kan tilldela inköpsavtalsrader och tjänster för aktiviteter som utförs av underleverantörer.
-   Du kan skapa periodiska inköpsorder och mottagningsavier för att stödja inköp och fakturering av tjänsterna.



