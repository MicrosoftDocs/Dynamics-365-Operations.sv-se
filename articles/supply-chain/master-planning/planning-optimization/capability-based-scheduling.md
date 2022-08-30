---
title: Tidsplanering med resursurval baserat på kapacitet
description: Denna artikel beskriver resursurval vid tidsplanering av obegränsad kapacitet när du anger kapacitet som resursbehov för en åtgärd.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd, WrkCtrTable, WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4a3c8236183b81ad015b43d7dbf869c177eafd44
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335418"
---
# <a name="scheduling-with-resource-selection-based-on-capability"></a>Tidsplanering med resursurval baserat på kapacitet

[!include [banner](../../includes/banner.md)]

Genom att ange resursbehov för en åtgärd i ett produktionsflöde definierar du vad som krävs för att utföra åtgärden. En åtgärd kanske till exempel kräver en viss resurs eller resursgrupp, eller en kombination av färdigheter eller kapacitet. Denna artikel beskriver resursurval vid tidsplanering av obegränsad kapacitet när du anger kapacitet som resursbehov för en åtgärd.

## <a name="turn-the-capability-based-scheduling-feature-on-or-off"></a>Aktivera eller inaktivera funktionen för tidsplanering av kapacitetsbaserad

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard. Administratörer kan aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Planering av oändlig kapacitet för Planeringsoptimering* i arbetsytan [Funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Mer information om denna funktion finns i [Tidsplanering med obegränsad kapacitet](infinite-capacity-planning.md).

## <a name="capability-based-scheduling"></a>Kapacitetsbaserad planering

En kapacitet är möjligheten hos en verksamhetsresurs att utföra en viss aktivitet. Mer än en kapacitet kan tilldelas en enda åtgärdsresurs och en enda kapacitet kan tilldelas mer än en resurs. Funktioner kan tilldelas alla typer av resurser, till exempel verktyg, leverantörer, maskiner, platser, anläggningar och personalresurser.

När du anger kapacitet som resursbehov kan du inaktivera resursallokeringen tills order har tidsplanerats. I stället för att tilldela specifika resurser eller resursgrupper till en flödesåtgärd kan du definiera vilka möjligheter som krävs för varje flödesåtgärd. Under planeringen matchar sedan systemet den kapacitet som krävs med den kapacitet som har definierats för resurserna. Systemet väljer bara resurser som uppfyller behoven.

Om du vill tilldela funktioner till en åtgärdsresurs använder du snabbflikarna **Funktioner** på sidan **Resurser**. Om du vill tilldela resurser till en funktion använder du **Resurser** på sidan **Resursfunktioner**. Båda sidorna är tillgängliga under **Produktionskontroll \> Inställningar \> Resurser** i navigeringsfönstret. Båda snabbflikarna innehåller ett rutnät med de resurser som har associerats med en vald resurs eller kapacitet. Båda snabbflikarna innehåller även ett verktygsfält som du använder när du vill lägga till, ta bort och redigera rader i rutnätet. Rutnätet innehåller följande kolumner:

- **Resurs** eller **Kapacitet** – Välj den resurs eller kapacitet som tilldelas av raden.
- **Beskrivning** – Ange en kort beskrivning av resursen eller kapaciteten.
- **Gäller från** – Ange det första datumet då resursen eller kapacitetstilldelningen används. Under tidsplaneringen används ingen resurs eller kapacitet som har en förfallen kapacitetstilldelning, även om resursen annars motsvarar behoven.
- **Upphörande** – Ange det sista datumet då resursen eller kapacitetstilldelningen används. Under tidsplaneringen används ingen resurs eller kapacitet som har en förfallen kapacitetstilldelning, även om resursen annars motsvarar behoven.
- **Nivå** – Ange nivån för effektivitet som resursen måste ha för kapaciteten. Om du sedan anger ett värde för **Minimum level needed** för resurs- eller kapacitetskravet, beaktar schemaläggningsmotorn kompetensnivån vid val av resurs Systemet väljer bara de resurser som har behov kapacitet på en nivå som är lika med eller överstiger den miniminivå som anges i resursbehov.
- **Prioritet** – Det här fältet stöds ännu inte av Planeringsoptimering. Om du använder den inbyggda planeringsmotorn kan du emellertid använda fältet **Prioritet** i resursen eller kapacitetstilldelning för att definiera resursprioritet. Om *Prioritet* väljs i fältet **Primärt resursval** på sidan **Planeringsparametrar** välj den resurs som har den högsta prioriteten (det lägsta numeriska värdet i fältet **Prioritet**) först vid planeringen.

## <a name="example"></a>Exempel

Det här exemplet visar hur planeringsmotorn väljer resurser utifrån kapacitet.

Ett produktionsflöde har fem åtgärder: *10*, *20*, *30*, *40* och *50*. Varje flödesåtgärd kräver en resurs med olika kapacitet. Flödesåtgärd *10* kräver en resurs som har möjlighet att montera en högtalare(*0050 Spkr sammansättning*) och funktionen träbearbetning (*1010 träfunktioner*). Flödesåtgärd *50* kräver en resurs som har förmågan att packa en produkt (*0070 förpackningskapaciteten*).

![Kapacitet används för planering.](media/capability-based-scheduling.png "Kapacitet används för planering.")

Under tidsplaneringen söker motor efter resurser som uppfyller åtgärdsbehoven. Till exempel väljer schemaläggningsmotorn resurs *00101* för att utföra åtgärden *10*, eftersom den här resursen är den första resursen som finns som har både de nödvändiga funktionerna. Till exempel väljer schemaläggningsmotorn resurs *00301* för att utföra åtgärden *50*, eftersom den här resursen är förpackningskapaciteten.

Tänk sedan på hur det här exemplet påverkas när kompetensnivåer används:

- Åtgärd *10* kräver en lägsta effektivitetsnivå på *7* för kapaciteten *0059 sammansättning*.
- Resurs *00101* har effektivitetsnivå på *5* för kapacitet *0059 sammansättning*.
- Resurs *00102* har effektivitetsnivå på *10* för kapacitet *0059 sammansättning*.

I det här fallet, under oändlig kapacitetsplanering, väljer schemaläggningsmotorn resurs *00102* för att utföra åtgärden *10*, eftersom denna resurs, till skillnad från resursen *00101*, har den kompetensnivå som krävs för förmågan.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
