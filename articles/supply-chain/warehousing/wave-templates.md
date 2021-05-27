---
title: Påfyllnadsmallar
description: I det här avsnittet beskrivs hur du ställer in villkoren som avgör om påfyllnad bearbetas manuellt eller automatiskt och arbetet som genereras för ett lagerställe när en påfyllnad bearbetas.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 95e315c1bf1e363db413abae985d510848059e62
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020069"
---
# <a name="wave-templates"></a>Påfyllnadsmallar

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in villkoren som avgör om påfyllnad bearbetas manuellt eller automatiskt och arbetet som genereras för ett lagerställe när en påfyllnad bearbetas. Du anger villkor genom att ställa in påfyllnadsmallar och frågor som matchar en påfyllnad mot frisläppta rader i försäljningsorder, tillverkningsorder och kanbans.

## <a name="settings-for-wave-templates"></a>Inställningar för påfyllnadmallar

När du ställer in en påfyllnadsmall, anger du följande:

- Den **plats** och det **lagerställe** som mallen ska skapa arbete för.
- Den ordning som mallen ska utvärderas i. Sekvensen i vilken mallarna matchas mot frisläpps-rader på försäljningsorder, tillverkningsorder och kanban. När en rad frisläpps tillämpar systemet den första påfyllnadmallen som raden uppfyller kriterierna för. Om kriterierna inte uppfyller kriterierna är det mer sannolikt att en rad uppfyller kriterierna, så du bör placera mallarna med de mest specifika kriterierna överst i listan. Använd knapparna **Flytta upp** och **Flytta ned** i åtgärdsfönstret om du vill ordna mallarna i listan.
- De åtgärder som vidtas av varje mall. **Påfyllnadsmetoderna** som utför de åtgärder som skapas av mallen, och därigenom skapar eller fördelar arbete för varje typ av påfyllnadsmall.
- De påfyllnadsattribut (filter) som måste gälla för att påfyllnadsmallen ska användas.

> [!NOTE]
> Om det behövs kan en utvecklare skapa ytterligare metoder. Du kan visa den fullständiga listan över metoder på sidan **Metoder för bearbetning av påfyllnad**.

Vissa inställningar representerar strategiska beslut för påfyllnadsbearbetning enligt följande:

- Om mallen används för leverans av artiklar för försäljningsorder och överföringsorder eller används för att flytta artiklar till produktion för produktionsorder eller kanban.
- Om en påfyllnad bearbetas manuellt eller automatiskt, enligt följande:

  - **Manuell bearbetning** – Raden anges till en påfyllnad och lagret reserveras. Du måste emellertid klicka på **Process** i listan **Alla påfyllnader** om du vill skapa plockningsarbetet för ordern.
  - **Automatisk bearbetning** – du kan helt eller delvis automatisera påfyllnadsbearbetningen. Om du helautomatiserar påfyllnadsbearbetningen skapas en påfyllnad som innehåller raden från försäljningsordern, produktionsordern eller kanban när en försäljningsorder, produktionsorder eller kanban skapas. Artiklarna dras av från lagerbehållningen och plockningsarbetet skapas. Om du delvis automatiserar påfyllnadsbearbetning, kan du ange standardvärden som ska utlösa påfyllnadsbearbetning. Du kan till exempel ange en högsta vikt för leveranser som ska utlösa påfyllnadsbearbetning när den totala vikten på raderna i påfyllnaden når värdet.

- Om du tilldelar leveranser till en öppen påfyllnad. Om du till exempel lovar kunder att en order som lagts efter 12:00 ska levereras inom 24 timmar kan du ställa in påfyllnadsmallen för automatisk tilldelning av orderrader till en öppen påfyllnad till 12:00. Vid den tidpunkten bearbetas påfyllnaden automatiskt.

När en påfyllnad bearbetas, baseras plockningsarbete på arbetsmallen och platsdirektivet som anges för lagerstället. Arbetsmallen anger hur plockningsarbetet skapas, och platsdirektivet anger plock- och läggplats.

## <a name="create-a-wave-template"></a>Skapa en påfyllnadsmall

Så här ställer du in en påfyllnadsmall:

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Påfyllnader** \> **Påfyllnadsmallar**.
1. Skapa en ny påfyllnadsmall genom att välja **Nytt**.
1. I fältet **Malltyp för påfyllnad** välj ett av följande alternativ:

    - *Leverans* - Använd påfyllnadsmallen för utleverans av artiklar för försäljningsorder och överföringsorder.
    - *Produktionsorder* - Använd påfyllnadsmallen för att flytta artiklar för produktionsordrar.
    - *Kanban* - Använd påfyllnadsmallen för att flytta artiklar för kanbanordrar.

1. I fälten **Påfyllnadsmallnamn** och **Beskrivning av påfyllnadsmall**, ange ett namn och en beskrivning för påfyllnadsmallen.

    > [!NOTE]
    > Om mer än en mall skapas för ett lagerställe visar antalet i fältet **Påfyllnadsmallsekvens** platsen för mallen i den sekvens i vilken mallar används när mallens villkor uppfylls. Om det behövs kan du välja **Flytta upp** eller **Flytta ned** om du vill ändra mallsekvensen.

1. I fälten **Webbplats** och **Lagerställe** väljer du webbplats och lagerställe som ska påfyllnadsmallen ska skapa påfyllnader och plockarbete för.
1. Om du vill automatisera påfyllnadsbearbetningen gör du följande inställningar efter behov:

    - **Automatisera skapande av påfyllnad** - Ange detta till *Ja* för att automatiskt skapa en våg när en försäljningsorder, produktionsorder eller kanban släpps till lagret.
    - **Tilldela till öppna påfyllnader** - Ange detta till *Ja* för att automatiskt tilldela rader till en öppen påfyllnad när raderna frisläpps. Rader tilldelas påfyllnader baserat på frågefiltret för påfyllnadsmallen.
    - **Bearbeta påfyllnaden vid släpp till lager** - Ange detta *Ja* för att automatiskt bearbeta påfyllnad och skapa arbete när en rad släpps till lagret.
    - **Bearbeta påfyllnad automatiskt vid tröskel** - Ange detta till *Ja* för att automatiskt bearbeta vågen när dess värden når tröskelvärdena för vikt, leverans och rader som anges i fältgruppen **Påfyllnadströskel**. Denna inställning är endast aktiv om *Leverans* har valts i fältet **Påfyllnadsmalltyp**.
    - **Automatisera släpp av påfyllnad** - Ställ in detta till *Ja* om du vill att påfyllnaden ska släppas automatiskt. Plockningsarbetet skapas och görs tillgängligt på mobila enheter.
    - **Automatisera frisläppning av lagerpåfyllnadsarbete** - Ange detta till *Ja* om du vill skapa efterfrågebaserat återanskaffningsarbete och frisläppa det automatiskt. Du måste lägga till påfyllnadsmetoden i påfyllnadsmallen och skapa en återanskaffningsmall av typen *Påfyllnadsefterfrågan*. Ställ in en påfyllnadsmall på sidan för **Återanskaffningmallar**. Detta kräver att du lägger till påfyllnads-metoden i påfyllnadsmallen.
    - **Fortsätt påfyllnadsbearbetningen när skapandet av arbete misslyckas** - När det anges till *Ja*, kommer systemet att använda en tom plats om det inte går att reservera lager på den plats som föreslås i platsdirektivet (t.ex. eftersom lagret inte längre är tillgängligt). När det anges till *Nej*, misslyckas påfyllnaden om systemet inte kan reservera lagret.

1. Ställ in fältgruppen **Påfyllnadströsklar** efter behov:
    - **Påfyllnadsviktens tröskelvärde** - Ange den högsta vikt en påfyllnad kan innehålla.
    - **Leveransgräns** - Ange det maximala antalet leveranser som kan inkluderas i en påfyllnad.
    - **Radgräns** - Ange det maximala antalet rader som kan inkluderas i en påfyllnad.

1. Välj de påfyllnadsattribut som ska användas som ytterligare kriterier för påfyllnadsmallen i fälten **Standardvärden**. Påfyllnadsattribut är användbara för att tilldela ytterligare kriterier, till exempel ett visst kundnamn, till en påfyllnadsmall. Du kan skapa dessa attribut på sidan **Påfyllnadsattribut**. 

1. Ange **Policy påfyllnadsmeddelanden** till den policy som du vill använda för att generera aviseringar relaterade till påfyllnader som använder den här mallen. Ett exempel på en policy påfyllnadsmeddelanden finns i [meddelande om påfyllnadskörning](wave-execution-notifications.md).

1. På snabbfliken **Metoder** visar fönstret **Valda metoder** metoderna för den valda påfyllnadsmallen. Påfyllnadsmetoderna som utför de åtgärder som skapas av mallen, och därigenom skapar eller fördelar arbete. Dessa åtgärder kallas också för påfyllnadsteg. Påfyllnadsmetoder är fördefinierade för varje typ av påfyllnadsmall. Du kan inte ta bort de fördefinierade påfyllnadsmetoderna, men du kan ändra ordning på metoderna och lägga till ytterligare metoder. Om du till exempel skapar en påfyllnadsmall för leverans, kan du lägga till metoder för påfyllnaden och behållarlastningen. Påfyllnad vid skapande av behållare kan läggas till i en sekvens av påfyllnadsmetoder, för att definiera skapandet av behållare, för de rader som bearbetas i en påfyllnadsmall. Gör följande om du vill lägga till ytterligare en metod:

    - Välj metod i fönstret **Återstående metoder** och välj sedan den **vänstra** pilen för att lägga till den i fönstret **Valda metoder**.
    - Välj metod och klicka sedan på **Upp** eller **Ned**-pilarna för att ändra sekvensen.

    > [!NOTE]
    > När du lägger till en metod, anges den automatiskt på rätt plats i sekvensen för steg.

1. Om du vill ställa in frågan som matchar frisläppta rader mot en lämplig påfyllnad väljer du **Redigera fråga** i åtgärdsfönstret.
1. Klicka på **Validera mall** om du vill kontrollera att påfyllnadsmallinställningarna gäller.
