---
title: "Hantering av skift och kassalåda"
description: "Den här artikeln beskrivs hur du ställer in och använder två typer av försäljningen (PO) SKIFT - delade och fristående retail mittpunkt. Delade skift kan användas av flera användare på flera ställen, medan fristående skift enbart kan användas av en medarbetare åt gången."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 09c7fce1fa83d6a8d6391db667b7260d2a199390
ms.lasthandoff: 03/31/2017


---

# <a name="shift-and-cash-drawer-management"></a>Hantering av skift och kassalåda

Den här artikeln beskrivs hur du ställer in och använder två typer av försäljningen (PO) SKIFT - delade och fristående retail mittpunkt. Delade skift kan användas av flera användare på flera ställen, medan fristående skift enbart kan användas av en medarbetare åt gången.

Det finns två typer av skift för butikskassor (POS): fristående och delade. Fristående skift kan enbart användas av en enda arbetare åt gången. Delade skift kan användas av flera användare på flera ställen. På så sätt skapar de effektivt ett enda skift för flera medarbetare i en butik.

## <a name="standalone-shifts"></a>Fristående SKIFT
Fristående skift används i ett traditionellt, fast kassascenario där kontanter stäms av separat för varje kassaregister. I en livsmedelsbutik till exempel finns det vanligtvis flera fasta kassaregister och varje kassaregister tilldelas i sin tur till en kassör. I det här fallet är det sannolikt att varje kassaregister används som ett fristående skift och kassören ansvarar för kassaregistrets kassalåda. Ett fristående skift omfattar all aktivitet i registret under kassörens arbetsskift. Aktiviteter kan omfatta startbeloppet som läggs i kassalådan, kontanter som tas bort eller läggs till genom åtgärder såsom bankinsättningar och växelposter samt kassaavstämningen i slutet av skiftet.

### <a name="set-up-a-stand-alone-shift"></a>Ställa in ett fristående skift

Ett fristående skift tilldelas på kassalådenivå. Här beskrivs hur du ställer in ett fristående skift i ett kassaregister.

1.  Klicka på **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**maskinvaruprofiler**.
2.  Välj vilken maskinvaruprofil som ska användas för det fristående skiftet.
3.  Bekräfta att alternativet **Kassalåda för delat skift** på snabbfliken **Kassalåda** är inställt på **Nej**.
4.  Click **Save**.
5.  Klicka på **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**registrerar**.
6.  Välj registret som kräver ett fristående skift och klicka sedan på **Redigera**.
7.  Markera maskinvaruprofilen du valde i steg 2 i fältet **Maskinvaruprofil**.
8.  Click **Save**.
9.  Klicka på **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**.
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
Delade skift används i en miljö där flera kassörer delar en kassalåda eller en uppsättning kassalådor under arbetsdagen. Vanligtvis används delade skift i mobila kassamiljöer. I en mobil miljö är kassören inte tilldelad och ansvarig för en enda kassalåda. I stället måste alla kassörer kunna ta betalt och lägga till kontanter i den kassalåda som är närmast dem. I det här fallet ingår kassalådorna som delas mellan kassörerna i ett delat skift. Alla kassalådor i delade skift ingår i samma skift för aktiviteter som är relaterade till kontanthanteringen under respektive skift. Startbeloppet för skiftet ska därför innehålla summan av alla kontanter i alla kassalådor som ingår i det delade skiftet. Av samma anledning kommer kassaavstämningen att innehålla summan av alla kontanter i alla kassalådor som ingår i det delade skiftet. **Anmärkning:** endast en delad SKIFT kan vara öppen åt gången i varje butik. Delade skift och fristående skift kan användas i samma butik.

### <a name="set-up-a-shared-shift"></a>Ställa in ett delat skift

1.  Klicka på **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**profiler för kassa**&gt;**maskinvaruprofiler**.
2.  Välj vilken maskinvaruprofil som ska användas för det delade skiftet.
3.  Gå till snabbfliken **Kassalåda** och ställ in alternativet **Kassalåda för delat skift** till **Ja**.
4.  Click **Save**.
5.  Klicka på **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**registrerar**.
6.  Välj registret som kräver ett delat skift och klicka sedan på **Redigera**.
7.  Markera maskinvaruprofilen du valde i steg 2 i fältet **Maskinvaruprofil**.
8.  Click **Save**.
9.  Klicka på **butik och handel**&gt;**Retail IT**&gt;**distributionsschema**.
10. Välj distributionsschema **1090** och klicka sedan på **Kör nu** för att synkronisera ändringarna av kassan.

### <a name="use-a-shared-shift"></a>Använda ett delat skift

1.  Logga in i kassan.
2.  Om kassan ännu inte är ansluten till en maskinvarustation, välj **Åtgärd som inte berör kassalådan** och välj sedan åtgärden **Välj maskinvarustation** för att aktivera en maskinvarustation för det delade skiftet. Den här steget krävs endast första gången ett register läggs till i en miljö med delade skift.
3.  Logga ut från kassan och logga sedan in igen.
4.  Välj **Skapa ett nytt skift**.
5.  Välj **Ange startbelopp**.
6.  Ange startbeloppet för alla kassalådor i butiken som ingår i det delade skiftet och klicka sedan på **Spara**.
    -   Om du vill lägga till startbeloppet till varje efterföljande kassalåda, använd åtgätden **Välj maskinvarustation ** för att aktivera maskinvarustationen.
    -   Om du vill lägga till en kassalåda till en speciell kassalåda, använd åtgärden **Öppna kassalådan**.
    -   Fortsätt tills alla kassalådor i det delade skiftet innehåller sin del av startbeloppet.

7.  Öppna alla kassalådor vid dagens slut och ta bort kontanterna.
8.  När du tagit bort kontanterna från sista kassalådan, räkna alla kontanter från alla kassalådor.
9.  Använd åtgärden **Stäm av betalningsmedel** för att ange det totala kontantbeloppet från alla kassalådor som ingår i det delade skiftet.
10. Använd åtgärden **Avsluta skift** för att avsluta delade skift.


