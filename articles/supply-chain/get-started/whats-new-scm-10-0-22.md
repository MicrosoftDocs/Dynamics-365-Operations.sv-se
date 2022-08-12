---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management (10.0.22 november 2021)
description: Denna artikel beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.22.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 310809799a81c6709041764f7038de2a70b7f203
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124803"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10022-november-2021"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management (10.0.22 november 2021)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management-version 10.0.22. Den här versionen har ett versionsnummer för 10.0.995 och är tillgänglig enligt följande:

- **Förhandsversion:** september 2021
- **Allmän tillgänglighet för versionen (självuppdatering):** oktober 2021
- **Allmän tillgänglighet för version (automatisk uppdatering):** november 2021

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Kolumnen *Funktion* innehåller länkar till [versionsplanen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), där du kan se de officiella frisläppningsdatumen för respektive funktion. Kolumnen *Mer information* innehåller mer information och/eller länkar till relaterad dokumentation. Information om hur du aktiverar en funktion finns i kolumnen *Aktiverad av*. Mer information om hur du använder funktionshantering finns i [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Vi kan komma att uppdatera denna artikel i syfte att inkludera funktioner som kommit med i versionen efter det att denna artikel publicerades första gången.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Planering | [Stöd för Planeringsoptimering för kapacitetsbaserad resursallokering](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Tidsplanering med resursurval baserat på kapacitet](../master-planning/planning-optimization/capability-based-scheduling.md) | Funktionshantering (*Planering med obegränsad kapacitet för Planeringsoptimering*) |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som ingår i denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges). Om du vill använda någon av dessa funktioner måste du explicit aktivera dem i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Distribuerad hybridtopologi | *(Ingen funktionshantering krävs.)* | <p>Den här versionen utökar de utgående lastplaneringsfunktionerna för lagerstyrningsarbetsbelastningen för moln- och kantskalningsenheter.</p><p>För mer information, se [Arbetsbelastningar för hantering av distributionslager för moln- och kantskalningsenheter](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Konstruktionsändringshantering | Variantgenerering för tekniska produkter | <p>Med hjälp av den här funktionen kan du skapa flera varianter för en konstruktionsprodukt baserat på dess färg, storlek, utförande eller konfigurationsdimensioner.</p><p>Mer information finns i [Generera varianter för konstruktionsprodukter](../engineering-change-management/engineering-variants.md).</p> |
| Hantering av lager och lagerstyrning | Integrering av lagersynlighet med reservationsförskjutning | <p>Den här funktionen kan bara aktiveras efter att funktionen *Integrering av Lagersynlighet* har aktiverats. Här finns funktioner för att motboka reservationer som görs i Lagersynlighet.</p><p>Mer information finns i [Reservationer för Lagersynlighet](../inventory/inventory-visibility-reservations.md).</p> |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpartiklar har nyligen lagts till eller uppdaterats väsentligt. Dessa artiklar är inte nödvändigtvis relaterade till de nya funktionerna som lagts till för denna version, enligt vad som beskrivs i det föregående avsnittet. De kan dock hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade artiklar |
|---|---|
| Konstruktionsändringshantering | I [Konstruktionsändringshantering – översikt](../engineering-change-management/product-engineering-overview.md) visas nu alla relaterade, valfria funktioner som är tillgängliga i funktionshantering |
| Huvudplanering | [Inställning av efterfrågeprognosticering](../master-planning/demand-forecasting-setup.md) |
| Huvudplanering | [Nettobehov och pegging-information med Planeringsoptimering](../master-planning/planning-optimization/net-requirements.md) |
| Lagerstyrning | [Släpp till lagerställe](../warehousing/release-to-warehouse-process.md) ger en detaljerad översikt över den fullständiga frisläppningsprocessen till lagerställe |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för appar för ekonomi och drift

Microsoft Dynamics 365 Supply Chain Management 10.0.22 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.22 av appar för ekonomi och drift (november 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.22 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2021

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2021](/dynamics365-release-plan/2021wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

