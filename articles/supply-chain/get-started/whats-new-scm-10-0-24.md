---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.24 (februari 2022)
description: Denna artikel beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.24.
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 94e465616338b0c905ccf6b8244324c18c7a59e8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849457"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10024-february-2022"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.24 (februari 2022)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management-version 10.0.24. Den här versionen har ett versionsnummer för 10.0.1084 och är tillgänglig enligt följande:

- **Förhandsgranska utgåva:** december 2021
- **Allmän tillgänglighet för frisläppning (självuppdatering):** 2022 januari
- **Allmän tillgänglighet för frisläppning (automatisk uppdatering):** 2022 februari

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel i syfte att inkludera funktioner som kommit med i versionen efter det att denna artikel publicerades första gången.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Distribuerad hybridtopologi | [Förbättrade arbetsbelastningar för lagerkörning på skalningsenheter](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [Arbetsbelastningar för distributionslagerhantering för moln- och kantskalningsenheter](../cloud-edge/cloud-edge-workload-warehousing.md) | Aktiverad som standard. |
| Distribuerad hybridtopologi | [Starta tillverkningsorder på arbetsbelastningen för lagerhantering för moln- och kantskalningsenhet](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-manufacturing-execution-workloads-scale-units) | [Arbetsbelastningar för tillverkningskörning för moln- och kantskalenheter](../cloud-edge/cloud-edge-workload-manufacturing.md) | Funktionshantering (*Starta tillverkningsorder på arbetsbelastningen för lagerhantering för moln- och kantskalningsenhet*)  |
| Planering | [Planeringsoptimeringssupport för beställningsmarginal och ut ärendemarginal](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [Säkerhetsmarginaler](../master-planning/planning-optimization/safety-margins.md) | Aktiverad som standard. |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som ingår i denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges).

Om du vill slå på eller stänga av någon av dessa funktioner måste du göra detta i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Produktionskontroll | Kontroll av materialtillgänglighet på begäran för tillverkningsorder | Denna funktion gör det snabbare att öppna sidan **Tillverkningsorder som ska frisläppas** som är tillgänglig från arbetsytan **Hantering av produktionsgolvskörning**. Om den här funktionen inte har den här funktionen kontrollerar systemet automatiskt om material är tillgängliga för alla listade tillverkningsorder så snart du öppnar sidan, vilket kan ta lång tid om du har ett stort antal order. När den här funktionen har aktiverats används i stället en verktygsfältsknapp som du kan använda för att initiera materialkontrollen enbart för valda order och vid behov. |
| Produktionskontroll | (Förhandsversion) Registrera materialförbrukning i körningsgränssnittet för produktionsgolv (inte WMS) | Med denna funktion kan arbetare använda gränssnittet för produktionsgolvkörning för att registrera materialförbrukning, batchnummer och serienummer. Den här funktionen stöder bara artiklar som inte är aktiverade för att använda avancerade lagerställeprocesser (WMS). Stöd för WMS-aktiverade artiklar planeras för en framtida version.<p>Vissa tillverkare, särskilt de som finns i processindustrier, måste explicit registrera hur mycket material som förbrukas för varje batch eller tillverkningsorder. En arbetare kan till exempel använda en våg för att väga hur mycket material som förbrukats medan de arbetar. För att garantera fullständig spårning av material måste dessa organisationer också registrera vilka batchnummer som förbrukades när varje produkt produceras. |
| Produktionskontroll | Rapportera som klar om arbetsbelastningen för lagerhantering för moln- och kantskalningsenhet | Med den här funktionen kan personalen använda mobilappen Warehouse Management för att rapportera en tillverknings- eller batchorder som färdig när programmet körs mot en arbetsbörda för lagerstyrning i en enhet för molnbaserad eller kantskala. Mer information finns i [Rapportera som färdig och inlagrad på en skalningsenhet](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF). |
| Warehouse management | Nya sidor för lastplaneringsworkbench | Aktiverar två nya workbench-sidorna för lastplanering: **Workbench för inkommande lastplanering** och **Workbench för utgående lastplanering**. |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpartiklar har nyligen lagts till eller uppdaterats väsentligt. Dessa artiklar är inte nödvändigtvis relaterade till de nya funktionerna som lagts till för denna version, enligt vad som beskrivs i det föregående avsnittet. De kan dock hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade artiklar |
|---|---|
| Kostnadshantering | [Lagervärderapporter](../cost-management/inventory-value-report-storage.md) |
| Kostnadshantering | [Exempel och logik rörande värderapport för lager](../cost-management/inventory-value-report-examples.md) |
| Huvudplanering | [Parametrar för datum och tid används i Planeringsoptimering](../master-planning/planning-optimization/date-time-used.md) |
| Huvudplanering | [Inställning av efterfrågeprognosticering](../master-planning/demand-forecasting-setup.md) |
| Huvudplanering | [Använd säkerhetslagerjournalen för att uppdatera minimumdisponering för artiklar](../master-planning/safety-stock-journal.md) |
| Produktionskontroll | [Anpassa körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-customize.md) |
| Produktionskontroll | [Styla körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-styles.md) |
| Försäljning och marknadsföring | [Schemalägga datarensning i försäljningshistorik](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Warehouse management | [Användarkonton för mobil enhet](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för Finance and Operations-appar

Microsoft Dynamics 365 Supply Chain Management 10.0.24 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.24 av Ekonomi och Drift-appar (februari 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.24 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f).

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
