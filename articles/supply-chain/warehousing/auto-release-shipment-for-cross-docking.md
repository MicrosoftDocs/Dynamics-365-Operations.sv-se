---
title: Automatisk frisläppning av försändelse för direktutleverans
description: Det här ämnet beskriver en direktutleveransstrategi som gör att du automatiskt kan frisläppa en efterfrågeorder till lagerstället när tillverkningsordern som tillhandahåller efterfrågade kvantiteter rapporteras som färdig, så att kvantiteten flyttas direkt från produktionsutleveransplatsen till den utgående platsen.
author: omulvad
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 849487134969144ec8d3c25023270f7e7a63d470
ms.sourcegitcommit: bc9b65b73bf6443581c2869a9ecfd0675f0be566
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2019
ms.locfileid: "2625886"
---
# <a name="auto-release-shipment-for-cross-docking"></a>Automatisk frisläppning av försändelse för direktutleverans

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver en direktutleveransstrategi som gör att du automatiskt kan frisläppa en efterfrågeorder till lagerstället när tillverkningsordern som tillhandahåller efterfrågekvantiteten rapporteras som färdig. På det här sättet flyttas den kvantitet som krävs för att slutföra efterfrågeorder direkt från produktionsutleveransplatsen till den utgående platsen.

Direktutleverans är ett lagerhanteringsflöde där den kvantitet som krävs för att uppfylla en utgående order dirigeras till orderns utgående docknings- eller mellanlagringsområde från den plats där den inkommande ordern mottogs. (Den inkommande ordern kan vara en inköpsorder, en överföringsorder eller en produktionsorder.) Den avancerade funktionen för direktutleverans stöder alla leverans- och efterfrågeorder och kräver att det utgående efterfrågan frigörs innan affärsmöjligheten för direktutleverans identifieras, har funktionen för automatisk frisläppning av försändelse följande egenskaper:

- Den stöder endast tillverkningsorder som tillgång och bara försäljningsorder och överföringsorder som efterfrågan.
- Direktutleveransåtgärden kan startas även om efterfrågeordern inte frisläpptes till lagret innan leveransens inleverans registrerades (det vill säga innan produktionen rapporterades som färdig).

De här funktionerna för direktutleverans har två fördelar:

- Lageroperationerna kan hoppa över steget med att föra in kvantiteter av färdiga varor i det vanliga lagret, om dessa kvantiteter bara hämtas igen för att genomföra den utgående ordern. I stället kan kvantiteterna flyttas en gång, från utleveransplatsen till en förpacknings-/leveransplats. På så sätt kan funktionen minimera det antal gånger som lagret hanteras och i slutändan maximerar du tid och sparar pengar för lagrets arbetsstyrning.
- Lageråtgärderna kan senarelägga frisläppningen av försäljningsorder och överföringsorder till lagerstället tills produktionen av färdiga varor för den associerade tillverkningsordern rapporteras som färdig. Den här fördelen kan vara särskilt relevant i produktionsmiljöer för tillverka på beställning, där tillverkningstid för produktion brukar vara längre än produktionstiderna i tillverka mot lager-miljöer.

## <a name="prerequisites"></a>Förutsättningar

| Förutsättning | Beskrivning |
|---|---|
| Objekt | Artikeln måste aktiveras för lagerhanteringsprocesser.<p>**Obs!** Artiklar som aktiverats för faktisk/nominell vikt kan inte inkluderas i direktutleveransen.</p> |
| Lagerställe | Lagerstället måste aktiveras för lagerhanteringsprocesser. |
| Mallar för direktleverans | Minst en mall för direktutleverans som använder principen för frisläppning av efterfrågan **Vid leverans av inleverans** måste ställas in för ett visst lagerställe. |
| Arbetsklass | Ett ID för direktutleverans måste skapas för arbetsordertypen **direktleverans**. |
| Arbetsmallar | Du måste använda arbetsmallar för arbetstypen **direktleverans** för att kunna skapa och lägga in arbete för direktleverans. |
| Platsdirektiv | Platsdirektiv för arbetsordertypen **direktleverans** krävs för att vägleda arbetet med de platser där försäljningsorder antalet ska packas och levereras. |
| Markera mellan en efterfrågeorder och en produktionsorder | Lagersystemet kan utlösa automatisk frisläppning av utgående orderförsändelse och skapa direktutleverans från utleveransplats vid åtgärden rapportera som färdig endast om försäljningsorder och överföringsorder har reserverats och markerats mot en tillverkningsorder. |

## <a name="example-cross-docking-flow"></a>Exempel på direktleveransflöde

Ett typiskt direktleveransflöde består av följande huvudsteg.

1. En kundadapter för försäljningsorder skapar en försäljningsorder för en produkt som tillverkas på beställning. Den begärda kvantiteten finns normalt inte i handen och måste först tillverkas.
2. Mottagaren av försäljningsordern skapar en tillverkningsorder direkt från försäljningsorderraden. På det sättet reserverar försäljningsordermottagaren och försäljningsorderkvantiteten markeras mot kvantiteten i tillverkningsordern. 

    Alternativt kan en produktionsplanerare ange att markeringen måste uppdateras när planerade order bekräftas.

3. Produktionsordern går igenom följande steg:

    1. En produktionsplanering uppskattar och släpper produktionsordern. (Uppskattning omfattar råmaterialreservation och frisläppningen inkluderar frisläppning till ett lagerställe.)
    2. Lagerarbetaren startar och slutför råmaterialplockningen från lagringsplatsen till platsen för produktionsinleverans, enligt produktionsplockningsarbetet.
    3. En fabriksoperatör startar tillverkningsordern.
    4. I den senaste operationen använder en maskin operatör den mobila enheten för att rapportera tillverkningsordern som färdig.

4. I systemet används inställningarna för att identifiera direktutleverans för de två kopplade orderna och sedan utföra följande uppgifter:

    1. Automatiskt frisläppa den kopplade försäljningsordern till ett lagerställe för att skapa en leverans.
    2. Skapa automatiskt direktleverans med instruktioner för att plocka de färdiga varorna från utleveransplatsen och flytta dem till den utgående plats som platsdirektiven för direktleverans har tilldelat försäljningsordern.
    3. Uppmana en maskinoperatör att slutföra direktleveransarbetet omedelbart efter det att tillverkningsordern har rapporterats som färdig.

5. När direktleverans är klar och kvantiteterna lastas på fordonet bekräftar en utgående lagerplanering försäljningsförsändelsen.

## <a name="example-scenario"></a>Exempelscenario

För det här scenariet måste du ha demonstrationsdata installerad och du måste använda **USMF**-demodataföretaget.

### <a name="set-up-cross-docking-that-uses-the-auto-release-shipment-feature"></a>Ställ in direktleverans där funktionen för automatisk frisläppning av försändelse används

#### <a name="cross-docking-template"></a>Mall för direktleverans

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Arbete** \> **Arbetsmallar**.
2. Välj **Ny**.
3. I fältet **Sekvensnummer**, ange **1**.
4. I fältet **Mall-ID för direktleverans** ange ett namn, t.ex. **XDock\_RAF**.
5. I fältet **principen för frisläppning av efterfrågan**, välj **Vid leverans av inleverans**.
6. I fältet **Lagerställe**, ange numret på det lagerställe där du vill ställa in processen för direktleverans. Välj **51** i det här exemplet.

    > [!NOTE]
    > Så snart du väljer **Vid leverans av inleverans** som policy för efterfrågan, blir alla andra fält på sidan inte tillgängliga. Du kan inte heller definiera några leveranskällor. Det här problemet beror på att funktionen för direktleverans som använder funktionen för automatisk frisläppning av försändelse bara stöder tillverkningsorder som leveranskällor och den kräver att det finns en markering mellan försäljningsorder och tillverkningsorder. Om du väljer **Innan leverans av inleverans** som frisläppning av efterfråga är fälten på **planering** och **leveranskällor** tillgängliga och kan redigeras.

#### <a name="work-classes"></a>Arbetsklasser

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Arbete** \> **Arbetsklasser**.
2. Välj **Ny**.
3. I fältet **Arbetsklass-ID**, ange ett namn t.ex. **CrossDock**.
4. Välj **Inköpsordertyp** i fältet **Direktleverans**.

Om du vill begränsa vilka typer av platser där direktlevererade färdiga varor kan beställas kan du ange en eller flera giltiga platstyper.

#### <a name="work-templates"></a>Arbetsmallar

1. Gå till to **Lagerstyrning** \> **Inställningar** \> **Arbete** \> **Arbetsmallar**.
2. Välj **Inköpsordertyp** i fältet **Direktleverans**.
3. Välj **Ny**.
4. I fältet **Sekvensnummer**, ange **1**.
5. I fältet **Arbetsmall** ange ett namn t.ex. **CrossDock\_51**.
6. Välj **Spara**.
7. I avsnittet **Arbetsmallinformation** välj **Ny**.
8. För den nya raden, välj **Arbetstyp** och välj **Plocka**. I fältet **Arbetsklass-ID**, välj **CrossDock**.
9. Välj **Ny**.
10. För den nya raden, välj **Arbetstyp** och välj **Placera**. I fältet **Arbetsklass-ID**, välj **CrossDock**.

#### <a name="location-directives"></a>Platsdirektiv

En standardprocess för artikelinförsel för färdiga varor kräver platsdirektivet **Placera** för att vägleda produktionen av plockade produktionskvantiteter till ett vanligt lagringsutrymme. På samma sätt måste du ställa in platsdirektivet direktleverans **Placera**om du vill att jobbet ska ställa in den färdiga kvantiteten på en angiven avgående plats som bevarar försändelsen av den associerade försäljningsordern.

För direktleverans, som för vanlig artikelinförsel av färdiga varor, behöver du inte skapa ett platsdirektiv för åtgärden välj arbetsplats eftersom utleveransplatsen anges. Den här utleveransplatsen förväntas också vara angiven som standardinställd utleveransplats på en av de resursbaserade posterna (dvs. resursen, resursgruppsrelationen eller resursgruppen) eller som en standardplats för produktion av färdiga varor för en lokal.

1. Gå till **Lagerstyrning** \> **Ställ in** \> **Platsdirektiv**.
2. Välj **Inköpsordertyp** i fältet **Direktleverans**.
3. Välj **Ny**.
4. I fältet **Sekvensnummer**, ange **1**.
5. Ange ett **namn** i fältnamn, t.ex. **Baydoor**.
6. Välj **Placera** i fältet **Arbetstyp**.
7. I fltet **Site**, välj **5**.
8. I fältet **Lagerställe**, välj **51**.
9. På snabbfliken **Rader**, välj **Ny**.
10. I fältet **Till kvantitet** anger du den maximala kvantiteten för intervallet, t.ex. **1000000**.
11. Välj **Spara**.
12. På snabbfliken **Platsdirektivåtgärder** välj **Ny**.
13. Ange ett **namn** i fältnamn, t.ex. **Baydoor**.
14. Välj **Spara**.
15. Du kan använda standardfunktionen för frågor om du vill begränsa antalet platser till en eller flera specifika platser. Välj **redigeringsfråga** och välj **51** som kriterium för fältet **lagerställe** i tabellen **platser**.

### <a name="cross-dock-finished-goods-to-the-outbound-location"></a>Direktleverans av färdiga varor till den avgående platsen

Om du vill direktleverera kvantiteten av färdiga varor till den utgående platsen för den associerade försäljningsordern följer du stegen nedan.

1. Gå till **Försäljning och marknadsföring** \> **Försäljningsorder** \> **Alla försäljningsorder**.
2. Välj **Ny**.
3. För försäljningsorderrubriken väljer du kundkonto **US-001** och ett lagerställe som har ställts in för direktleverans och funktionen för automatisk frisläppning av försändelse används.
4. Lägg till en rad för den färdiga produkten och ange **10** som kvantitet.
5. I avsnittet **försäljningsorderrader** väljer du **Produkt och leverans** \>**Produktionsorder**.
6. I dialogrutan **Skapa produktionsorder** granskar du standardvärdena och väljer sedan **Skapa**. En ny tillverkningsorder skapas och länkas till försäljningsordern (dvs. den är reserverad och markerad).
7. Valfritt: ändra värdet i fältet **kvantitet** så att det är mer än det värde som krävs för att uppfylla försäljningsordern. När produktionskvantiteten rapporteras som färdig kommer systemet att skapa direktleverans för den markerade kvantiteten och artikelinförselarbetet för den återstående kvantiteten enligt den vanliga proceduren för hantering av artikelinförsel av färdiga varor.

    Som tidigare nämnts måste det finnas en markering mellan försäljningsordern och tillverkningsordern. I annat fall fungerar inte direktleverans. En markering kan skapas på flera sätt:

    - Systemet kan skapa markeringen automatiskt i följande situationer:

        - Produktionsordern skapas manuellt direkt från försäljningsorderraden (se steg 6).
        - Planerade produktionsorder bestyrks och fältet **Uppdatera markering** anges till **Standard**.

    - Användaren kan skapa markeringen manuellt genom att öppna sidan **markering** från efterfrågeraden.

    > [!NOTE]
    > En markering kan inte skapas manuellt för artiklar som är inställda på att använda standard- och viktat medelvärde som lagermodeller.

8. På sidan **Produktionsorder** i åtgärdsfönstret, på fliken **Produktionsorder** i grupp **Process** välj **Uppskatta** och välj sedan **OK**. Ordern är uppskattad och råmaterialkvantiteten reserveras för produktionen.
9. I åtgärdsfönstret, på fliken **Produktionsorder** i gruppen **Process** välj **Frisläpp** och välj sedan **OK**. Lagerplockningsarbete skapas för råmaterialen.
10. Öppna och granska arbetet. I åtgärdsfönstret, på fliken **Lagerställe**, i gruppen **Allmänt**, väljer du **Arbetsdetaljer**. Gör en notering av arbets-ID.
11. Öppna och logga in på Dynamics 365 for Finance and Operations – appen lagerställe för att köra arbete i lagerställe 51.
12. Gå till **Produktion** \> **Produktionsplockning**.
13. Ange arbets-ID:t för att starta och slutföra plockningen av råmaterial. 

    När arbetet har rapporterats som färdigt är kvantiteten av råmaterial tillgänglig på platsen för produktionsinleverans (**005** i USMF demodata) och körningen av tillverkningsordern kan starta.

14. På sidan **Produktionsorder** i åtgärdsfönstret, på fliken **Produktionsorder** i grupp **Process** välj **Start** och välj sedan **OK**.
15. I appen, gå till **Produktion** \> **RAF och plats**.
16. I fältet **Prod-ID** ange produktionsordernummer och andra obligatoriska detaljer och välj sedan **OK**.

Observera att följande inträffar:

- Frisläppningen till ett lagerställe utlöses för den kopplade försäljningsordern.
- Baserat på frisläppning skapas leverans och direktleverans. Detta arbete instruerar lageroperatören att plocka de kvantiteter som krävs för att uppfylla försäljningsorderraden och placera dem på den utgående plats som har angetts i direktivet för direktleveransplats.
- Om kvantiteten för tillverkningsorder är mer än den kvantitet som krävs för försäljningsordern skapas regelbundet artikelinförselarbete. Detta arbete instruerar lageroperatören att plocka den mängd färdiga varor som återstår efter direktleverans och flytta den till vanlig lagring, enligt det platsdirektiv som används.
