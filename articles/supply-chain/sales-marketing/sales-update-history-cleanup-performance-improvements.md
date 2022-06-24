---
title: Schemalägg datarensning i försäljningshistorik
description: I denna artikel beskrivs hur du kan förbättra systemets prestanda genom att schemalägga den periodiska körningen för rensning av uppdateringshistorik för försäljning så att denna körs med jämna mellanrum.
author: myvakalo
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1b2c9436fbb5020065f8f6ec30eedeca342d8aa9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900837"
---
# <a name="schedule-sales-history-data-cleanup"></a>Schemalägg datarensning i försäljningshistorik

[!include [banner](../includes/banner.md)]

Som en del av standarddriften skapar och lagrar Microsoft Dynamics 365 Supply Chain Management kontinuerligt data rörande uppdatering av försäljningshistorik. Med tiden kan en stor mängd inaktuella data rörande försäljningshistorik komma att ackumuleras i systemet. Dessa ackumulerade data kan orsaka prestanda- och funktionsproblem när dokument som hör till försäljningsorder bokförs. (Dessa dokument inkluderar bekräftelser av försäljningsorder, försäljningsföljesedlar, försäljningsplocklistor och fakturor). Därför bör du konfigurera och schemalägga den periodiska rensningen av *uppdateringshistoriken för försäljning* så att denna körs med jämna mellanrum. Denna uppgift tar bort alla uppdateringsdata för försäljningshistorik som inte längre behövs.

Om du använder den periodiska rensningen för *uppdateringshistorik för försäljning* rekommenderar vi att du aktiverar funktionen för *Prestandaförbättringar för rensning av uppdateringshistorik för försäljning*, som gör att uppgiften körs mer effektivt. (Du kan emellertid även köra uppgiften utan att aktivera denna funktion.)

## <a name="turn-on-the-sales-history-cleanup-features"></a>Aktivera rensningsfunktionen för försäljningshistorik

Om du vill konfigurera och använda den periodiska uppgiften för *rensning av uppdateringshistorik för försäljning* tillsammans med alla funktioner som beskrivs i denna artikel, måste du aktivera funktionerna *Prestandaförbättringar för rensning av uppdateringshistorik för försäljning* samt *Rensa uppdateringshistoriken för försäljning efter ålder* i funktionshanteringen enligt bekrivningen i följande underavsnitt.

### <a name="sales-history-cleanup-performance-improvements"></a>Förbättringar av prestanda för rensning av försäljningshistorik

Det periodiska batchjobbet **Rensningen av försäljningsuppdateringshistorik** kan ta lång tid om den körs sällan i miljöer med stora antal försäljningsuppdateringar. I dessa situationer kan funktionen *Förbättringar i rensning av försäljningshistorik* hjälpa till att minska körningens varaktighet och förbättra tillförlitligheten.

Funktionen förbättrar det befintliga rensningsjobbet på följande sätt:

- Rensningen delas upp i batchar (du kan ändra batchstorleken genom anpassningar).
- Den kommer att köras i högst 2 timmar (du kan ändra tiden genom anpassningar).
- Där så är möjligt utnyttjar den databaskapaciteter i syfte att minimera låsningar och undvika att transaktionsregister sammanfogas under rensningen.

När funktionen har aktiverats kommer batchjobbet **Rensning av försäljningsuppdateringshistorik** (**Försäljning och marknadsföring \> Periodiska uppgifter \> Rensning \> Rensning av försäljningsuppdateringshistorik**) att köras som tidigare, men nu med bättre prestanda samt i maximalt 2 timmar. Detta innebär att det kanske måste köras flera gånger om du vill rensa alla data för en specifik kvarhållningstidsram.

Innan du kan använda funktionen måste den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Försäljning och marknadsföring*
- **Funktionens namn** *Förbättringar i prestanda för rensning av försäljningshistorik*

### <a name="clean-up-sales-update-history-based-on-age"></a>Rensa försäljningsuppdateringshistorik grundat på ålder

Funktionen *Rensa historiken för försäljningshistorik* låter dig ange den maximala åldern hos de poster som ska behållas när den periodiska uppgiften *Historikuppdatering för försäljningshistorik* körs. Äldre poster raderas. Denna funktion är användbar när du konfigurerar uppgiften så att den körs periodiskt, detta eftersom ålder alltid beräknas i relation till det datum då uppgiften körs. Om du inte använder denna funktion kan du bara ange ett visst datum för de äldsta posterna som ska behållas.

Innan du kan använda funktionen måste den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Försäljning och marknadsföring*
- **Funktionsnamn:** *Rensa uppdateringshistoriken för försäljning grundat på ålder*

## <a name="set-up-and-schedule-the-sales-history-cleanup-periodic-task"></a>Konfigurera och planera den periodiska uppgiften för rensning av försäljningshistorik

Följ de här stegen om du vill konfigurera den periodiska uppgiften *Rensning av försäljningshistorik*.

1. Analysera ditt företags behov för att fastställa hur många dagar av historiska bokföringsdata för försäljningsorder du måste ha. Vi rekommenderar vanligtvis att du kör rensningsuppgiften var tredje månad och högst en gång i halvåret.
1. Gå till **Försäljning och marknadsföring \> Perioduppgifter \> Rensning \> Rensa försäljningsuppdateringshistorik**.
1. I dialogrutan **Rensa försäljningsuppdateringshistorik**, på snabbfliken **Parametrar**, anger du följande fält:

    - **Rensning** – Välj ett av följande värden om du vill ange vilken typ av poster som ska rensas:

        - **Körd** – Radera endast poster som har bearbetats fullständigt. Eftersom du inte får någon ytterligare användning av dessa poster är det här alternativet det säkraste.
        - **Körd och felaktig** – Radera både fullständigt bearbetade poster och poster där ett fel har inträffat. Det här alternativet är det vanligaste. Du kanske vill inspektera eller till och med åtgärda felaktiga poster istället för att få dem rensade automatiskt. Många företag väljer emellertid att rensa upp dessa poster även efter ungefär en månad, detta eftersom de troligen inte längre är relevanta vid den tiden.
        - **Alla** – Radera körda, felaktiga och väntande poster. Väntande poster är giltiga men har inte bearbetats helt. I de flesta fall vill du troligen inte att de ska raderas automatiskt. I vissa situationer kan du emellertid välja att radera dem automatiskt efter att en viss tid har passerats.

    - **Behåll poster baserat på ålder** – Ange om du vill rensa poster baserat på deras ålder den dag uppgiften körs eller ta bort poster som skapades före ett fast datum. Om du planerar rensningen som en återkommande uppgift bör du ange detta alternativ som *Ja*, detta eftersom åldern alltid beräknas i förhållande till det datum då uppgiften körs.

        - Ange detta alternativ som *Ja* om du vill aktivera fältet **Maximal ålder**. Du använder detta fält när du vill ange den högsta ålder för posterna som ska behållas varje gång uppgiften körs. Fältet **Skapad till** ignoreras.
        - Ange detta alternativ som *Nej* om du vill aktivera fältet **Skapad till**. Du använder detta fält när du vill ange det äldsta skapandedatum för posterna som ska behållas när uppgiften körs. Fältet **Maximal ålder** ignoreras.

    - **Skapad till** – Den här inställningen gäller bara om alternativet **Behåll poster baserat på ålder** ställs in på *Nej*. Ange det äldsta skapandedatum för posterna som ska behållas när uppgiften körs. Poster som skapats före detta datum kommer att raderas.
    - **Maximal ålder** – Denna inställning gäller bara om alternativet **Behåll poster baserat på ålder** ställs in på *Ja*. Ange den högsta ålder (i dagar) för posterna som ska behållas varje gång uppgiften körs. Äldre poster raderas.

1. På snabbfliken **Kör i bakgrunden** anger du hur, när och hur ofta iuppgiften sak köras. Använd dessa inställningar när du vill implementera tidsplanen du skapade i steg 1. Fälten fungerar precis som för andra typer av [batchjobb](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK** om du vill använda inställningarna och stänga dialogrutan.
