---
title: Hantering av skift och kassalåda
description: Det här avsnittet beskriver hur du ställer in och använder shift i butikskassor.
author: jblucher
manager: AnnBe
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e600e1d2bb4bc1a49d55fb58b3e74fa7e13fc2af
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017907"
---
# <a name="shift-and-cash-drawer-management"></a>Hantering av skift och kassalåda

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver hur du ställer in och använder shift i butikskassor.

I Dynamics 365 Retail beskriver termen *skift* kassatransaktionsdata och aktiviteter mellan två tidpunkter. För varje skift jämförs belopp som förväntas mot det belopp som har räknats och deklareras.

Vanligtvis öppnas skift i början av arbetsdagen. Då deklarerar en användare startbeloppet som kassalådan innehåller. Försäljningstransaktioner ska sedan genomföras under dagen. Slutligen räknas kassalådan i slutet av dagen och de avslutande beloppen deklareras. Skiftet har avslutats och en Z-rapport skapas. Z-rapport anger om det finns något över- eller underskott.

## <a name="typical-shift-scenarios"></a>Typiska skiftscenarier

Retail innehåller flera konfigurationsalternativ och kassaåtgärder som stöder en mängd olika affärsprocesser i slutet av dagen för kassan. Det här avsnittet beskriver några vanliga skiftscenarier.

### <a name="fixed-till"></a>Fast till

Tidigare har det här scenariot använts oftast. Det används fortfarande ofta. I ett "fast till"-skift associeras skiftet till ett visst register. De flyttas inte från ett register till ett annat. Ett ”fast till”-skift kan användas av en enskild användare eller delas av flera användare. ”Fast till”-skift kräver inte någon särskild konfiguration.

### <a name="floating-till"></a>Flytande till

I ”flytande till”-skift kan skift och kassalåda flyttas från en kassa till en annan. Även om en kassa endast kan ha ett aktivt skift per kassalåda kan skift avbrytas tillfälligt och sedan fortsätta senare eller i en annan kassa.

T.ex. en butik har två kassor. Varje kassa öppnas i början av den dag när kassören öppnar ett nytt skift och ger startbeloppet. När en kassör tar en paus, skjuter kassören upp skiftet och tar bort det från kassalådan. Kassan blir då tillgänglig för andra kassörerna. En annan kassör kan logga in och öppna sitt eget skift i kassan. Efter första kassörens rast har avslutats kan den kassören återuppta sitt skift när någon av de andra kassorna blir tillgängliga. ”Flytande till”-skift kräver inte någon särskild konfiguration eller behörighet.

### <a name="single-user"></a>Enskild användare

Många återförsäljare föredrar att bara ha en användare per skift och för att garantera den högsta nivån av ansvar för kontanter i kassalådan. Om bara en användare kan använda kassaapparaten som är kopplad till ett skift kan användaren endast hållas ansvarig för eventuella avvikelser. Om flera användare använder ett skift, är det svårt att avgöra vem som har skrivit fel eller som försöker stjäla från kassalådan.

### <a name="multiple-users"></a>Flera användare

Vissa återförsäljare är villiga att offra ansvar som ger enskilda användare skift och tillåta flera användare per skift. Denna metod gäller när det finns fler användare än tillgängliga kassor och behovet av flexibla och snabba lösningar uppväger risken för förlust. Gäller även när butikschefer inte har egna skift men kan vid behov använda deras kassörers skift. Om du vill logga in och använda ett skift som har öppnats av en annan användare, måste användaren dessutom ha POS-behörigheten **Tillåt flera skiftinloggningar**.

### <a name="shared-shift"></a>Delade skift

En konfiguration för ”delade skift” låter återförsäljare ha ett enda skift på flera kassor, kassalådor och användare. Ett delat skift har ett enda startbelopp och ett enkelt avslutande belopp som sammanfattas över alla kassalådor. Delade skift är vanligast när mobila enheter används. I det här scenariot är en separat kassalåda inte reserverad för varje kassa. Alla kassor kan däremot dela en kassalåda.

För delade skift som ska användas i en butik måste kassalådan ha konfigurerats som ”delad skiftlåda” i **Retail \>kanalinställningar \>POS-inställningar \>POS-profiler\> maskinvaruprofiler \>kassalåda**. Dessutom måste användare ha minst delad skiftbehörigheter (Tillåt hantering av delade skift och tillåt användning av delade skift).

> [!NOTE]
> Endast ett delat skift åt gången kan vara öppet i varje butik. Delade skift och fristående skift kan användas i samma butik.

## <a name="shift-and-drawer-operations"></a>Åtgärder av kassalåda och skift

Olika åtgärder kan utföras för att ändra status för ett skift eller för att öka eller minska penningbeloppet i kassalådan. Det här avsnittet beskriver dessa skiftoperationer för Retail Modern POS och Cloud POS.

### <a name="open-shift"></a>Öppna skift

POS kräver att en användare har ett aktivt, öppet skift för att utföra alla åtgärder som leder till en finansiell transaktion, t.ex en försäljning, retur eller kundorder.

När en användare loggar in till kassan, verifierar systemet först om det finns ett aktivt skift för användaren i den aktuella kassan. Om ett aktivt skift inte är tillgängligt kan användaren sedan välja att öppna ett nytt skift, återuppta ett befintligt skift eller fortsätta att logga in i läget ”utan låda”, beroende på systemkonfigurationen och användarens behörigheter.

### <a name="declare-start-amount"></a>Stäm av startbelopp

Den här åtgärden är ofta den första åtgärden som vidtas i ett nyligen öppnat skift. Användare anger startbeloppet i kassalådan för skiftet. Denna åtgärd är viktig eftersom över- eller underskottberäkningen som utförs när ett skift som har stängts kan identifiera startbelopp.

### <a name="float-entry"></a>Växelpost

*Växeltransaktioner* är ej försäljningstransaktioner som utförs i ett aktivt skift och de ökar kontantbeloppet i kassalådan. Ett vanligt exempel på en växelpost är en transaktion för att lägga till ytterligare växel i kassalådan när det börjar ta slut.

### <a name="tender-removal"></a>Borttagning av betalningsmedel

*Borttagning av betalningsmedel* är ej försäljningstransaktioner som utförs i ett aktivt skift för att minska kontantbeloppet i kassalådan. Denna åtgärd används oftast tillsammans med en växelpost i ett annat skift. Till exempel Kassa 1 börjar få slut på växel så användaren av Kassa 2 utför en borttagning av betalningsmedel för att minska beloppet i kassalådan. Användaren i kassan 1 gör sedan en växelpost för att öka hans eller hennes kassalåda.

### <a name="suspend-shift"></a>Skjut upp skift

Användare kan skjuta upp sina aktiva skift för att frigöra den aktuella kassan till en annan användare eller flytta sitt skift till en annan kassa (i detta fall kallas skiftet ofta för ”flytande kassalåda”).

Att skjuta upp skift förhindrar eventuella nya transaktioner eller ändringar av skiftet tills det återupptas.

### <a name="resume-shift"></a>Återuppta ett skift

Den här åtgärden tillåter användare att återuppta ett tidigare avbrutet skift i en kassa som inte redan har ett aktivt skift.

### <a name="tender-declaration"></a>Kassaavstämning

Den här åtgärden utförs om du vill ange det totala beloppet som finns i kassalådan. Användarna utför oftast denna åtgärd innan de stänger ett skift. Den angivna värdet jämförs med det förväntade skiftets belopp om du vill beräkna för högt/för lågt belopp.

### <a name="safe-drop"></a>Lämna pengar i kassaskåp

Säkra insättningar kan utföras när som helst under ett aktivt skift. Den här åtgärden tar bort pengar från kassalådan, så att de kan överföras till en säkrare plats, till exempel ett kassaskåp i ett enskilt rum. Det totala beloppet som registrerats för säkra insättningar finns fortfarande i summorna för skift, men behöver inte räknas som en del av kassaavstämningen.

### <a name="bank-drop"></a>Bankinsättning

Som säkra insättningar utförs bankinsättningar även under aktiva skift. Den här åtgärden tar bort pengar från skiftet för att förbereda för bankinsättningar.

### <a name="blind-close-shift"></a>Stäng skift dolt

*Skift som har stängts dolt* är inte längre är aktiva men har inte avslutats helt. Till skillnad från uppskjutna skift kan skift som har stängts dolt inte återupptas. Dock kan åtgärder såsom deklarera startbelopp och kassaavstämning utföras på dem senare, eller från en annan kassa.

Ett skift som har stängts dolt används ofta för att frigöra en kassa för en ny användare eller skift, utan att behöva helt räkna, stämma av eller stänga skiftet först.

### <a name="close-shift"></a>Stäng skift

Denna åtgärd beräknar summor för skift, för högt/för lågt belopp och slutför sedan ett aktivt skift eller skift som har stängts dolt. Beroende på användarens behörighet skrivs också en Z-rapport för skiftet. Skift som har stängts dolt kan inte återupptas eller ändras.

### <a name="print-x"></a>Skriv ut X

Åtgärden som skapar och skriver ut en X-rapport för aktuella aktiva skiftet.

### <a name="reprint-z"></a>Skriv ut Z igen

Åtgärden skriver ut den senaste Z-rapporten igen som systemet skapade när ett skift stängdes.

### <a name="manage-shifts"></a>Hantera skift

Den här åtgärden låter användare visa alla skift som är aktiva, uppskjutna och som har stängts dolt för butiken. Beroende på vilka behörigheter användarna har kan de utföra åtgärder för deras slutgiltiga stängningsprocedurerna, till exempel kassaavstämning och stängning av skift för skift som har stängts dolt. Åtgärden kommer även att låta användare visa och ta bort ogiltiga skift i det sällsynta fallet att ett skift är kvar i ett dåligt tillstånd efter att ha växlat mellan offline- och online-lägen. Dessa ogiltiga skift innehåller inte någon ekonomisk information eller transaktionsdata för avstämning.

## <a name="shift-and-drawer-permissions"></a>Behörigheter för kassalåda och skift

Följande POS-behörigheter påverkar vad vi kan och inte kan göra i olika situationer:

- **Tillåt hemlig stängning**
- **Tillåt utskrift av X-rapport**
- **Tillåt utskrift av Z-rapport**
- **Tillåt kassaavstämning**
- **Tillåt kassaredovisning**
- **Öppna kassalådan utan försäljning**
- **Tillåt flera skiftinloggningar** - Med denna behörighet kan användaren logga in och använda ett skift som en annan användare öppnade. Användare som inte har den här behörigheten kan logga in och använda skift som de har öppnat.
- **Att hantera delade skift** – användarna måste ha behörighet för att öppna eller stänga ett delat skift.
- **Att använda delade skift** – användarna måste ha behörighet för att logga in och använda ett delat skift.

## <a name="back-office-end-of-day-considerations"></a>Att tänka på backoffice i slutet av dagen

Det sätt som skift och kassaavstämning används i POS skiljer sig från hur transaktionsdata sammanfattas under utdragsberäkningen. Det är viktigt att du förstår skillnaden. Beroende på konfigurationen och affärsprocesserna kan skiftdata i POS (Z-rapport) och en utdragsberäkning i backoffice ge dig olika resultat. Denna skillnad innebär inte nödvändigtvis att skiftdata eller utdragsberäkningen är fel eller att det finns ett problem med informationen. Det innebär bara att parametrarna som tillhandahålls kan innefatta ytterligare transaktioner eller färre transaktioner eller att transaktionerna har sammanfattats annorlunda.

Även om alla återförsäljare har olika affärsbehov, rekommenderar vi att du ställer in datorn för att undvika situationer där skillnaderna mellan den här typen ska utföras:

Gå till **Retail \>kanaler \>detaljhandel \>alla detaljhandel \>utdrag/stängning**, och för varje butik anger både **utdragsmetod** och **Stängningsmetod** till **skift**.

Den här inställningen kan garantera att backoffice-rapporterna innehåller samma transaktioner som skift i POS och att informationen summeras genom det skiftet.

Mer information om utdrag och stängningsmetoder finns i [spara konfigurationer för butiksutdrag](https://docs.microsoft.com/dynamics365/unified-operations/retail/tasks/store-configurations-retail-statements).
