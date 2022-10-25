---
title: Förhandsversion av Dynamics 365 Supply Chain Management 10.0.30 (november 2022)
description: Denna artikel beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.30.
author: kamaybac
ms.date: 09/08/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-09-08
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 18fec49f2388159cae0809c63685102a04e90c57
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689203"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10030-november-2022"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management (10.0.30 november 2022)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management version 10.0.30. Den här versionen har ett versionsnummer för 10.0.1362 på följande schema:

- **Förhandsversion:** september 2022
- **Allmän tillgänglighet för versionen (självuppdatering):** oktober 2022
- **Allmän tillgänglighet för version (automatisk uppdatering):** november 2022

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel att inkludera funktioner somlades till i versionen efter det att denna artikel ursprungligen publicerades.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Tillverkning | [Övervaka utrustning med Sensor Data Intelligence](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/monitor-equipment-sensor-data-intelligence) | [Sensor Data Intelligence-startsida](../sensor-data-intelligence/sdi-home-page.md) | Funktionshantering:<br>*(Förhandsversion) Sensor Data Intelligence* |
| Warehouse management | [Omvägar på flera nivåer för mobilappen Warehouse Management](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/multi-level-detours-warehouse-management-mobile-app) | [Konfigurera omvägar för steg i menyalternativ för mobila enheter](../warehousing/warehouse-app-detours.md) | Funktionshantering:<br>*Omvägar på flera nivåer för mobilappen Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som ingår i denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges).

Om du vill slå på eller stänga av någon av dessa funktioner måste du göra detta i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Produktionskontroll | Information om behållning på sidan med produktionsorder som ska frisläppas | Lägg till en kolumn med lagerbehållningen för radartikeln i radavsnittet på sidan med **produktionsorder för frisläppning**.  |
| Transporthantering | Tilldela leveranser relaterade ruttsegment | Med denna funktion kan systemet fördela fraktkostnaderna på ett mer korrekt sätt, inklusive för lastning med flera leverans som levereras till olika segmentdestinationer längs ett enskilt flöde. Varje leverans tilldelas till det mest lämpliga flödessegmentet utifrån försändelse- och segmentadresserna. Funktionen beräknar sedan varje leveranss fraktkostnad som en del av belastningens totala fraktkostnad, baserat på leveransens relativa vikt, volym, kvantitet och körsträcka. Den här funktionen gäller endast för försändelser som hanteras med hjälp av modulen Transporthantering (TMS). |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för Ekonomi och drift-appar

Microsoft Dynamics 365 Supply Chain Management 10.0.30 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.30 av Finance and Operations-appar (November 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i version 10.0.29 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2022](/dynamics365-release-plan/2022wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
