---
title: Strategier för lagerpåfyllnad
description: Det här avsnittet innehåller information om strategier för påfyllning och förklarar hur du kan använda fältet återanskaffningsstrategi på rader för återanskaffning av en påfyllning för att välja hur påfyllning ska göras.
author: mirzaab
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-29
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 84c97bdbe00285d7992a25edbf5d42ffe9b58903
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814522"
---
# <a name="replenishment-strategies"></a>Strategier för lagerpåfyllnad

[!include [banner](../includes/banner.md)]

Mallarna som har definierats på sidan **påfyllnadsmall** inkluderar rader för återanskaffning av en påfyllning som du kan använda för att välja hur påfyllning ska göras. Varje rad innehåller nu ett fält **påfyllningsstrategin**.

Strategin *Fyll på efterfrågekvantitet* är standardstrategin. Det är den strategi för påfyllnad som användes innan införandet av fältet för **påfyllningsstrategin**. Det använder direktiv för återanskaffningsplats för att hitta platser som kan fyllas på. Därefter återförs dessa platser tills efterfrågan täcks.

*Strategin för maximal platskapacitet* introducerar vissa nya funktioner. På samma sätt som strategin *Fyll på efterfrågekvantitet* denna strategi använder direktiv för återanskaffningsplats för att hitta platser som kan fyllas på, och sedan fyller de på dessa platser tills efterfrågan täcks. Det skiljer sig från strategin *Fyll på efterfrågekvantitet* i att alla påfyllningsplatser fylls på med sin max. kapacitet, enligt definitionen i lagerplatsgränsen. *Strategin för maximal platskapacitet* försöker skapa arbete för att ta med den begärda kvantiteten, plus en extra kvantitet, för att fylla de platser som fylls på. I vissa fall kan dock försöket misslyckas. Till exempel kanske det inte finns tillräckligt med lagerplatser för att täcka den extra kvantiteten. I dessa fall upptäcker systemet ett fel och försöker återställa.

Högsäsong är ett exempel på en situation där strategin *maximal platskapacitet* är bättre än strategin för *Fyll på efterfrågekvantitet*. Under högsäsong kan vissa artiklar säljas till en hög volym. Därför kanske du vill att de relevanta plockplatserna måste fyllas i proaktivt så mycket som möjligt för att minska antalet arbets-ID som skapas för påfyllnaden.

> [!IMPORTANT]
> För att helt kunna utnyttja strategin *maximal platskapacitet* måste du omdefiniera lagergränsen för de relevanta platserna. I annat fall fungerar strategin precis som strategin för att *Fyll på efterfrågekvantitet*.

## <a name="turn-on-the-replenish-to-max-based-on-stocking-limits-feature"></a>Aktivera funktionen återanskaffning till max baserat på lagergränser

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *återanskaffning till max baserat på lagergränser*

## <a name="set-up-replenishment-strategies"></a>Ställ in påfyllningsstrategier

För åtkomst till mallarna, gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad**. I avsnittet **Översikt** väljer eller skapar du en mall för lagerpåfyllnadsbegäran där fältet **Lagerpåfyllnadstyp** är inställt på *Lagerpåfyllnad*. Skapa sedan raderna för påfyllningsmallen i avsnittet **Information om mall för lagerpåfyllnad**. För varje rad väljer du den **lagerpåfyllnadsstrategi** som du vill använda i fältet lagerpåfyllnadsstrategi.

![Sidan Mallar för lagerpåfyllnad](media/ReplenTempWaveDmdMaxLocCap.png "Sidan Mallar för lagerpåfyllnad")

Om kolumnen **påfyllningsstrategin** inte visas i rutnätet i avsnittet **Information om mall för lagerpåfyllnad** kontrollerar du att funktionen har aktiverats och att den valda påfyllnadsgrupp har en påfyllningstyp för en *Lagerpåfyllnad*.

> [!NOTE]
> Strategin *Fyll på efterfrågekvantitet* är standardstrategin. Därför behöver du bara uppdatera raderna i lagerpåfyllnadsmallen där du vill använda strategin *maximal platskapacitet* i stället.

## <a name="example-scenarios"></a>Exempelscenarier

### <a name="example-1"></a>Exempel 1

I det här exemplet finns det bara en påfyllnadsgrupp som bara har en rad för påfyllnadsgrupp.

Du skapar en försäljningsorder för 130 stycken (stycken) med artikel A0001. Innan du släpper ordern på lagerstället, ställs lagerstället in på följande sätt:

- Det finns bara en bulkplats och den har 500 datorer av tillgänglig lagerbehållning.
- Det finns tre plockplatser, där var och en har en lagergräns på 100 stycken. (Kom ihåg att lagergränser måste anges för *Maximal strategi för platskapacitet*).
- Påfyllningsplatserna är desamma som platserna för försäljningsplockningen.
- Påfyllningsenheten är en låda (1 låda = 20 stycken).

Vid tidpunkten för ordern finns följande lagerbehållning på försäljningsplockplatserna:

- **Plockning-001:** 20 st (1 låda)
- **Plocka-002:** 0 st
- **Plocka-003:** 0 st

Inledningsvis är en påfyllningsstrategi inställd på *Fyll på efterfrågekvantitet*.

När du släpper upp försäljningsordern på lagerstället och påfyllnadsbearbetning har körts för påfyllnad, får du följande påfyllningsarbete:

- **Påfyllnadsarbete 1:** Välj 4 lådor från bulkplatser och placera dem i plats-001-plock.
- **Påfyllnadsarbete 2:** Välj 2 lådor från bulkplatser och placera dem i plats-002-plock.

Du får två lagerpåfyllnad arbets-ID eftersom du måste fylla på två platser, och flera resurser stöds inte.

Om du ställer in återanskaffningsstrategin till *maximal platskapacitet* i stället, får du följande påfyllningsarbete:

- **Påfyllnadsarbete 1:** Välj 4 lådor från bulkplatser och placera dem i plats-001-plock.
- **Påfyllnadsarbete 2:** Välj 5 lådor från bulkplatser och placera dem i plats-002-plock.

[![Exempel 1](media/ReplenTemp_example_1.png "Exempel 1")](media/ReplenTemp_example_1_large.png)

### <a name="example-2"></a>Exempel 2

Det här exemplet visar vad som händer när en bulkplats inte har tillräckligt med lager för att täcka den extra kvantiteten. Den använder samma scenario som exempel 1, men bulkplatser har 160 datorer (8 lådor).

Strategin *Fyll på efterfrågekvantitet* skapar samma arbete som det gjorde i exempel 1.

Eftersom den *maximala platskapaciteten* försöker skapa arbets-ID som i exempel 1, det kan misslyckas. Vid den punkten försöker systemet återställa.

Beroende på inställningen av alternativet **Tillåt delning** i platsdirektiv för påfyllningsplockning, kan två resultat:

- Om alternativet **Tillåt delning** är inställt på *Ja*, skapas följande påfyllnadsarbete:

    - **Påfyllnadsarbete 1:** Välj 4 lådor från bulkplatser och placera dem i plats-001-plock.
    - **Påfyllnadsarbete 2:** Välj 4 lådor från bulkplatser och placera dem i plats-002-plock.

- Om alternativet **Tillåt delning** är inställt på *Nej*, skapas följande påfyllnadsarbete:

    - **Påfyllnadsarbete 1:** Välj 4 lådor från bulkplatser och placera dem i plats-001-plock.
    - **Påfyllnadsarbete 2:** Välj 2 lådor från bulkplatser och placera dem i plats-002-plock.

Resultaten skiljer sig på grund av den information som är tillgänglig när du skapar arbetet. När alternativet **Tillåt delning** har ställts in på *Ja* i platsdirektiv för påfyllnadsplockning vet du att du har hanterat att hitta 160 st. Därför kan du skapa arbete för kvantiteten. Om alternativet **Tillåt delning** är inställt på *Nej*, vet du dock inte om det finns några 160 st. Eftersom den extra kvantitet som du har valt att fylla på var 3 lådor, släpper du den extra kvantiteten och prova den ursprungliga kvantiteten på nytt.

[![Exempel 2](media/ReplenTemp_example_2.png "Exempel 2")](media/ReplenTemp_example_2_large.png)

Om du vill hämta den maximala kvantiteten till de påfyllningsbara platserna bör du ställa in alternativet **Tillåt delning** på *Ja* i platsdirektiv för påfyllningsplockning.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]