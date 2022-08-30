---
title: Rapporten jämföra lager för artikelpriser
description: Läs mer om hur du genererar en rapport över jämför artikelpriser och sedan bläddrar och/eller exporterar resultatet.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c6373679299b68413d75236ca8cc18ceba03e091
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334998"
---
# <a name="compare-item-prices-storage-report"></a>Rapporten jämföra lager för artikelpriser

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du kör rapporten **Jämföra lager för artikelpriser** och gör utdata tillgänglig digitalt, antingen som en interaktiv sida i Dynamics 365 Supply Chain Management, eller som ett exporterat dokument i ett flertal format.

När du visar rapporten i din webbläsare, justeras kolumner och aggregerade saldon dynamiskt, beroende på vilken layout som har konfigurerats. Du kan sortera resultaten, filtrera dem, öka detaljnivån i data och mycket mer.

Rapportresultaten lagras i dataentiteten **jämför artikelpriser**, vilket gör att du kan filtrera och exportera resultaten till ett format som t.ex. CSV eller Microsoft Excel.

Rapporten **jämföra lager för artikelpriser** är användbar när utdata innehåller många rader. Till exempel kommer utdata att innehålla många rader om du har mer än 40 000 artiklar som innehåller ett väntande artikelpris i kostnadsversionen.

## <a name="turn-the-compare-item-prices-storage-feature-on-or-off"></a>Aktivera eller inaktivera funktionen Jämför artikelpriser

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.29 version av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.29 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Jämför lager för artikelpriser* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="generate-a-compare-item-prices-storage-report"></a>Generera en rapport för jämföra lager för artikelpriser

Följ dessa steg för att skapa och lagra rapporten **jämföra lager för artikelpriser**:

1. Gå till **Kostnadshanterings > Förfrågningar och rapporter > Förutbestämda kostnadsrapporter > Jämföra lager för artikelpriser**.

1. Välj **Ny** om du vill öppna fönstret **jämför artikelpriser**. Ange följande alternativ för att definiera vilka priser som ska jämföras i rapporten:

    - På snabbfliken **parametrar** ger du rapporten ett unikt **namn** och använder fälten i **Väntande priser som ska jämföras** och **Priser som används för jämförelsen** för att definiera vilka priser och datum som ska jämföras.
    - På snabbfliken **Poster som ska ingå** kan du konfigurera filter och begränsningar för att definiera vilka data som ska ingå i rapporten.
    - På snabbfliken **kör i bakgrund** ställer du in hur, när och hur ofta du vill generera rapporten.
    > [!NOTE]
    > Den här rapporten körs alltid som en del av ett batchjobb.

1. Välj **OK** om du vill använda inställningarna och stänga fönstret.

1. När batchjobbet är klart visas det på sidan **jämföra lager för artikelpriser**. Du kanske måste uppdatera sidan om du vill visa rapporten.

## <a name="explore-the-compare-item-prices-storage-report"></a>Utforska en rapport för jämföra lager för artikelpriser

När du har genererat en rapport kan du visa och utforska den när som helst enligt följande:

1. Gå till **Kostnadshanterings > Förfrågningar och rapporter > Förutbestämda kostnadsrapporter > Jämföra lager för artikelpriser**.

1. Välj en rapport i listan.

1. Gör något av följande:

    - Välj **översikt** om du vill få en översikt över dina rapportresultat.
    - Välj **Visa information** om du vill få en mer detaljerad översikt över din rapport

1. När den valda vyn öppnas kan du göra följande:

    - Välj nästan alla kolumnrubriker om du vill sortera eller filtrera tabellen efter värden i den kolumnen, på samma sätt som i de flesta standardformulär i Supply Chain Management. Observera att du inte kan sortera eller filtrera kolumnen **nettoändringspris %** eftersom det är ett beräknat fält.
    - Välj **dimensionsvisning** om du vill öppna en ruta där du kan välja vilken dimensionskolumn som ska inkluderas i formuläret. Ange **Spara inställning** till **Ja** om du vill spara inställningarna så att de bevaras nästa gång du öppnar rapporten. Välj **OK** om du vill använda inställningarna och stänga.
    - Markera en rad i formuläret och välj sedan **Visa information** om du vill visa mer information om den valda artikeln. Du kan gå nedåt i informationen härifrån.
    - Markera en rad i formuläret och välj sedan **Visa jämförelsediagram** för att se en interaktiv grafisk representation av resultaten som de är relaterade till den valda artikeln. Du kan utforska dessa resultat genom att välja olika grafiska element i diagrammet och diagramförklaringen.
    - Markera en rad i formuläret och välj sedan **Visa beräkningsinformation** om du vill visa mer information beräkningar relaterade till den valda artikeln. Du kan gå nedåt i informationen härifrån.

## <a name="export-the-compare-item-prices-storage-report"></a>Exportera en rapport för jämföra lager för artikelpriser

Varje rapport som du skapar lagras i dataenheten **jämför artikelpriser**. Du kan använda de standardiserade datahanteringsfunktionerna i Supply Chain Management för att exportera data från den här enheten till alla dataformat som stöds inklusive CSV eller Microsoft Excel.

Nedan finns ett exempel på hur du exporterar rapporten **jämföra lager för artikelpriser**:

1. Gå till **Systemadministration > Arbetsytor > Datahantering**.

1. Välj knappen **Exportera** i avsnittet **Datahantering**.

1. Sidan **Export** öppnas, som du kommer att använda för att konfigurera exportjobbet. Börja med att ge jobbet ett **gruppnamn**.

1. I avsnittet **valda entiteter** väljer du **Lägg till entitet** för att öppna en dialogruta där du kan konfigurera följande alternativ:

    - **Entitetsnamn** - Välj **jämför artikelpriser**.
    - **Måldataformat** – Välj det format som du vill exportera till.

1. Välj **Lägg till** för att lägga till den nya raden och välj sedan **Stäng** för att stänga dialogrutan.

1. Vanligtvis exporterar du en rapport i taget. Det gör du genom att konfigurera **filter** för den rad som du just har lagt till i fönstret **Fråga**. På så sätt kan du definiera vilka rapporter från enheten **jämför artikelpriser** som du vill ta med i exporten. Ställ in följande filteralternativ för att exportera en enskild rapport:

    - På fliken **intervall**, välj **Lägg till** om du vill lägga till en ny rad.
    - Ange **Register** till **Jämför artikelpriser**.
    - Ange **härlett register** till **Jämför artikelpriser**.
    - Ställ in **fältet** till det fält som du vill filtrera efter. Vanligtvis ska du använda **körningsnamn** eller **körningstid**.
    - Ange **Kriterier** till värdet från det valda fältet som du vill söka efter (antingen namnet på rapporten eller tiden rapporten genererades).
    - Lägg till fler rader till tabellen **Intervall** tills du har identifierat den rapport som du söker efter, om det behövs.

1. Välj **OK** om du vill spara inställningarna och stänga.

1. Välj **Spara** om du vill spara dina exportinställningar.

1. Öppna fliken **exportalternativ** och välj **exportera nu** för att generera exportfilen.

1. Sidan **körningssammanfattning** öppnas, där du kan se statusen för exportjobbet och en lista över de enheter som har exporterats. Markera enheten **jämför artikelpriser** i området **Bearbetningsstatus för entitet** och välj sedan **hämta fil** för att hämta de data som exporteras från den enheten.

Mer information om hur du använder datahantering för att exportera data finns i [översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]