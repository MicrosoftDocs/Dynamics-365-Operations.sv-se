---
title: Begränsad kapacitetsplanering och tidsplanering
description: Begränsad kapacitetsplanering och planering hjälper dig att förstå hur mycket arbete som kan produceras under en viss period när begränsningar i olika resurser beaktas.
author: t-benebo
ms.date: 09/19/2022
ms.topic: article
ms.search.form: ReqParameters, ReqPlanSched, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-19
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 5f02ec58c88cfd0d663a97de4e3e4dff1cdd5e90
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740097"
---
# <a name="finite-capacity-planning-and-scheduling"></a>Begränsad kapacitetsplanering och tidsplanering

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!--KFM: Preview until 10.0.31 GA -->

Begränsad kapacitet är en metod som hjälper dig att förstå hur mycket arbete som kan produceras under en viss period när begränsningar i olika resurser beaktas. Syftet med begränsad kapacitetsplanering kapacitet är att se till att arbetet fortsätter vid en jämnare och effektiv arbetsplanering i hela fabriksanläggning.

Begränsad kapacitetsplanering och tidsplanering skapar en mer realistisk plan för produktionsprocesserna än den obegränsade inläsningsmetod som skapas. Om det inte finns tillräcklig kapacitet för resurserna leveransdatum kommer att skjutas ut och jobbet kommer att schemaläggas när det finns tillräckligt med kapacitet.

> [!NOTE]
> Begränsad kapacitetsplanering och planering fungerar nästan på samma sätt, oavsett om du använder Planeringsoptimering eller den inaktuella huvudplaneringsmotorn. Vid planeringsoptimering används dock inte parametern **Flaskhalstidsgräns**. När du använder Planeringsoptimering planeras alltid flaskhalsar med samma tidsgräns som resurser som inte anges vara flaskhalsresurser (vilket anges av tidsgränsen för begränsad kapacitet).

## <a name="set-up-finite-capacity-functionality"></a>Ställa in funktionen för begränsad kapacitet

Om du vill använda funktionen för begränsad kapacitet måste du aktivera kapacitetsplanering globalt och du måste aktivera begränsad kapacitetsplanering både för den huvudplan där den ska användas och för varje resurs där den används. För planer och resurser där begränsad kapacitet är aktiverad kommer tidsplaneringen av planerade produktionsorder att beakta kapacitet som redan har reserverats. Planerade produktionsorder tidsplaneras bakåt från behovsdatum. Om kapacitet inte är tillgänglig för att uppnå det optimala schemat försöker systemet att kräva komponentartiklar på ett tidigare datum. Om din kapacitet kan ändras när kraven ändras (till exempel när du arbetar med skift), bör du inte använda funktionen begränsad kapacitet eftersom de beräknade handläggningstiderna inte blir korrekta. Schemaläggning tar endast hänsyn till kapacitet som redan är reserverad för resurser där begränsad kapacitet är aktiverad. Genom att aktivera begränsad kapacitet för en resurs kan du ändra tidsgränsen för ändlig kapacitet.

### <a name="activate-master-planning-parameters"></a>Aktivera huvudplaneringsparametrar

Om du vill använda funktionen för begränsad kapacitet måste du aktivera kapacitetsplanering på sidan **Parametrar för huvudplanering**.

1. Gå till **Huvudplanering \> Inställningar \> Huvudplaneringsparametrar**.
1. På fliken **Planerade order** i avsnittet **Kapacitetsplanering**, ställ in alternativet **Produktion** på *Ja*.

### <a name="activate-a-master-plan"></a>Aktivera en huvudplan

Du måste aktivera begränsad kapacitetsplanering och planering för varje huvudplan där du vill använda den.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj i listfönstret en huvudplan som du vill ställa in för att använda begränsad kapacitetsplanering och planering.
1. På snabbfliken **Allmänt** i avsnittet **Planerade produktionsorder** ange alternativet **Begränsad kapacitet** till *Ja*.
1. Upprepa steg 2 och 3 för varje ytterligare huvudplan där du vill konfigurera.

### <a name="activate-resources"></a>Aktivera resurser

Du måste aktivera begränsad kapacitetsplanering och planering för varje resurs där du vill använda den.

1. Gå till **Produktionsstyrning \> Inställningar \> Resurser \> Resurser**.
1. Välj i listfönstret en resurs som du vill ställa in för att använda begränsad kapacitetsplanering och planering.
1. På snabbfliken **Åtgärd** i knappen **Kapacitet** anger du alternativet **Begränsad kapacitet** till *Ja*.
1. Upprepa steg 2 och 3 för varje ytterligare resurs där du vill konfigurera.

## <a name="examples"></a>Exempel

Det här avsnittet innehåller följande exempel som visar hur du arbetar med både obegränsad och begränsad kapacitetsplanering och schemaläggning:

- Exempel 1 – Obegränsad kapacitetsplanering
- Exempel 2 – Begränsad kapacitetsplanering med en tidsgräns på en dag
- Exempel 3 – Begränsad kapacitetsplanering med en tidsgräns på två dagar

### <a name="preconditions"></a>Förvillkor

I alla tre exempel förutsätts förutsättningarna som beskrivs i det här avsnittet.

Produkt *Produkt1* har ett flöde som innehåller följande operationer.

| Operation nr. | Operationsnamn | Resurs        | Körtid | Processkvantitet | Nästa |
|---------------|----------------|-----------------|----------|--------------|------|
| 10            | Svetsning        | Svetsrad    | 1        | 2            | 20   |
| 20            | Sammansätter     | Monteringsrad | 1        | 4            |      |

Medarbetare på företaget arbetar i ett skift i åtta timmar (8:00 –16:00).

Det finns en tidsplanerad tillverkningsorder för *24 st* av *Produkt1*. Den har ett leveransdatum på *Idag + 3 dagar*.

Efter planeringen läser systemet in resurserna på följande sätt:

- **Svetsrad:** Den här resursen laddas från *Idag kl. 8:00* till *Idag + 1 kl. 12:00*.
- **Monteringsrad:** Den här resursen laddas från *Idag + 1 kl 12:00* till *Idag + 2 kl. 10:00*.

I följande bild visas det resulterande Gantt-diagrammet (du väljer det för en större vy).

[![Gantt-diagram som visar förutsättningar.](media/finite-examples-conditions-small.png "Gantt-diagram som visar förutsättningar")](media/finite-examples-conditions.png)

### <a name="example-1--infinite-capacity-planning"></a>Exempel 1 – Obegränsad kapacitetsplanering

Det här exemplet visar planeringsresultaten när du använder obegränsad kapacitetsplanering i stället för begränsad kapacitetsplanering.

Huvudplanen har följande relevanta inställningar, vilket inaktiverar begränsad kapacitetsplanering för planen:

- **Begränsad kapacitet:** *Nr*

Alternativet **Begränsad kapacitet** ställs också in på *Nej* för båda relevanta resurser när du vill inaktivera begränsad kapacitetsplanering för dem:

- Svetsrad
- Monteringsrad

Du lägger nu till en ny försäljningsorder för *8 st* av *Product1* och kör planen. Det innebär att systemet läser in raden från *idag klockan 8:00* till *idag klockan 12:00*. När operationerna på svetsraden har slutförts läser systemet in monteringsraden från *idag klockan 12:00* till *idag klockan 14:00*.

I följande bild visas det resulterande Gantt-diagrammet (du väljer det för en större vy).

[![Gantt-diagram som visar ett exempel på begränsad kapacitetsplanering.](media/finite-examples-example1-small.png "Gantt-diagram som visar ett exempel på begränsad kapacitetsplanering")](media/finite-examples-example1.png)

### <a name="example-2--finite-capacity-planning-with-a-time-fence-of-one-day"></a>Exempel 2 – Begränsad kapacitetsplanering med en tidsgräns på en dag

Det här exemplet visar planeringsresultaten när du använder begränsad kapacitetsplanering och tidsgräns på en dag.

Huvudplanen har följande relevanta inställningar, vilket aktiverar begränsad kapacitetsplanering och ställer in en tidsgräns för planen:

- **Begränsad kapacitet:** *Ja*
- **Tidsgräns för begränsad kapacitet:** *1*

Alternativet **Begränsad kapacitet** ställs också in på *Ja* för båda relevanta resurser när du vill aktivera begränsad kapacitetsplanering för dem:

- Svetsrad
- Monteringsrad

Du lägger nu till en ny försäljningsorder för *8 st* av *Product1* och kör planen. Det innebär att systemet läser in raden från *idag + 1 klockan 8:00* till *idag + 1 klockan 12:00*. När operationerna på svetslinjen har slutförts läser systemet in monteringslinjen från *idag + 1 klockan 12:00* till *klockan idag + 1 14:00*. Systemet tar bara hänsyn till den begränsade kapaciteten under en dag.

I följande bild visas det resulterande Gantt-diagrammet (du väljer det för en större vy).

[![Gantt-diagram som visar begränsad kapacitetsplanering med en tidsgräns på en dag.](media/finite-examples-example2-small.png "Gantt-diagram som visar begränsad kapacitetsplanering med en tidsgräns på en dag")](media/finite-examples-example2.png)

### <a name="example-3--finite-capacity-planning-with-a-time-fence-of-two-days"></a>Exempel 3 – Begränsad kapacitetsplanering med en tidsgräns på två dagar

Det här exemplet visar planeringsresultaten när du använder begränsad kapacitetsplanering och tidsgräns på två dagar.

Huvudplanen har följande relevanta inställningar, vilket aktiverar begränsad kapacitetsplanering och ställer in en tidsgräns för planen:

- **Begränsad kapacitet:** *Ja*
- **Tidsgräns för begränsad kapacitet:** *2*

Alternativet **Begränsad kapacitet** ställs också in på *Ja* för båda relevanta resurser när du vill aktivera begränsad kapacitetsplanering för dem:

- Svetsrad
- Monteringsrad

Du lägger nu till en ny försäljningsorder för *8 st* av *Product1* och kör planen. Det innebär att systemet läser in raden från *idag + 1 klockan 12:00* till *idag + 1 klockan 16:00*. När operationerna på svetslinjen har slutförts läser systemet in monteringslinjen från *idag + 2 klockan 8:00* till *klockan idag + 2 10:00*. Systemet tar bara hänsyn till den begränsade kapaciteten under två dagar.

I följande bild visas det resulterande Gantt-diagrammet (du väljer det för en större vy).

[![Gantt-diagram som visar begränsad kapacitetsplanering med en tidsgräns för två dagar.](media/finite-examples-example3-small.png "Gantt-diagram som visar begränsad kapacitetsplanering med en tidsgräns för två dagar")](media/finite-examples-example3.png)

> [!IMPORTANT]
> Du bör alltid ställa in tidsgränsen för begränsad kapacitet efter behov. De exempel som ges i den här artikeln illustrerar bara funktionerna. I praktiken är en engångstidsgräns troligen för låg för de flesta tillverkare som använder begränsad kapacitetsplanering.
