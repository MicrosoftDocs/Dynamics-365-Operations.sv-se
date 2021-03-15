---
title: Lagringsrapport för lagervärde
description: I det här avsnittet beskrivs hur du kör lagringsrapport för lagervärde och gör utdata tillgänglig digitalt, antingen som en interaktiv sida i Microsoft Dynamics 365 Supply Chain Management eller som ett exporterat dokument i ett flertal format.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0f54c02fc828d60f4ddb28be932bbf8eb137ee92
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008195"
---
# <a name="inventory-value-storage-report"></a>Lagringsrapport för lagervärde

I det här avsnittet beskrivs hur du kör **lagringsrapport för lagervärde** och gör utdata tillgänglig digitalt, antingen som en interaktiv sida i Microsoft Dynamics 365 Supply Chain Management eller som ett exporterat dokument i ett flertal format.

När du visar rapporten i din webbläsare, justeras kolumner och aggregerade saldon dynamiskt, beroende på vilken layout som du har konfigurerat. Du kan sortera resultaten, filtrera dem, öka detaljnivån i data och mycket mer.

Rapportresultaten lagras i dataentiteten **lagervärde**. Därför kan du filtrera och exportera resultaten till ett format, t.ex. kommaavgränsade värden (CSV) eller Microsoft Excel-format.

**Lagringsrapport för lagervärde** är användbar när utdata innehåller många rader. Du har till exempel 50 000 artiklar och 300 butiker har skapats som lagerställen. Om du i det här fallet begär lagerslutsaldon per artikel, plats och lagerställe, innehåller utflödet många rader.

> [!NOTE]
> Rapporten innehåller delsummor som definieras i rapportlayouten. Det inkluderar inte heller redovisningssaldon, även om de definieras i rapportlayouten. Du måste göra avstämning till redovisningen med hjälp av råbalansen.

## <a name="turn-on-the-inventory-value-storage-feature"></a>Aktivera funktionen lagring för lagervärde

Innan du kan generera en **Lagringsrapport för lagervärde** måste du aktivera funktionen i systemet. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul** – Kostnadshantering
- **Funktionsnamn** – Aktivera lagring för lagervärde

## <a name="generate-an-inventory-value-storage-report"></a>Generera en lagringsrapport för lagervärde

Följ dessa steg för att skapa och lagra **Lagringsrapport för lagervärde**.

1. Gå till **kostnadshantering \>förfrågningar och rapporter \>Lagring av lagervärderapport**.
1. Välj **Ny**.
1. I dialogrutan **Lagervärde** som visas anger du följande värden för att definiera vilka poster som ska ingå i rapporten:

    - På snabbfliken **Parametrar** ange ett unikt namn för rapporten och använd fälten i avsnittet **Datumintervall** för att definiera vilka poster som ska ingå i rapporten. Om du vill definiera datumintervallet kan du antingen välja ett förinställt intervall (relativt rapportens genereringsdatum) i fältet **datumintervallkod** eller välja särskilda datum i fälten i fälten **Från datum** och **Till datum**.
    - På snabbfliken **Poster som ska ingå** kan du ställa in filter och begränsningar för att definiera vilka data som ska ingå i rapporten.
    - På snabbfliken **kör på snabbfliken bakgrund** anger du hur, när och hur ofta rapporten ska genereras.

    > [!NOTE]
    > Den här rapporten körs alltid som en del av ett batchjobb.

1. Välj **OK** om du vill använda inställningarna och stänga dialogrutan.

Efter att batchjobbet är slutfört kommer rapporten att listas på sidan **Lagring av lagervärderapport**. Du kanske måste uppdatera sidan för att kunna se rapporten.

## <a name="explore-an-inventory-value-storage-report"></a>Utforska en lagringsrapport för lagervärde

När du har genererat en rapport kan du visa och utforska den genom att följa dessa steg.

1. Gå till **kostnadshantering \>förfrågningar och rapporter \>Lagring av lagervärderapport**.
1. Välj en rapport i listan.
1. Välj **Visa information** om du vill visa rapportinnehållet.
1. Granska rapporten på följande sätt:

    - Som för de flesta standardsidor i Supply Chain Management kan du välja nästan vilken kolumnrubrik som helst för att sortera eller filtrera rutnätet efter värdena i den kolumnen.
    - Använd fältet **filter** om du vill filtrera rapporten efter vilket värde som helst i flera tillgängliga kolumner.
    - Använd visa-menyn (ovanför fältet **filter**) för att spara och läsa in dina favoritkombinationer av sorterings- och filteralternativ.

## <a name="export-an-inventory-value-storage-report"></a>Exportera en lagringsrapport för lagervärde

Varje rapport som du skapar lagras i dataenheten **Lagringsrapport**. Du kan använda de standardiserade datahanteringsfunktionerna i Supply Chain Management för att exportera data från den här enheten till alla dataformat som stöds inklusive CSV eller Excel-format.

I följande exempel visas hur du exporterar en **Lagervärderapport**.

1. Gå till **Systemadministration \> Arbetsytor \> Datahantering**.
1. I välj **Import/export**, välj panelen **Export**. 
1. På sidan **export** som visas ska du ställa in exportjobbet. Ange först ett gruppnamn för jobbet.
1. I avsnitt **Vald entiteter**, välj **Lägg till entitet**.
1. Ställ in följande fält i dialogrutan som visas:

    - **Enhetsnamn** – Välj **Lagervärde**.
    - **Måldataformat** – Välj vilket format du vill exportera data till.

1. Välj **Lägg till** för att lägga till den nya raden och välj sedan **Stäng** för att stänga dialogrutan.
1. Vanligtvis exporterar du en rapport i taget. Om du vill exportera en enda rapport skapar du ett filter för den rad som du just har lagt till i dialogrutan **förfrågan**. På det här sättet kan du definiera vilken rapport från enheten **Lagervärde** som ska tas med i exporten. Följ stegen för att ange följande filteralternativ för att exportera en enskild rapport:

    1. På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad.
    2. Ange fältet **Tabell** till **Lagervärde**.
    3. Ange fältet **härlett register** till **Lagervärde**.
    4. Ställ in **fältet** till det fält som du vill filtrera efter. Vanligtvis använder du fältet **körningsnamn** och/eller fältet **körningstid**.
    5. Ställ in fältet **Kriterier** till det värde som du vill söka efter i det valda fältet. (Om du har valt fältet **körningsnamn** i föregående steg är det här värdet som är namnet på rapporten. Om du har valt fältet **körningstid** kommer det att vara den tidpunkt då rapporten genererades.)
    6. Lägg till fler rader till tabellen **Intervall** som du önskar till tills du har identifierat den rapport som du söker efter, om det behövs.

1. Välj **OK** om du vill spara inställningarna och stänga dialogrutan.
1. Välj **Spara** om du vill spara dina exportinställningar.
1. PÅ fliken **exportalternativ** välj **exportera nu** för att generera exportfilen.
1. På sidan **körningssammanfattning** som visas kan du se statusen för exportjobbet och en lista över de enheter som har exporterats. I avsnittet **Bearbetningsstatus för entitet**, välj **Lagervärde** i listan och välj sedan **Hämta fil** för att hämta de data som exporteras från den enheten.

Mer information om hur du använder datahantering för att exportera data finns i [översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]