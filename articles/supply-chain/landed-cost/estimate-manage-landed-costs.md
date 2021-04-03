---
title: Uppskatta och hantera hemtagningskostnader
description: I systemet används dina automatiska kostnadsinställningar för att beräkna en uppskattning av hemtagningskostnaden. I det här avsnittet beskrivs hur du definierar olika scenarier när du vill leverera en mer korrekt uppskattning.
author: sherry-zheng
manager: tfehr
ms.date: 01/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMCostTemplateTable, ITM CostEstimateDialog, ITMCostEstimateTable, SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-26
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: cbd652f2b29f7a78ad9e4e1d3dda4a3ef8a9f3f3
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501280"
---
# <a name="estimate-and-manage-landed-costs"></a>Uppskatta och hantera hemtagningskostnader

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I systemet används dina [automatiska kostnadsinställningar](auto-cost-setup.md) för att beräkna en uppskattning av hemtagningskostnaden. Dessutom kan du definiera olika scenarier när du vill leverera en mer korrekt uppskattning. Dessa scenarier lagras. Därför kan du granska dem senare och jämföra dem med faktiska värden i en rapport. Du kan även uppdatera artikelpriset.

## <a name="set-up-cost-estimates"></a>Konfigurera kostnadsuppskattningar

### <a name="set-up-cost-templates"></a>Ställ in kostnadsmallar

Kostnadsmallar skapar standardinställningar som användare som får uppskattningen inte nödvändigtvis vet. Mallar minskar komplexiteten i uppskattningsprocessen genom att minimera de val som användarna måste ange för att få en korrekt uppskattning. Om du använder standardkostnadsmodellen kan du använda kostnadsmallar medan du ställer in kostnaderna för varor.

Du ställer in dina kostnadsmallar genom att gå till **Hemtagningskostnad \> Inställning av kostnadsredovisning \> Kostnadsmallar**. På sidan **Kostnadsmallar** visas alla aktuella kostnadsmallar i listfönstret till vänster. Med knapparna i åtgärdsfönstret kan du skapa, ta bort och redigera mallar.

Följande register beskriver de fält som är tillgängliga för varje mall.

| Fält | beskrivning |
|---|---|
| Kostnadsmall | Ange ett unikt namn för kostnadsmallen. Namnet beskriver vanligtvis faktorn eller kostnadsmultiplikatorn för mallen. |
| beskrivning | Ange en beskrivning för kostnadsmall. |
| Speditör | Välj det transportföretag som ska användas när mallen används. |
| Leveranssätt | Välj det leveranssätt, t.ex. båt eller flyg, som ska användas när mallen används. Det här fältet gör det lättare att bestämma de automatiska kostnader som associeras med varorna vid en kostnadsuppskattning. |
| Typ av fraktcontainer | Välj typ av leveransbehållare som ska användas när mallen används. Det här fältet gör det lättare att bestämma de automatiska kostnader som associeras med varorna vid en kostnadsuppskattning. |
| Tullmäklare | Tullombudet (leverantör) som ska användas när mallen används. Det här fältet gör det lättare att bestämma de automatiska kostnader som associeras med en kostnadsuppskattning. |
| Faktor | Ange multiplikatorn (procentsatsen) som automatiskt ska tillämpas på kostnadsuppskattningen när mallen används. Skriv till exempel om du vill lägga till 10 procent till den beräknade kostnadsuppskattningen, ange *1,10*. |

### <a name="create-a-cost-estimate"></a>Skapa en kostnadsuppskattning

Använd dialogrutan **Kostnadsuppskattning** om du vill skapa en ny kostnadsuppskattning som baseras på en vald kostnadsmall, en vald uppsättning artiklar och andra detaljer som kan användas för en kostnadsuppskattning. Dessa inställningar används sedan för att fastställa de uppskattade hemtagningskostnaderna för varor. Dessa kostnadsuppskattningar används främst för att arbeta med standardkostnadsartiklar. Genom att lägga till de uppskattade hemtagningskostnaderna till standardkostnaden för varor i lagret, bör du uppleva mindre avvikelsetransaktioner när varorna läggs till en färd, eftersom standardkostnaden återspeglar uppskattningarna av dessa hemtagningskostnader.

Öppna dialogrutan **Kostnadsuppskattning** genom att gå till **Hemtagningskostnader \> Periodiska kostnader \> Kostnadsuppskattning**. Ställ sedan in fälten enligt beskrivningen i följande underavsnitt på varje snabbflik. Klicka på **OK** för att skapa den nya uppskattningen. Sidan **Kostnadsuppskattning** (**Hemtagningskostnader \> Frågor \> Kostnadsuppskattningar**) visas och visar din nya uppskattning, enligt beskrivningen senare i det här avsnittet.

### <a name="settings-on-the-parameters-tab"></a>Inställningar på fliken Parametrar

I följande tabell beskrivs fälten som är tillgängliga i dialogrutan **Parametrar** i **Kostnadsuppskattning**.


| Fält | beskrivning |
|---|---|
| Kostnadsmall | Välja en kostnadsmall. De inställningar som associeras med den valda mallen används för att bestämma vilka automatiska kostnader som ska användas. |
| Uppskatta datumet | Som standard är det här fältet inställt på dagens datum, men du kan ändra värdet. Det angivna datumet används för att välja tillämpliga försäljningspriser, inköpspriser, automatiska kostnader och valutakurs om en leveranskurs används. |
| Mått | Kostnaderna kan bero på en mätning. När till exempel flygfrakt används kan volymprissättning gälla. Om kostnaden beror på en mätning anger du värdet på måttet. Annars rekommenderar vi att du ställer in det här fältet till *1*, om du inte är säker på att ingen fördelning sker genom mätning. Ange ett decimalvärde. Enheten är den som definieras i den tillämpliga posten för automatisk kostnad. |
| Resemall | Välj en [färdmall](multi-leg-journey-setup.md). Detta fält används för att fastställa de korrekta automatiska kostnader som ska användas. |
| Från hamn | Den port som artiklarna ska levereras från. Det här fältet ställs in utifrån den valda färdmallen. |
| Till hamn | Den port som artiklarna ska levereras till. Det här fältet ställs in utifrån den valda färdmallen. |
| Valuta | Välj vilken valuta artiklarna ska köpas i. |
| Fraktbehållare | Om flera behållare normalt används anger du antalet behållare. Systemet kommer sedan att använda kostnader för flera behållare när det uppskattar kostnaderna. |
| Folios | Ange kvantiteten om flera folio används. (Kvantiteten är vanligtvis *1*.) |
| Site | Ange den plats dit varorna ska levereras. |

### <a name="settings-on-the-items-tab"></a>Inställningar på fliken Artiklar

På fliken **Artiklar** kan du lägga till så många artiklar som du behöver i uppskattningen. Använd verktygsfältet om du vill lägga till objekt i rutnätet eller ta bort objekt. Välj **Lager \> Visa dimensioner** i verktygsfältet om du vill öppna en dialogruta där du kan lägga till dimensionskolumner i rutnätet eller ta bort kolumner.

Följande register beskriver de fält som är tillgängliga för varje artikel.

| Fält | beskrivning |
|---|---|
| Artikelnummer | Välj artikeln som du vill bestämma priset för. (Om artikeln ännu inte finns i systemet skapar du en artikel, kopplar den eventuellt till en kostnadsgrupp för artikeln och lämnar sedan priset tomt, eller skapar eller ändrar priset.) |
| Leverantörskonto | Välj den leverantör som ska användas för uppskattningen av den här artikeln. Om en standardleverantör tilldelas artikeln ställs det här fältet in automatiskt. |
| Kvantitet | Välj vilken kvantitet du vill köpa. |
| Självkostnad | Systemet använder sina prisregler för att hitta ett ursprungligt pris, men du kan åsidosätta det priset om det behövs. |
| Försäljningspris | Ange förväntat försäljningspris för varorna. |
| Mått | Ange ett decimalvärde för mätningen av varorna. Enheten är den som har ställts in för den tillämpliga frisläppta produkten. |
| Uppdatera artikelns vikt/volym | Markera den här kryssrutan om du vill uppdatera vikt eller volymmått för den frisläppta produkten så att den matchar värdet **mått** som angetts för den här raden. |
| (Övriga dimensioner) | Beroende på vilka dimensioner du har valt att visa kanske ytterligare kolumner med information om varje artikel visas. |

Om du vill visa eller justera volym- och/eller viktdetaljer för en artikel markerar du artikeln i rutnätet och använder sedan fälten längst ned på sidan.

## <a name="manage-estimated-costs"></a>Hantera uppskattade kostnader

Gå till om du vill visa och redigera de kostnadsberäkningar du har skapat **Hemtagningskostnad \> Frågor \> Kostnadsuppskattningar**. På sidan **Kostnadsuppskattningar** visas alla aktuella kostnadsuppskattningar i listfönstret till vänster. Med knapparna i åtgärdsfönstret kan du skapa, ta bort och arbeta med en vald uppskattning. Observera att du inte kan skapa en ny kostnadsuppskattning från sidan **Kostnadsuppskattning**. Använd istället dialogrutan **Kostnadsuppskattning** (**Hemtagningskostnad \> Periodiska uppgifter \> Kostnadsuppskattning**), enligt beskrivningen tidigare i det här avsnittet.

Sidan **Kostnadsuppskattningar** visar hur varje uppskattad kostnad härleddes. Här visas också den uppskattade hemtagningskostnaden för varje artikel. Du kan ändra en kostnadsuppskattning genom att ändra självkostnaden och/eller valutan som associeras med de olika varorna. Du kan även ändra de associerade färdkostnaderna på både den första och sista nivån i behållaren. När du använder den här sidan för att ändra kostnaderna uppmanas du att beräkna om de uppskattade kostnaderna för artiklarna i kostnadsuppskattningen. När du är klar kan du använda uppskattningarna om du vill uppdatera självkostnaden för artiklarna i kostnadsmallen.

### <a name="information-on-the-header"></a>Information i rubriken

Överst på sidan **Kostnadsuppskattningar** visas de inställningar som användes för att generera den valda kostnadsuppskattningen, enligt beskrivningen i det föregående avsnittet. 

### <a name="settings-and-buttons-on-the-lines-fasttab"></a>Inställningar och knappar på snabbflikarna Rader

På snabbflikarna **Rader** visas alla artiklar som ingår i den aktuella uppskattningen. Följande register beskriver de fält som är tillgängliga för varje rad.

| Fält | beskrivning |
|---|---|
| Leverantörskonto | Leverantörskontot som har associerats med artikeln. |
| Artikelnummer | Artikelnummer. |
| Kvantitet | Antalet artiklar som används för att bestämma kostnaden. |
| Självkostnad | Självkostnaden enligt handelsavtalet. Värdet visas i lokal valuta. |
| Mått | Den enskilda mätningen. Enheten är den som har definierats för den tillämpliga frisläppta produkten. |
| Uppskattad hemtagningskostnad | Den uppskattade hemtagningskostnaden för den totala kvantiteten. |
| Per kolli | Den uppskattade hemtagningskostnaden delas av kvantiteten. |
| (Övriga dimensioner) | Beroende på vilka dimensioner du har valt att visa kanske ytterligare kolumner med information om varje artikel visas. |

I följande tabell beskrivs de knappar som finns tillgängliga i verktygsfältet på snabbfliken **Rader**.

| Knapp | beskrivning |
|---|---|
| Lägg till | Lägg till artiklar till kostnadsuppskattningen. När du har lagt till artiklar måste du välja **Omberäkna** i åtgärdsfönstret. |
| Ta bort | Ta bort artiklar från kostnadsuppskattningen. När du har tagit bort artiklar måste du välja **Omberäkna** i åtgärdsfönstret. |
| Kostnader för sjötransport | Öppna en sida där du kan visa och redigera olika typer av kostnader för artikeln. |
| Lager \> Visa dimensioner | Öppna en dialogruta där du kan lägga till dimensionskolumner i rutnätet eller ta bort kolumner. |

### <a name="settings-on-the-general-fasttab"></a>Inställningar på snabbfliken Redovisning

På snabbfliken **Allmänt** visas information om artikeln som har markerats på snabbfliken **Rader**. En stor del av informationen upprepas från snabbflikarna **Rader** och kan redigeras på båda håll. Här finns även ytterligare detaljer. Värdena i de extra fälten baseras på inställningarna för den tillämpliga frisläppta produkten.

### <a name="settings-on-the-dimension-fasttab"></a>Inställningar på snabbfliken Dimension

På snabbfliken **Dimension** visas värden för alla tillgängliga lagerdimensioner för artikeln som har markerats på snabbfliken **Rader**, oavsett vilka dimensioner du har valt att visa där. Alla värden som visas här kommer från den tillämpliga kostnadsuppskattningsmallen. De är valfria i kostnadsuppskattningsmallen.

### <a name="buttons-on-the-action-pane"></a>Knappar i åtgärdsfönstret

Du kan använda knapparna på åtgärdsfönstret på sidan **kostnadsuppskattning** för att arbeta med vald kostnadsuppskattning. I följande tabell beskriver de knappar som är tillgängliga.

| Åtgärd | beskrivning |
|---|---|
| Kostnadsförfrågan | Visa alla kostnader för färden. Du kan visa kostnader på nivån för den enskilda artikeln efter behov. |
| Uppdatera standardkostnad | <p>Uppdatera standardkostnaden genom att använda standardversionen för kostnadsredovisning som definieras på sidan **Parametrar för hemtagningskostnad**. Du kan åsidosätta den här versionen.</p><p>**Observera:** Om en artikel har flera artikeldimensioner (till exempel olika storlekar, färger och konfigurationer), men dessa dimensioner inte har valts för uppskattningen, skapas ett väntande pris för varje kombination i systemet.</p><p>**Viktigt:** Prisuppdelningen skapas och används för att fastställa standardkostnadsavvikelsen per landad kostnad.</p> |
| Kostnader för sjötransport | Visa och redigera kostnader för alla varor i försändelsen. |
| Omberäkna | Uppdatera de uppskattade hemtagningskostnader efter att färdkostnader har uppdaterats, lagts till eller tagits bort. |
| Lås | Lås posten för kostnadsuppskattning så att inga fler ändringar kan göras. |

## <a name="item-cost-price-update"></a>Uppdatering av självkostnad för artikel

Uppdateringar av periodisk uppgift **Uppdatering av självkostnad för artikeln** uppdaterar alla kostnadsuppskattningar som matchar de filter du anger när du kör uppgiften. Det här påminner om hur du väljer **Uppdatera standardkostnad** i åtgärdsfönstret för en enda uppskattning. I det här fallet gäller dock uppdateringen alla matchande uppskattningar.

Följ dessa steg för att köra den periodiska uppgiften.

1. Gå till **Hemtagningskostnad \> Periodiska uppgifter \> Uppdatering av självkostnad för artikel**.
1. I dialogrutan **Uppdatera självkostnad från uppskattning**, ange följande fält efter behov för att begränsa omfattningen av uppdateringen:

    - **Version** – Uppdatera endast uppskattningar där den angivna kostnadsredovisningsversionen används.
    - **Plats** – Uppdatera endast uppskattningar där den angivna platsen används.
    - **Kostnadsmall** – Uppdatera endast uppskattningar där den angivna mallen används.
    - **Till hamn** – Uppdatera endast uppskattningar där den angivna "till" hamn används.
    - **Uppskattat datum** – Uppdatera endast uppskattningar som har det angivna datumet.

1. Ställ in alternativen på snabbflikerna **Poster som ska ingå** och **Kör i bakgrunden** som vanligt för periodiska uppgifter.
1. Klicka på **OK** om du vill köra uppgiften.

> [!NOTE]
> Den periodiska uppgiften kommer endast att utföras om följande information finns tillgänglig:
>
> - Varje relevant produkt måste ha ett **Bruttodjup**, **Bruttobredd** och **Bruttohöjd** definierat.
> - Varje relevant leverantör måste ha definierat en **Från hamn**.
