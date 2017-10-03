---
title: "Skapa planer för variabel kompensation"
description: "Variabel kompensation utgör en medarbetares oregelbundna lön såsom bonusar och aktieutdelning. Det här avsnittet beskriver komponenterna som måste ställas in innan du kan använda variabel kompensation och registrera en medarbetare i en plan för variabel kompensation."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 26ed9de01bffbcd468ac0cf1b9eb3f101707eb04
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="create-variable-compensation-plans"></a>Skapa planer för variabel kompensation

[!include[banner](includes/banner.md)]


Variabel kompensation utgör en medarbetares oregelbundna lön såsom bonusar och aktieutdelning. Det här avsnittet beskriver komponenterna som måste ställas in innan du kan använda variabel kompensation och anmäla en medarbetare i planen för variabel kompensation.

Beräkningen av belopp i en variabel kompensation för medarbetarna kan baseras på flera faktorer, till exempel medarbetarens resultat, medarbetarens kompensationsnivå och avdelningens prestanda.

## <a name="variable-compensation-components"></a>Komponenter i variabel kompensation
### <a name="create-compensation-types"></a>Skapa kompensationstyper

**Typer för variabel kompensation** är en obligatorisk komponent. Typer av variabel kompensation gör att du kan beskriva typerna av variabel kompensation som din organisation har. De kan göra att du kan ange om kompensationen är kontant eller ett annat format, till exempel aktier.

### <a name="describe-vesting-rules"></a>Beskriv överlåtelseregler

Företag kan ställa in **överlåtelseregler** om de vill. Överlåtelseregler beskriver hur den variabla belöningen ska fördelas över tid. En överlåtelseregel kan exempelvis ange att medarbetaren ska få 25 procent av sin totala belöning varje år under de kommande fyra åren. Överlåtelseregler utgör ren information.

## <a name="variable-compensation-plans"></a>Planer för variabel kompensation
**Planen för variabel kompensation** innehåller regler, beräkningsmetoder och standardvärden för beräkning av variabel kompensation för medarbetare. När du skapar en variabel kompensationsplan anger du den variabla kompensationstypen. Den variabla kompensationstypen avgör om systemet beräknar ett valutabelopp eller antalet enheter som belöning. Du måste även ange beräkningsmetoden:

-   **Tidpunkt** – Beräkningen av den variabla belöningen baseras på den fasta kompensationsplan som medarbetaren hade ett visst datum. Detta datum anges för den processhändelse när nya kompensationsbelopp bearbetas.
-   **Sammansatt** – Ett kompensationsbelopp beräknas för varje unikt lönesats för fast kompensation som medarbetaren hade mellan startdatum och slutdatum i kompensationsperioden för processhändelsen. Tarifferna läggs därefter samman för att fastställa den slutliga belöningen. Under cykeln överförs till exempel en medarbetare till en annan befattning med en annan lönesats. I det här fallet justeras den variabla kompensationen för hur länge medarbetaren hade varje lönesats.

Beloppet för variabel kompensation kan baseras på antingen ett procenttal av medarbetarens det vanliga basinkomster eller ett visst antal enheter.

-   Välj alternativet **Procent av bas** för att ange en standardprocentsats och ange om basen ska vara medarbetarens fasta lönesats eller kontrollpunkten för medarbetarens kompensationsnivå. Kompensationsnivån anges för medarbetarens jobb. En av referenspunkterna från kompensationsstrukturen kan anges som kontrollpunkten i den fasta kompensationsplanen. Systemet använder kompensationsnivån från medarbetarens jobb och korsrefererar till denna med den kontrollpunkt som anges i medarbetarens fasta kompensationsplan för att hitta kontrollpunktsbeloppet för medarbetarens kompensationsnivå. Kontrollpunkten används sedan i stället för medarbetarens fasta lönesats som grund för belöningen.
-   Välj alternativet **Antal enheter** för att ange ett standardantal enheter, värdet på varje enhet och valutan för enhetsvärdet, om kompensationsplanen gäller ej kontantersättningar (exempelvis 200 enheter av aktier som är värderade till 40 USD), eller bara antalet enheter, om kompensationsplanen gäller kontant ersättning. För en kontantersättning får medarbetaren det angivna antalet enheter i den valuta som används för dennes fasta kompensationsplan (t.ex. 500 enheter av 1 USD). Relationskontrollen en-mot-en kan användas för att ange om en direkt mappning en-mot-en mellan antalet enheter och enhetsvärdet. När du skapar en variabel kompensationsplan för en kontantbaserad plan genom att använda antalet enheter, låses denna inställningen automatiskt som **Ja**, och enhetsvärdet är **1,0000**.

Inställningen **Anställningsregel** gör att du kan ange om alla medarbetare ska få samma ökning, oavsett det datum då de anställdes (**Anställningsregel** = **Ingen**), eller huruvida medarbetare ska få en procentandel av ökningen, som baseras på hur länge han eller hon har varit anställd under cykeln (**Anställningsregel** = **Procent**). 

**Påverka** låter dig justera en medarbetares belöning, baserat på resultaten för medarbetarens avdelning. Resultatmått kan ställas in för varje avdelning på sidan **Avdelningar** under **Relaterade formulär** &gt; **Kompensation** &gt; **Resultat**. Den belöning som medarbetare på denna avdelning får beror på värdet i fältet **Procent av uppnått mål**, som visar företagets resultat:

-   Om avdelningens resultat är 100 procent, delas ersättningen upp för medarbetare på avdelningen med procenttalet som anges i fältet **Utbetalning vid 100 %**.
-   Om avdelningens resultat är mer än 100 procent, lägger systemet till procenten som anges i fältet **Per 1% över mål** i procenten som anges i fältet **Utbetalning vid 100 %** tills värdet som anges i fältet **Högsta tillåtna utbetalning** uppnås.
-   Om avdelningens resultat är mindre än 100 procent, drar systemet ifrån procenten som anges i fältet **Per 1% under mål** i procenten som anges i fältet **Utbetalning vid 100 %** tills värdet som anges i fältet **Lägsta tillåtna utbetalning** uppnås.

Du kan ange **toleransnivåer** på tröskelprocentsatserna, så att ett varningsmeddelande visas om resultatet leder till att procentsatsen hamnar utanför tröskelprocentsatsen. 

Som standard söker systemet efter den avdelning som anges för medarbetarens befattning. Belöningen för vissa medarbetare kan dock vila på resultatet för flera avdelningar. I det här fallet kan de olika avdelningar och den procentsats av belöningen som tilldelas resultaten för respektive avdelning anges i medarbetarens variabla kompensationsregistrering. Mer information finns i avsnittet "Variabel kompensationsregistrering" nedan. 

Påverkan användbara om **Resultatlön** har valts när kompensationsprocessen körs. 

Fliken **Nivååsidosättning** låter dig du åsidosätta belöningens standardprocentsats eller antalet enheter, baserat på medarbetarens kompensationsnivå. Om **Aktivera åsidosättning för nivå** anges som **Ja** för medarbetare som deltar i den variabla kompensationsplanen, hämtar systemet nivån från medarbetarens jobb och söker sedan efter den i tabellen för nivååsidosättning för att avläsa procentandel eller antal enheter för den nivån. Om nivån inte finns i tabellen för nivååsidosättning, kommer standardprocentsats eller antal enheter i fliken **Allmänt** att användas. Procentandelen och antal enheter kan också åsidosättas i medarbetarens registrering i den variabla kompensationsplanen.

## <a name="variable-compensation-enrollment"></a>Anmälan till variabel kompensation
### <a name="determine-who-is-eligible-for-the-plan"></a>Bestäm vem som är berättigad till planen

När du ska anmäla medarbetare till en plan för variabel kompensation är det första steget att bestämma vem som är berättigad till kompensation som definieras i planen. Du kan inte koppla planen till någon medarbetare innan du har bestämt vem som är berättigad till planen. Ställ in kvalifikation genom att öppna sidan **Berättiganderegler**. Här skapar du en ny berättiganderegel för din kompensationsplan och villkor som en medarbetare måste uppfylla för att vara berättigad till en plan. Du kan begränsa berättigandet baserat på avdelning, fackförening, kompensationsregion (plats), jobb, jobbfunktion och/eller kompensationsnivå. Medarbetare kan bara tas med i en kompensationsplan om de uppfyller **alla** kriterier som angetts i berättiganderegeln. 

**Obs!** Berättiganderegler används till planer för både fast och variabel kompensation. Berättiganderegler använder följande fält i posterna för jobb, befattning och anställd för att fastställa om en medarbetare är berättigad till en kompensationsplan.

-   På sidan **Jobb**:
    -   Fältet **Jobb**.
    -   Fälten **Funktion** och **Jobbtyp** på fliken **Jobbklassificering**.
    -   Fältet **Nivå** på fliken **Kompensation**.
-   På sidan **Befattningar**: fälten **Avdelning** och **Kompensationsregion**.
-   På sidan **Medarbetare**: Informationen om fackföreningar som är associerad med medarbetaren **Personlig information** &gt; **Fackföreningar** på fliken ****Medarbetare****.

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Aktivera anmälan till plan för variabel kompensation

På sidan **Planer för variabel kompensation** ställer du in alternativet **Aktivera anmälan** på **Ja** för att tillåta berättigade medarbetare att gå med i planen.

### <a name="enroll-the-employee"></a>Ta med anställd

Nu kan du anmäla medarbetare till planen för variabel kompensation. Gå till sidan **Medarbetare** och välj en medarbetare för att anmäla medarbetaren. Klicka sedan på **Kompensation** &gt; **Variabel planregistrering** i åtgärdsfönstret. 

**Obs!** **Anmälning** måste ha värdet **Ja** i planen för variabel kompensation. Fältet **Plan** visar endast planer som medarbetaren är berättigad till, baserat på de berättiganderegler som skapats för dessa planer. Om ingen berättiganderegel har ställts in för en plan, har ingen medarbetare rätt till planen. 

Kontrollera att fältet **Giltighetsdatum** ställs in på rätt sätt. Om planen för variabel kompensation använder beräkningsmetoden **Sammansatt**, kan giltighetsdatumet för registreringen användas under beräkningen av en medarbetares belöning. 

Du kan använda fliken **Åsidosättning** för att åsidosätta specifika värden för medarbetaren. Om till exempel **Anställningsregel** anges som **Procent** på planen och olika anställningsdatum ska användas vid beräkningen av medarbetarens anställningsprocent, kan du ange anställningsdatum i fältet **Datum för anställningsregel**. Kan du även åsidosätta antingen värdet **Belöningsprocent** eller värdet **Antal enheter** för en viss medarbetare, beroende på inställningarna för planen. Dessa värden kan fortfarande påverkas av anställningsregeln, resultatfaktorer och andra inställningar för planen. 

**Åsidosättningar inom organisationen** används för att basera en medarbetares belöning på resultatet för en eller flera avdelningar. Den procentsats som ska fördelas på avdelningarna bör uppgå till 100 procent. Medarbetarens enskilda resultat beaktas också. Dessa inställningar används bara om **Resultatlön** har valts när kompensationsprocessen körs.

<a name="see-also"></a>Se även
--------

[Kompensationsplaner](compensation-plans.md)




