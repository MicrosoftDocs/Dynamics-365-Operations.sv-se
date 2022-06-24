---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.20 augusti 2021
description: Denna artikel innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Supply Chain Management 10.0.20.
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3eadc447d8c0c443fa9d3eab220300e3eedf051d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888655"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10020-august-2021"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.20 augusti 2021

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management version 10.0.20. Den här versionen har ett versionsnummer för 10.0.886 och är tillgänglig enligt följande:

- **Förhandsversion:** maj 2021
- **Allmän tillgänglighet för version (självuppdatering):** juli 2021
- **Allmän tillgänglighet för frisläppning (automatisk uppdatering):** augusti 2021

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande register lista de funktioner som ingår i denna version: Kolumnen *Funktion* innehåller länkar till [versionsplanen](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), där du kan se de officiella frisläppningsdatumen för respektive funktion. Kolumnen *Mer information* innehåller mer information och/eller länkar till relaterad dokumentation.

De flesta av dessa funktioner måste aktiveras med [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) innan du kan använda dem.

| Funktionsområde | Funktion | Mer information |
|---|---|---|
| Lager&nbsp;och&nbsp;logistik | [Prestandaförbättringar för försäljningsorderinformation](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Med den här funktionen blir användargränssnittet effektivare när försäljningsorder öppnas, särskilt för order som innehåller många rader. |
| Tillverkning | [Starta processautomatiseringsflöden för att skapa kvalitetsorder](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [Starta processautomatiseringsflöden för att skapa kvalitetsorder](../production-control/process-automation-quality-orders.md ) |
| Tillverkning | [Förbättrat gränssnitt för produktion av golv för tillverkning](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [Konfigurera körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-configure.md) |
| Planering | [Planering av oändlig kapacitet för Planeringsoptimering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | [Tidsplanering med obegränsad kapacitet](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Produktinformationshantering | [Hantera ändringar i formler och deras ingredienser](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [Hantera ändringar i formler och deras ingredienser](../engineering-change-management/manage-formula-changes.md) |
| Produktinformationshantering | [Produktberedskapskontroller](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [Produktberedskap](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande register lista de funktionsförbättringar som ingår i denna version: Var och en av dessa tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [frisläppningsplanen](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges). Om du vill använda någon av dessa funktioner måste du explicit aktivera dem i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn&nbsp;&nbsp;i&nbsp;funktionshantering | Mer information |
|---|---|---|
| Huvudplanering | Parallell auktorisering av justerad efterfrågeprognos | Med den här funktionen kan du parallellt skapa justerad efterfrågeprognos från sidan **Justerad efterfrågeprognos**. Syftet med funktionen är att öka prestanda när ett stort antal prognoser godkänns. Vid auktorisering kan användaren ange **Antal trådar** i dialogrutan för godkänna. |
| Huvudplanering | (Förhandsversion) Batchbar bekräftelse och konsolidering för planerade bulk- och paketbatchorder | Den här funktionen gör det möjligt att använda batchjobb för att bekräfta och konsolidera planerade bulk- och paketorder. |
| Produktionskontroll | Kopiera allmänna flöden | Med den här funktionen utökas kopieringsflödesfunktionen så att användarna kan kopiera flöden som inte är artikelspecifika. Det gör att systemet kan uppdatera all relevant information (till exempel plats, flödesgrupp, resursbehov och olika tider) när funktionen för kopiering av flöde har använts för att skriva över ett flöde som ännu inte tilldelats en artikel. |
| Produktionskontroll | Uppdatera relaterade resurskrav när en flödesåtgärd ändras | Den här funktionen gör det möjligt för systemet att uppdatera de relaterade resurskraven när en användare ändrar åtgärden för ett befintligt flödessteg. |
| Produktinformationshantering | Förbearbetning av strukturlistasrapport för att förhindra tidsgräns | Med den här funktionen kan strukturlistasrapporten förbearbetas. På så sätt undviker du tidsutjämningsproblem när du har en stor databelastning för rapporten. |
| Anskaffning och källa | Aktivera återställning av anskaffningsrelaterade arbetsflöden | Med den här förhandsgranskningsfunktionen kan du återställa följande arbetsflöden till utkaststatus: Inköpsorder, Leverantörsändring och Inköpsrekvisitioner. |
| Transporthantering | Gör det möjligt att skapa en leverantörsfakturajournal när en fraktsedel kastas | När den här funktionen är aktiverad skapas en motsvarande leverantörsfakturajournal bara av avstämningsskäl när du använder alternativet för löneleverantör. Annars skapas alltid fakturajournalen. |
| Warehouse management | Validera mallar valda för lagerpåfyllnadsjobb | Med den här funktionen kan användarna välja giltiga påfyllnadsmallar när de konfigurerar ett påfyllnadsjobb. Den hindrar användarna från att skapa ett påfyllnadsjobb utan en mall och från att välja mallar av typen *Lagerpåfyllnad*, om inte skapar påfyllnadsarbete och kan ta lång tid att bearbeta. |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpartiklar har nyligen lagts till eller uppdaterats väsentligt. De är inte nödvändigtvis relaterade till de nya funktioner som har lagts till för den här versionen, vilket visas i föregående avsnitt, men de kan hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade artiklar |
|---|---|
| Konstruktionsändringshantering | [Produktens livscykeltillstånd och transaktioner](../engineering-change-management/product-lifecycle-state-transactions.md) |
| Lagerhantering | [Tillägg för lagersynlighet](../inventory/inventory-visibility.md)<br><br>[Översikt över kvalitet och avvikelsehantering](../inventory/quality-management-processes.md) (samt alla relaterade kvalitetshanteringsartiklar) |
| Anskaffning och källa | [Underhålla leverantörscertifiering](../../finance/public-sector/manage-vendor-certification.md) |
| Produktionskontroll | [Styla körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-styles.md) |
| Warehouse management | [Tilldela stegikoner och titlar för mobilappen för Warehouse Management](../warehousing/step-icons-titles.md)<br><br>[Uppskjuten bearbetning av manuell lagerrörelse](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för Ekonomi och drift-appar

Microsoft Dynamics 365 Supply Chain Management 10.0.20 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.20 av appar för ekonomi och drift (juli 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.20 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8). 

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: 2021 utgivningsvåg 1 plan

Har du frågeställningar om nya och kommande funktioner i våra affärsappar eller plattformen?

Se [Dynamics 365: 2021 utgivningsvåg 1 plan](/dynamics365-release-plan/2021wave1/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
