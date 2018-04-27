---
title: "Hantering av skift och kassalåda"
description: "Den här artikeln innehåller en beskrivning av hur du ställer in och använder de två typerna av skift för butikskassor: delat och fristående. Delade skift kan användas av flera användare på flera ställen, medan fristående skift enbart kan användas av en medarbetare åt gången."
author: rubencdelgado
manager: AnnBe
ms.date: 02/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 8a24f8adc4f7886a1f942d83f7a4eb12e7034fcd
ms.openlocfilehash: c1483d3240d266845cea7789b70c038cb98fdfcc
ms.contentlocale: sv-se
ms.lasthandoff: 03/22/2018

---

# <a name="shift-and-cash-drawer-management"></a>Hantering av skift och kassalåda

[!INCLUDE [banner](includes/banner.md)]

Den här artikeln innehåller en beskrivning av hur du ställer in och använder de två typerna av skift för butikskassor: delat och fristående. Delade skift kan användas av flera användare på flera ställen, medan fristående skift enbart kan användas av en medarbetare åt gången.

Det finns två typer av skift för butikskassor (POS): fristående och delade. Fristående skift kan enbart användas av en enda arbetare åt gången. Delade skift kan användas av flera användare på flera ställen. På så sätt skapar de effektivt ett enda skift för flera medarbetare i en butik.

## <a name="standalone-shifts"></a>Fristående skift
Fristående skift används i ett traditionellt, fast kassascenario där kontanter stäms av separat för varje kassaregister. I en livsmedelsbutik till exempel finns det vanligtvis flera fasta kassaregister och varje kassaregister tilldelas i sin tur till en kassör. I det här fallet är det sannolikt att varje kassaregister används som ett fristående skift och kassören ansvarar för kassaregistrets kassalåda. Ett fristående skift omfattar all aktivitet i registret under kassörens arbetsskift. Aktiviteter kan omfatta startbeloppet som läggs i kassalådan, kontanter som tas bort eller läggs till genom åtgärder såsom bankinsättningar och växelposter samt kassaavstämningen i slutet av skiftet.

### <a name="set-up-a-stand-alone-shift"></a>Ställa in ett fristående skift

Ett fristående skift tilldelas på kassalådenivå. Här beskrivs hur du ställer in ett fristående skift i ett kassaregister.

1.  Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofiler** &gt; **Maskinvaruprofiler**.
2.  Välj vilken maskinvaruprofil som ska användas för det fristående skiftet.
3.  Bekräfta att alternativet **Kassalåda för delat skift** på snabbfliken **Kassalåda** är inställt på **Nej**.
4.  Klicka på **Spara**.
5.  Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaapparat**.
6.  Välj registret som kräver ett fristående skift och klicka sedan på **Redigera**.
7.  Markera maskinvaruprofilen du valde i steg 2 i fältet **Maskinvaruprofil**.
8.  Klicka på **Spara**.
9.  Klicka på **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.
10. Välj distributionsschema **1090** och klicka sedan på **Kör nu** för att synkronisera ändringarna av kassan.

### <a name="use-a-stand-alone-shift"></a>Använda ett fristående skift

1.  Logga in i kassan.
2.  Om inget skift är öppet väljer du **Öppna ett nytt skift**.
3.  Gå till åtgärden **Ange startbelopp** och ange kontantbeloppet som läggs i kassalådan i början av arbetsdagen.
4.  Utför några transaktioner.
5.  Välj **Stäm av betalningsmedel** i slutet av dagen för att ange kontantbeloppet som finns kvar i kassalådan.
6.  Ange kontantbeloppet och klicka sedan på **Spara** för att spara kassaavstämningen.
7.  Välj **Stäng skift** för att avsluta skiftet.

**Obs!** Andra åtgärder är tillgängliga under skiftet beroende på vilka affärsprocesser som används. Åtgärderna **Lämna pengar i kassaskåp**, **Bankinsättning** och **Borttagning av betalningsmedel** kan användas för att ta bort pengar från kassalådan under dagen eller innan skiftet avslutas. Om kontanterna i en kassalåda börjar ta slut kan åtgärden **Växelpost** användas för att lägga till kontanter i kassalådan.

## <a name="shared-shifts"></a>Delade skift
Delade skift används i en miljö där flera kassörer delar en kassalåda eller en uppsättning kassalådor under arbetsdagen. Vanligtvis används delade skift i mobila kassamiljöer. I en mobil miljö är kassören inte tilldelad och ansvarig för en enda kassalåda. I stället måste alla kassörer kunna ta betalt och lägga till kontanter i den kassalåda som är närmast dem. I det här fallet ingår kassalådorna som delas mellan kassörerna i ett delat skift. Alla kassalådor i delade skift ingår i samma skift för aktiviteter som är relaterade till kontanthanteringen under respektive skift. Startbeloppet för skiftet ska därför innehålla summan av alla kontanter i alla kassalådor som ingår i det delade skiftet. Av samma anledning kommer kassaavstämningen att innehålla summan av alla kontanter i alla kassalådor som ingår i det delade skiftet. **Obs!** Endast ett delat skift åt gången kan vara öppet i varje butik. Delade skift och fristående skift kan användas i samma butik.

### <a name="set-up-a-shared-shift"></a>Ställa in ett delat skift

1.  Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofiler** &gt; **Maskinvaruprofiler**.
2.  Välj vilken maskinvaruprofil som ska användas för det delade skiftet.
3.  Gå till snabbfliken **Kassalåda** och ställ in alternativet **Kassalåda för delat skift** till **Ja**.
4.  Klicka på **Spara**.
5.  Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställning** &gt; **Kassaapparat**.
6.  Välj registret som kräver ett delat skift och klicka sedan på **Redigera**.
7.  Markera maskinvaruprofilen du valde i steg 2 i fältet **Maskinvaruprofil**.
8.  Klicka på **Spara**.
9.  Klicka på **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.
10. Välj distributionsschema **1090** och klicka sedan på **Kör nu** för att synkronisera ändringarna av kassan.

### <a name="use-a-shared-shift"></a>Använda ett delat skift

1.  Logga in i kassan.
2.  Om kassan ännu inte är ansluten till en maskinvarustation, välj **Åtgärd som inte berör kassalådan** och välj sedan åtgärden **Välj maskinvarustation** för att aktivera en maskinvarustation för det delade skiftet. Den här steget krävs endast första gången ett register läggs till i en miljö med delade skift.
3.  Logga ut från kassan och logga sedan in igen.
4.  Välj **Skapa ett nytt skift**.
5.  Välj **Ange startbelopp**.
6.  Ange startbeloppet för alla kassalådor i butiken som ingår i det delade skiftet och klicka sedan på **Spara**.
    -   Om du vill lägga till startbeloppet till varje efterföljande kassalåda, använd åtgätden **Välj maskinvarustation** för att aktivera maskinvarustationen.
    -   Om du vill lägga till en kassalåda till en speciell kassalåda, använd åtgärden **Öppna kassalådan**.
    -   Fortsätt tills alla kassalådor i det delade skiftet innehåller sin del av startbeloppet.

7.  Öppna alla kassalådor vid dagens slut och ta bort kontanterna.
8.  När du tagit bort kontanterna från sista kassalådan, räkna alla kontanter från alla kassalådor.
9.  Använd åtgärden **Stäm av betalningsmedel** för att ange det totala kontantbeloppet från alla kassalådor som ingår i det delade skiftet.
10. Använd åtgärden **Avsluta skift** för att avsluta delade skift.

## <a name="shift-operations"></a>Skiftoperationer
Olika åtgärder kan utföras för att ändra status för ett skift eller för att öka eller minska penningbeloppet i kassalådan. I avsnittet nedan beskrivs dessa skiftåtgärder för Dynamics 365 for Retail Modern POS och Cloud POS.

**Öppna skift**

POS kräver att en användare har ett aktivt, öppet skift för att utföra alla åtgärder som leder till en finansiell transaktion, t.ex en försäljning, retur eller kundorder.  

Vid inloggning i POS kontrollerar systemet först om användaren har ett aktivt skift tillgänglig på den aktuella journalen. Om inte kan användaren sedan välja att öppna ett nytt skift, återuppta ett befintligt skift eller fortsätta att logga in i läget ”utan låda”, beroende på systemkonfigurationen och deras behörigheter.

**Stäm av startbelopp**

Den här åtgärden är ofta den första åtgärden som vidtas i ett nyligen öppnat skift. Användare anger startbeloppet i kassalådan för skiftet. Detta är viktigt eftersom över/underberäkningen som uppstår när du avslutar ett skift tar hänsyn till detta belopp.

**Växelpost**

Växelposter är ej försäljningstransaktioner som utförs i ett aktivt skift och de ökar kontantbeloppet i kassalådan. Ett vanligt exempel på en växelpost är om du vill lägga till ytterligare växel i kassalådan när det börjar ta slut.

**Borttagning av betalningsmedel**

Borttagning av betalningsmedel är ej försäljningstransaktioner som utförs i ett aktivt skift för att minska kontantbeloppet i kassalådan. Detta används oftast tillsammans med en växelpost i ett annat skift. Till exempel Kassa 1 börjar få slut på växel så användaren av Kassa 2 utför en borttagning av betalningsmedel för att minska beloppet i kassalådan. Användaren av Kassa 1 utför sedan en växelpost för att öka sitt belopp:

**Skjut upp skift**

Användare kan skjuta upp sina aktiva skift för att frigöra den aktuella kassan till en annan användare eller flytta sitt skift till en annan kassa (detta kallas ofta för ”flytande kassalåda”). 

Att skjuta upp skift förhindrar eventuella nya transaktioner eller ändringar av skiftet tills det återupptas.

**Återuppta ett skift**

Den här åtgärden tillåter en användare att återuppta ett tidigare avbrutet skift i en kassa som inte redan har ett aktivt skift.

**Kassaavstämning**

Kassaavstämning är åtgärden som användaren utför för att ange det totala beloppet som för närvarande finns i kassalådan, oftast innan skiftet stängs. Detta är det värde som jämförs med det förväntade skiftet om du vill beräkna för högt/för lågt belopp.

**Lämna pengar i kassaskåp**

Säkra insättningar kan utföras när som helst under ett aktivt skift. Den här åtgärden tar bort pengar från kassalådan, så att de kan överföras till en säkrare plats, till exempel ett kassaskåp i ett enskilt rum. Det totala beloppet som registrerats för säkra insättningar finns fortfarande i summorna för skift, men behöver inte räknas som en del av kassaavstämningen.

**Bankinsättning**

Som säkra insättningar utförs bankinsättningar även under aktiva skift. Den här åtgärden tar bort pengar från skiftet för att förbereda för bankinsättningar.

**Stäng skift dolt**

Ett skift som har stängts dolt är ett skift som inte längre aktivt men som inte har stängts helt. Ett skift som har stängts dolt kan inte fortsätta som ett uppskjutet skift, men procedurer som att deklarera utgångsbelopp och kassaavstämning kan göras vid ett senare tillfälle eller från en annan kassa.

Ett skift som har stängts dolt används ofta för att frigöra en kassa för en ny användare eller skift, utan att behöva helt räkna, stämma av eller stänga skiftet först. 

**Stäng skift**

Denna åtgärd beräknar summor för skift, för högt/för lågt belopp och slutför sedan ett aktivt skift eller skift som har stängts dolt. Skift som har stängts dolt kan inte återupptas eller ändras.  

**Hantera skift**

Den här åtgärden låter användare visa alla skift som är aktiva, uppskjutna och som har stängts dolt för butiken. Beroende på vilka behörigheter användarna har kan de utföra åtgärder för deras slutgiltiga stängningsprocedurerna, till exempel kassaavstämning och stängning av skift för skift som har stängts dolt. Åtgärden kommer även att låta användare visa och ta bort ogiltiga skift i det sällsynta fallet att ett skift är kvar i ett dåligt tillstånd efter att ha växlat mellan offline- och online-lägen. Dessa ogiltiga skift innehåller inte någon ekonomisk information eller transaktionsdata för avstämning. 

