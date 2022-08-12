---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.27 (juli 2022)
description: Denna artikel beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.27.
author: kamaybac
ms.date: 04/22/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: ff92e6904b8042232159a0aea095d7a91c17d4b7
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124113"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10027-july-2022"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.27 (juli 2022)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management version 10.0.27. Den här versionen har ett versionsnummer för 10.0.1227 på följande schema:

- **Förhandgranskning av version:** april 2022
- **Allmän tillgänglighet för version (självuppdatering):** juni 2022
- **Allmän tillgänglighet för version (automatisk uppdatering):** juli 2022

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel att inkludera funktioner somlades till i versionen efter det att denna artikel ursprungligen publicerades.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Lager och logistik | [Lagerfördelning för tillägget Lagersynlighet](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-allocation-inventory-visibility-add-in) | [Lagerfördelning för Lagersynlighet](../inventory/inventory-visibility-allocation.md) | Aktiverad som standard |
| Tillverkning | Vyn Min dag i körningsgränssnittet för produktionsgolvet | [Hur arbetare använder gränssnittet för produktionsgolvskörning](../production-control/production-floor-execution-use.md) och [Visa semestersaldon i gränssnittet för produktionsgolvkörning](../production-control/production-floor-execution-payroll-stats.md) | Funktionshantering:<br>*Vyn Min dag i körningsgränssnittet för produktionsgolvet* |
| Planering | [Planering Optimeringsstöd för underleverantörer](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-subcontracting) | [Hantera legotillverkningsarbete i produktionen](../production-control/manage-subcontract-work-production.md) | Aktiverad som standard |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som ingår i denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges).

Om du vill slå på eller stänga av någon av dessa funktioner måste du göra detta i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Huvudplanering | Ta hänsyn till ledtid för lager när du skapar en planerad överföringsorder | När en planerad överföringsorder skapas leder den här funktionen till att systemet tar hänsyn till lagerleveranstiden angiven i artikelns standardorderinställningar vid beräkning av inleveransdatumet för planerad överföringsorder för leveransdatumkontroll inställd på Ingen eller ledtid för försäljning. När överföringstid anges används det värdet till beräkning av inleveransdatum och transportdagar ignoreras typ *Ingen* eller *Försäljning*. När överförings leadtid anges används dess värde för beräkningen av inleveransdatum, och transportdagar ignoreras. |
| Anskaffning och källa | Momsinformation för standardmäklarkontrakt på leverantörsfakturarader | Den här funktionen introducerar logik för att ange standardvärden för fälten **Moms** och **Artikelmoms** på mäklarkontrakt leverantörs fakturarader. Den här logiken används bara om avgiftstypen på mäklarkontraktsraden är redovisning/redovisning. Artikelmomsgruppen tar sitt standardvärde antingen från mäklaranskaffningskategorin (om den är inställd) eller från avgiftstypen. Momsgruppen tar sitt standardvärde från leverantörskontot. |
| Anskaffning och källa | Begränsa antalet inköpsorderrader per batchuppgift | Med den här funktionen kan du optimera systemets prestanda när bekräftelser och produktinleveranser bokförs. Den lägger till en ny inställning som heter **Rader per uppgift** på fliken **Leverans** på sidan **Anskaffnings- och inköpsparametrar**. Med den här nya inställningen kan du begränsa antalet inköpsorderrader som varje batchuppgiftsprocess bearbetar. Det kan därför förhindra att stora batchuppgifter gör systemet långsammare. |
| Produktinformationshantering | Fyll i produktattributvärden | Den här funktionen lägger till en periodisk uppgift som kallas *Fyll i produktattributvärden*. Den här nya periodiska uppgiften skapar saknade produktattributvärdeposter för attribut associerade med produkter genom en produktkategori. |
| Produktionskontroll | Ytterligare konfiguration i körningsgränssnittet för produktionsgolvet | <p>Den här alternativ lägger till inställningar för följande alternativ på sidan **Konfigurera körning på produktionsgolv**:</p><ul><li>Öppna dialogrutan **Öppna dialogrutan Starta automatiskt när sökningen slutförs** – När detta alternativ är aktiverat kommer dialogrutan **Starta jobb** öppnas automatiskt när arbetare använder sökfältet för att hitta jobbet.</li><li>**Öppna dialogrutan Rapportförlopp automatiskt när sökningen slutförs** – När detta alternativ är aktiverat kommer dialogrutan **Rapportförlopp** för jobbet öppnas automatiskt när arbetare använder sökfältet för att hitta jobbet.</li><li>**Standard återstående kvantitet i dialogrutan för rapportförlopp** – När detta alternativ är aktiverat, visas dialogrutan **Rapportförlopp** visar återstående kvantitet att rapportera på ett produktionsjobb.</li></ul><p>Mer information finns i [Konfigurera gränssnittet för körning av produktionsstyrning](../production-control/production-floor-execution-configure.md).</p> |
| Produktionskontroll | Produktionsteam i körningsgränssnittet för produktionsgolvet | <p>När flera arbetare tilldelas samma produktionsjobb kan de nu välja en arbetare som ledare. De återstående arbetarna blir automatiskt medhjälpare till ledare. För det resulterande teamet måste bara piloten registrera jobbstatus, medan tidsposter gäller för alla teammedlemmar. Den här funktionen har även stöd för scenarion som kallas för *hjälpmedelsresurs*. I det här scenariot kan en arbetare registrera sig som medhjälpare till en annan arbetare, som sedan blir chef för den nya gruppen.</p><p>Mer information finns i [så här använder du gränssnittet för körning av produktionsstyrning](../production-control/production-floor-execution-use.md).</p> |
| Produktionskontroll | Rapportera planeringsartiklar i körningsgränssnittet för produktionsgolvet | Med den här funktionen förenklas rapporteringsprocessen i batchorder för planering av artiklar i produktionsgolvskörningsgränssnittet. När en batchorder skapas för en produkt som har produktionstypen *Planering av artikel*, kan rapportering som färdig endast göras för sam- och biprodukterna för denna batchorder. Batchorder för planering av artiklar används vanligtvis för att stödja de disassembleringsprocesser, där en råmaterialprodukt disassembleras i flera olika produkter. När en arbetare rapporterar en batchorder för en planeringsartikel som färdig, visar dialogrutan **Rapportera förlopp** nu bara samprodukterna och biprodukterna. Tidigare har det också visats att planeringsartikeln, och detta beteende kan blanda ihop arbetare. |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpartiklar har nyligen lagts till eller uppdaterats väsentligt. Dessa artiklar är inte nödvändigtvis relaterade till de nya funktioner som lagts till för denna version, enligt vad som beskrivs i de föregående avsnitten. De kan dock hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade artiklar |
|---|---|
| Kostnadshantering | [Viktat genomsnittsdatum med Inkludera fysiskt värde och länkning](../cost-management/weighted-average-date.md) |
| Distribuerad hybridtopologi | [Prova skalenheter i en distribuerad hybridtopologi](../cloud-edge/cloud-edge-try-out.md) |
| Dubbelriktad skrivning | [Synkronisera på begäran med prissättningsmotorn Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/pricing-engine.md) |
| Lagerstyrning | [Släpp till distributionslager](../warehousing/release-to-warehouse-process.md) |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för appar för ekonomi och drift

Microsoft Dynamics 365 Supply Chain Management 10.0.27 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.27 av appar för ekonomi och drift (juni 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-27.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.27 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=673271).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022](/dynamics365-release-plan/2022wave1/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

