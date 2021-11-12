---
title: Tidsplanering med resursurval baserat på kapacitet
description: Det här ämnet beskriver resursurval vid tidsplanering av obegränsad kapacitet när du anger kapacitet som resursbehov för en operation.
author: ChristianRytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: RouteInventProd, WrkCtrTable, WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 382814eb3d4322ed52bd39fcb22740201335614e
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/25/2021
ms.locfileid: "7679015"
---
# <a name="scheduling-with-resource-selection-based-on-capability"></a>Tidsplanering med resursurval baserat på kapacitet

[!include [banner](../../includes/banner.md)]

Genom att ange resursbehov för en operation i ett produktionsflöde definierar du vad som krävs för att utföra operationen. En operation kanske till exempel kräver en viss resurs eller resursgrupp, eller en kombination av färdigheter eller kapacitet. Det här ämnet beskriver resursurval vid tidsplanering av obegränsad kapacitet när du anger kapacitet som resursbehov för en operation.

## <a name="turn-on-the-capability-based-scheduling-feature"></a>Aktivera funktionen för tidsplanering av kapacitetsbaserad

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *huvudplanering*
- **Funktionsnamn:** *Planering med obegränsad kapacitet för Planeringsoptimering*

Mer information om denna funktion finns i [Tidsplanering med obegränsad kapacitet](infinite-capacity-planning.md).

## <a name="capability-based-scheduling"></a>Kapacitetsbaserad planering

En kapacitet är möjligheten hos en verksamhetsresurs att utföra en viss aktivitet. Mer än en kapacitet kan tilldelas en enda operationsresurs och en enda kapacitet kan tilldelas mer än en resurs. Funktioner kan tilldelas alla typer av resurser, till exempel verktyg, leverantörer, maskiner, platser, anläggningar och personalresurser.

När du anger kapacitet som resursbehov kan du inaktivera resursallokeringen tills order har tidsplanerats. I stället för att tilldela specifika resurser eller resursgrupper till en flödesoperation kan du definiera vilka möjligheter som krävs för varje flödesoperation. Under planeringen matchar sedan systemet den kapacitet som krävs med den kapacitet som har definierats för resurserna. Systemet väljer bara resurser som uppfyller behoven.

Om du vill tilldela funktioner till en operationsresurs använder du snabbflikarna **Funktioner** på sidan **Resurser**. Om du vill tilldela resurser till en funktion använder du **Resurser** på sidan **Resursfunktioner**. Båda sidorna är tillgängliga under **Produktionskontroll \> Inställningar \> Resurser** i navigeringsfönstret. Båda snabbflikarna innehåller ett rutnät med de resurser som har associerats med en vald resurs eller kapacitet. Båda snabbflikarna innehåller även ett verktygsfält som du använder när du vill lägga till, ta bort och redigera rader i rutnätet. Rutnätet innehåller följande kolumner:

- **Resurs** eller **Kapacitet** – Välj den resurs eller kapacitet som tilldelas av raden.
- **Beskrivning** – Ange en kort beskrivning av resursen eller kapaciteten.
- **Gäller från** – Ange det första datumet då resursen eller kapacitetstilldelningen används. Under tidsplaneringen används ingen resurs eller kapacitet som har en förfallen kapacitetstilldelning, även om resursen annars motsvarar behoven.
- **Upphörande** – Ange det sista datumet då resursen eller kapacitetstilldelningen används. Under tidsplaneringen används ingen resurs eller kapacitet som har en förfallen kapacitetstilldelning, även om resursen annars motsvarar behoven.
- **Nivå** – Ange nivån för effektivitet som resursen måste ha för kapaciteten. Om du sedan anger ett värde för **Minimum level needed** för resurs- eller kapacitetskravet, beaktar schemaläggningsmotorn kompetensnivån vid val av resurs Systemet väljer bara de resurser som har behov kapacitet på en nivå som är lika med eller överstiger den miniminivå som anges i resursbehov.
- **Prioritet** – Det här fältet stöds ännu inte av Planeringsoptimering. Om du använder den inbyggda planeringsmotorn kan du emellertid använda fältet **Prioritet** i resursen eller kapacitetstilldelning för att definiera resursprioritet. Om *Prioritet* väljs i fältet **Primärt resursval** på sidan **Planeringsparametrar** välj den resurs som har den högsta prioriteten (det lägsta numeriska värdet i fältet **Prioritet**) först vid planeringen.

## <a name="example"></a>Exempel

Det här exemplet visar hur planeringsmotorn väljer resurser utifrån kapacitet.

Ett produktionsflöde har fem åtgärder: *10*, *20*, *30*, *40* och *50*. Varje flödesoperation kräver en resurs med olika kapacitet. Flödesoperation *10* kräver en resurs som har möjlighet att montera en högtalare(*0050 Spkr sammansättning*) och funktionen träbearbetning (*1010 träfunktioner*). Flödesoperation *50* kräver en resurs som har förmågan att packa en produkt (*0070 förpackningskapaciteten*).

![Kapacitet används för planering.](media/capability-based-scheduling.png "Kapacitet används för planering.")

Under tidsplaneringen söker motor efter resurser som uppfyller operationsbehoven. Till exempel väljer schemaläggningsmotorn resurs *00101* för att utföra åtgärden *10*, eftersom den här resursen är den första resursen som finns som har både de nödvändiga funktionerna. Till exempel väljer schemaläggningsmotorn resurs *00301* för att utföra åtgärden *50*, eftersom den här resursen är förpackningskapaciteten.

Tänk sedan på hur det här exemplet påverkas när kompetensnivåer används:

- Operation *10* kräver en lägsta effektivitetsnivå på *7* för kapaciteten *0059 sammansättning*.
- Resurs *00101* har effektivitetsnivå på *5* för kapacitet *0059 sammansättning*.
- Resurs *00102* har effektivitetsnivå på *10* för kapacitet *0059 sammansättning*.

I det här fallet, under oändlig kapacitetsplanering, väljer schemaläggningsmotorn resurs *00102* för att utföra åtgärden *10*, eftersom denna resurs, till skillnad från resursen *00101*, har den kompetensnivå som krävs för förmågan.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
