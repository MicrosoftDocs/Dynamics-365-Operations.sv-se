---
title: Visualisering av utgående arbetsbelastning
description: Denna artikel innehåller information om visualisering av utgående arbetsbelastning. Med hjälp av den här funktionen kan lagerchefer och administratörer skapa anpassade arbetsbelastningsdiagram som kan användas för att övervaka förloppet för det aktuella arbetet och det belopp som återstår. Lager chefer kan skapa flera vyer och konfigurera automatisk uppdatering när de behövs.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-08-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 78d0d81095bb52a314936dd7590a5690d94ecb15
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334428"
---
# <a name="outbound-workload-visualization"></a>Visualisering av utgående arbetsbelastning

[!include [banner](../includes/banner.md)]

Avancerade installationsmöjligheter som är tillgängliga från sidan **Visualisering av utgående arbetsbelastning** gör det möjligt för distributionslagerchefer och ansvariga att skapa anpassade arbetsbelastningsdiagram som kan användas för att övervaka förloppet för det aktuella arbetet och det belopp som återstår. Lager chefer kan skapa flera vyer och konfigurera automatisk uppdatering när de behövs. Visualiseringar av utgående arbetsbelastning är lämpliga för visning på sidorna för lagerprestanda.

Den här funktionen kan användas för att spåra förloppet för plocknings arbete. Funktionen är integrerad med arbetsstyrningen, och om arbetshantering är inställt kan avgående visualiseringar visa en beräkning av antalet timmar som återstår för det pågående plockningsarbetet (filtrerat).

## <a name="turn-the-outbound-workload-visualization-feature-on-or-off"></a>Aktivera och inaktivera funktionen för Visualisering av utgående arbetsbelastning

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.29 version av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.29 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Visualisering av utgående arbetsbelastning* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-outbound-workload-visualizations"></a>Ställ in visualisering av utgående arbetsbelastning

När du konfigurerar visualiseringarna skapar du en samling filter (vyer) och utformar varje filter så att det visar en annan typ av analys. Du använder sidan **Konfigurera filter** för att utforma filtren.

Om du vill konfigurera en utgående arbetsbelastningsvisualisering följer du stegen nedan.

1. Gå till **Hantering av distributionslager \> Lagerövervakningsrapporter \> Visualisering av utgående arbetsbelastning**.

    Sidan **Visualisering av utgående arbetsbelastning** visas. När du har skapat vissa filter visas visualiseringen i den här sidan. Du kan skapa så många filter som du vill. Alla filter som du skapar sparas under ditt användarkonto, så att du kan använda dem senare. Med andra ord får varje användare sin egen uppsättning filter som de skapar. Dessa filter delas inte med andra användare.

1. På sidan **Visualisering av utgående arbetsbelastning** i åtgärdsfönstret på fliken **Filter** välj **Konfigurera filter**.
1. På sidan **Konfigurera filter** i åtgärdsfönstret, välj **Ny** för att lägga till ett filter och ange sedan följande fält:

    - **Grupptabell x-axel** – Välj det register som innehåller fältet som ska användas för att gruppera X-axelns värden.
    - **Gruppfältet x-axel** – bland fälten i registret som du valde i **tabellfältet x-axel grupp**, markera det fält som ska användas för att gruppera X-axelns värden.
    - **Värdetabell x-axel** – Välj det register som innehåller fältet som ska användas för att ytterligare analysera grupperna.
    - **Värdefältet x-axel** – bland fälten i registret som du valde i **tabellvärde x-axel grupp**, markerar det fält som ger värden som ska analyseras för varje grupp.
    - **Uppdatera automatiskt** – Välj om visualiseringen ska uppdateras automatiskt.
    - **Uppdateringsintervall (minuter)** – Ange antalet minuter mellan automatiska uppdateringar.
    - **Visningsnivå** – Välj om du vill visa öppna rader eller öppna sidhuvud antal i diagrammet.
    - **Plockningstyp** – Om du anger fältet **Visningsnivå** till _Öppna rader_, väljer du om antalet öppna arbetsrader i diagrammet ska omfatta initial plockningar, mellanplockade plockningar eller både initial plockning och mellanlagrade plockningar.
    - **Webbplats** – Välj den webbplats som diagrammet ska läsas in för.
    - **Lagerställe** – Välj det lagerställe som diagrammet ska läsas in för.
    - **Antal dagar att inkludera** – Ange det antal dagar bakåt från vilket diagrammet ska genereras.
    - **Typ av arbetsorder** – Välj de avgående arbetsordertyper som du vill filtrera efter.

    ![Sidan konfigurera filter.](media/work-viz-filters-1.png "Sidan konfigurera filter")

1. Stäng sidan **Konfigurera filter** om du vill återvända till sidan **Visualiseringar av utgående arbetsbelastning**.

    På sidan **Visualiseringar av utgående arbetsbelastning** visas nu data, baserat på de nya filterinställningarna. Det nya filtret är nu tillgängligt och har valts i fältet **Filter**. Följande fält är tillgängliga överst i diagrammet:

    - **Filter** – det här fältet innehåller alla filter som du har skapat hittills. Välj ett filter om du vill visa data i diagrammet.
    - **Uppdaterades senast** – i det här fältet visas det datum och den tidpunkt då informationen i diagrammet senast uppdaterades.
    - **Uppskattad/faktisk tid** – om arbetsstandarder ställs in i systemet ställer du in det här alternativet på *Ja* för att visa ackumulerade uppskattade plocktider överst i varje kolumn i diagrammet. Om du inte använder arbetsstandarder är det här alternativet inte tillgängligt.

    ![Exempel på visualisering.](media/work-viz-chart.png "Exempel på visuella effekter")

1. Välj en stapel i diagrammet om du vill visa den tillhörande arbetsradinformationen.

    ![Arbetsradsdetaljer.](media/work-viz-work-details.png "Arbetsradsdetaljer")

## <a name="example-outbound-workload-visualization-for-zones"></a>Exempel: Visualisering av utgående arbetsbelastning för zoner

I det här exemplet vill du skapa en visualisering som visar arbetsrader för varje zon, och status för varje arbetsrad ( _öppen_, _stängd_ eller _annullerad_). I det här fallet kan du konfigurera ett filter med följande inställningar:

- **Filternamn** – Ange ett namn för filtret (t.ex _Zon kontra arbetsstatus_).
- **Beskrivning** – Ange en kort beskrivning för filtret (t.ex _Zon kontra arbetsstatus_).
- **Grupptabellen X-axel** – Välj _platser._
- **Grupp med X-axeln** – Välj _zon-ID_.
- **Värderegistret för X-axeln** – Välj _arbete_ eftersom du vill visa arbete per zon.
- **Värdefält för X-axeln** – Välj _arbetsstatus_ eftersom du vill visa arbetsstatus.
- **Uppdatera automatiskt** – Välj om visualiseringen ska uppdateras automatiskt.
- **Plockningtyp** – Välj _initiala plockningar och mellanplockade plockningar_, eftersom du vill inkludera både ursprungliga plockningar och plockningar från mellanlagringsplatser. Med andra ord vill du alltid inkludera alla de plockningsarbetsrader som du har.
- **Visningsnivå** – Välj _Öppna rader_, eftersom du vill visa informationen per rad, inte per arbetshuvud.

Följande bild visar ett exempel på det resulterande diagrammet.

![Visualisering av zoner kontra arbetsstatus.](media/work-viz-chart.png "Visualisering av zoner kontra arbetsstatus")

Det här diagrammet visar två zoner med namnet **VÅNING** och **BULK**, plus en zon som har namnet **Tom**. Den **tomma** zonen representerar alla arbetsrader som inte är medlemmar i några zoner. Diagrammet visar alltid alla icke-relaterade filtrerade data som **tomma** för att ge så mycket synlighet som möjligt. I **GOLVET** visar diagrammet tre stängda rader och fyra öppna rader. I **BULK** visar diagrammet fyra stängda rader, en öppen och 24 annullerade rader. Slutligen visar diagrammet åtta stängda rader som inte ingår i någon zon och därför listas som **tomma**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]