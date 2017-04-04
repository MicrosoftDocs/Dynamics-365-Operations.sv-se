---
title: "Skapa planer för variabel kompensation"
description: "Variabel kompensation utgör en medarbetares oregelbundna lön såsom bonusar och aktieutdelning. Det här avsnittet beskrivs de komponenter som måste ställas in innan du kan använda variabel kompensation och registrera en medarbetare i en variabel kompensationsplan."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: be156afa73de731e54985485b617bcbae883db3a
ms.lasthandoff: 03/31/2017


---

# <a name="create-variable-compensation-plans"></a>Skapa planer för variabel kompensation

Variabel kompensation utgör en medarbetares oregelbundna lön såsom bonusar och aktieutdelning. Det här avsnittet beskriver komponenterna som måste ställas in innan du kan använda variabel kompensation och anmäla en medarbetare i planen för variabel kompensation.

Beräkningen av belopp i en variabel kompensation för medarbetarna kan baseras på flera faktorer, till exempel medarbetarens resultat, medarbetarens kompensationsnivå och avdelningens prestanda.

## <a name="variable-compensation-components"></a>Komponenter i variabel kompensation
### <a name="create-compensation-types"></a>Skapa kompensationstyper

**Typer för variabel kompensation** är en obligatorisk komponent. Typer av variabel kompensation gör att du kan beskriva typerna av variabel kompensation som din organisation har. De kan göra att du kan ange om kompensationen är kontant eller ett annat format, till exempel aktier.

### <a name="describe-vesting-rules"></a>Beskriv överlåtelseregler

Företag kan ställa in **överlåtelseregler** om de vill. Överlåtelseregler beskriver hur den variabla belöningen ska fördelas över tiden. Till exempel anges en överlåtelseregel som medarbetaren ska få 25 procent av sin totala belöningen varje år under de kommande fyra åren. Överlåtelseregler är bara information.

## <a name="variable-compensation-plans"></a>Planer för variabel kompensation
**Planen för variabel kompensation** innehåller regler, beräkningsmetoder och standardvärden för beräkning av variabel kompensation för medarbetare. När du skapar en variabel kompensationsplan, anger du den variabla kompensationstypen. Den variabla kompensationstypen avgör om systemet beräknar ett valutabelopp eller antalet enheter som en tilldelning. Du måste även ange beräkningsmetoden:

-   **Tidpunkt** – beräkningen av den variabla belöningen baseras på en fast kompensationsplan som medarbetaren hade ett visst datum. Detta datum anges på processhändelsen när nya kompensationsbelopp bearbetas.
-   **Sammansatt** – Ett kompensationsbelopp beräknas för varje unikt lönesats för fast kompensation som medarbetaren hade mellan startdatum och slutdatum i kompensationsperioden för processhändelsen. Andel läggs därefter samman för att fastställa den slutliga belöningen. Under cykeln överförs till exempel en medarbetare till en annan plats som har en annan lönesats. I det här fallet justeras den variabla kompensationen för hur länge medarbetaren hade varje lönesats.

Beloppet för variabel kompensation kan baseras på antingen ett procenttal av medarbetarens det vanliga basinkomster eller ett visst antal enheter.

-   Välj alternativet **Procent av bas** för att ange en standardprocentsats och ange om basen ska vara medarbetarens fasta lönesats eller kontrollpunkten för medarbetarens kompensationsnivå. Kompensationsnivån anges för medarbetarens jobb. En referenspunkterna från kompensationsstrukturen kan anges som kontrollpunkten i den fasta kompensationsplanen. I systemet används kompensationsnivån från medarbetarens jobb och korsrefererar till det. med kontrollpunkten som anges i medarbetarens fasta kompensationsplan till att kontrollen tidpunkt för medarbetarens kompensationsnivå. Hur kontrollen punkt sedan används i stället för medarbetarens fasta lönesats som grund för tilldelning.
-   Välj alternativet **Antal enheter** för att ange ett standardantal enheter, värdet på varje enhet och valutan för enhetsvärdet, om kompensationsplanen gäller ej kontantersättningar (exempelvis 200 enheter av aktier som är värderade till 40 USD), eller bara antalet enheter, om kompensationsplanen gäller kontant ersättning. För en kontantersättning får medarbetaren det angivna antalet enheter av den valuta som används för dennes fasta kompensationsplan (t ex 500 enheter av 1 USD). Kontrollen samarbete kan användas för att ange om en direkt mappning mellan antalet enheter och enhetsvärdet. När du skapar en variabel kompensationsplan för en kontant-baserade plan med antalet enheter inställningen låses automatiskt till **Ja**, och enhetsvärdet är **1,0000**.

Den **anställningsregeln** inställning kan du ange om alla medarbetare ska få samma ökning, oavsett när de anställdes (**anställningsregeln** = **ingen**), eller om medarbetare får en procentandel av belöningen som baseras på längden på sin anställning under cykeln (**anställningsregeln** = **%**). 

**Använda** kan du justera en medarbetares belöning, grundat på prestationerna för medarbetarens avdelning. Resultatmått kan ställas in för varje avdelning på de **avdelningar** sidan under **relaterade formulär**&gt;**kompensation**&gt;**prestanda**. Tilldelning som medarbetare i denna avdelning får beror på värdet av de **procent av uppnått mål** som visar företagets resultat:

-   Om avdelningens resultat är 100 procent, delas ersättningen upp för medarbetare på avdelningen med procenttalet som anges i fältet **Utbetalning vid 100 %**.
-   Om avdelningens resultat är mer än 100 procent, lägger systemet till procenten som anges i fältet **Per 1% över mål** i procenten som anges i fältet **Utbetalning vid 100 %** tills värdet som anges i fältet **Högsta tillåtna utbetalning** uppnås.
-   Om avdelningens resultat är mindre än 100 procent, drar systemet ifrån procenten som anges i fältet **Per 1% under mål** i procenten som anges i fältet **Utbetalning vid 100 %** tills värdet som anges i fältet **Lägsta tillåtna utbetalning** uppnås.

Du kan ange **toleransnivåer** på tröskelprocentsatserna, så att ett varningsmeddelande visas om resultatet leder till att procentsatsen hamnar utanför tröskelprocentsatsen. 

Som standard sker efter den avdelning som anges för medarbetarens befattning. Tilldelning för vissa medarbetare kan dock beroende prestanda för flera avdelningar. I det här fallet kan olika avdelningar och procent av tilldelningen som allokeras till varje avdelning prestanda ställas in på medarbetarens anmälan till variabel kompensation. Mer information finns i avsnittet "anmälan till variabel kompensation" nedan. 

Påverkan användbara om **Resultatlön** har valts när kompensationsprocessen körs. 

Den **nivåer åsidosätter** på fliken kan du åsidosätta belöningen standardprocentsats eller antalet enheter, baserat på medarbetarens kompensationsnivån. Om **åsidosätter aktivera för** anges till **Ja** för medarbetare som deltar i den variabla kompensationsplanen systemet tar nivå från medarbetarens jobb och söker efter det i nivåerna åsidosätter sedan tabellen för att upptäcka procentandelen eller antalet enheter för den nivån. Om nivån inte finns i nivån åsidosätter tabell, standardprocentsats eller antalet enheter från den **allmänna** fliken används. Procent och antal enheter kan också åsidosättas i medarbetarens registrering i variabel kompensationsplan.

## <a name="variable-compensation-enrollment"></a>Anmälan till variabel kompensation
### <a name="determine-who-is-eligible-for-the-plan"></a>Bestäm vem som är berättigad till planen

När du ska anmäla medarbetare till en plan för variabel kompensation är det första steget att bestämma vem som är berättigad till kompensation som definieras i planen. Du kan inte koppla planen till någon medarbetare innan du har bestämt vem som är berättigad till planen. Ställ in kvalifikation genom att öppna sidan **Berättiganderegler**. Här skapar du en ny berättiganderegel för din kompensationsplan och villkor som en medarbetare måste uppfylla för att vara berättigad till en plan. Du kan begränsa berättigandet baserat på avdelning, fackförening, kompensationsregion (plats), jobb, jobbfunktion och/eller kompensationsnivå. Medarbetare kan bara tas med i en kompensationsplan om de uppfyller **alla** kriterier som angetts i berättiganderegeln. 

**Obs!** Berättiganderegler används till planer för både fast och variabel kompensation. Berättiganderegler använder följande fält i posterna för jobb, befattning och anställd för att fastställa om en medarbetare är berättigad till en kompensationsplan.

-   På sidan **Jobb**:
    -   Fältet **Jobb**.
    -   Fälten **Funktion** och **Jobbtyp** på fliken **Jobbklassificering**.
    -   Fältet **Nivå** på fliken **Kompensation**.
-   På sidan **Befattningar**: fälten **Avdelning** och **Kompensationsregion**.
-   I den **medarbetare** sida: information om fackföreningar som associeras med medarbetare under **personuppgifter**&gt;**fackföreningar** på den *** arbetare *** fliken

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Aktivera anmälan till plan för variabel kompensation

På sidan **Planer för variabel kompensation** ställer du in alternativet **Aktivera anmälan** på **Ja** för att tillåta berättigade medarbetare att gå med i planen.

### <a name="enroll-the-employee"></a>Ta med anställd

Nu kan du anmäla medarbetare till planen för variabel kompensation. Gå till sidan **Medarbetare** och välj en medarbetare för att anmäla medarbetaren. I åtgärdsfönstret, klicka på **kompensation**&gt;**registrering i variabel plan**. 

**Obs!** **Anmälning** måste ha värdet **Ja** i planen för variabel kompensation. Den **planera** visar endast de planer som medarbetaren är berättigad för utifrån berättiganderegler som har ställts in för dessa planer. Om en berättiganderegel inte anges för en plan inga anställda inte berättigar till planen. 

Kontrollera att den **giltighetsdatum** ställs in på rätt sätt. Om du använder den variabla kompensationsplanen i **sammansatta** beräkningsmetod, giltighetsdatumet för anmälan kan beaktas vid beräkning av medarbetarens. 

Du kan använda den **åsidosätter** att åsidosätta specifika värden för medarbetaren. Till exempel om **anställningsregeln** anges till **procent** av planen och olika anställningsdatum ska användas vid beräkning av medarbetarens anställningsprocent kan du ange anställningsdatum den **datum för anställningsregel** fält. Kan du även åsidosätta någon i **Belöningsprocenten** värde eller **antal** värdet för en viss medarbetare, beroende på inställningarna för planen. Dessa värden kan fortfarande vägas anställningsregeln och resultatfaktorer och andra inställningar på planen. 

**Åsidosättning av organisationens** för en medarbetares belöning baseras på resultatet för en eller flera avdelningar. Den procentsats som ska fördelas på avdelningar bör uppgå till 100 procent. Medarbetarens enskildes resultat beaktas också. De här inställningarna används bara om **resultatlön** väljs när du kör kompensationsprocessen.

<a name="see-also"></a>Se även
--------

[Kompensationsplaner](compensation-plans.md)


