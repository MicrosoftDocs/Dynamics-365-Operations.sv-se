---
title: Borttagna och utfasade funktioner i Dynamics 365 Supply Chain Management
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: d4d2805e36f132660152370cbeee856862ad6faa
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689546"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Borttagna och utfasade funktioner i Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Det här ämnet kommer att uppdateras när nya borttagna eller inaktuella funktioner dokumenteras för Dynamics 365 Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull.

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Borttagna eller föråldrade funktioner i Supply Chain Management version 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11-stöd för Dynamics 365 är inaktuellt

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Från och med december 2020 kommer Microsoft Internet Explorer 11-stöd för samtliga Dynamics 365-produkter att betraktas som inaktuellt, och Internet Explorer 11 kommer inte att stödjas efter augusti 2021.<br><br>Detta påverkar kunder som använder Dynamics 365-produkter som har utformats för användning med ett Internet Explorer 11-gränssnitt. Efter augusti 2021 stöds inte Internet Explorer 11 för sådana Dynamics 365-produkter. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar våra kunder att övergå till Microsoft Edge.|
| **Produktområden som påverkas**         | Alla Dynamics 365-produkter |
| **Distribueringsalternativ**              | Allt|
| **Status**                         | Inaktuell. Internet Explorer 11 kommer inte att stödjas efter augusti 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Användning av den inbyggda huvudplaneringsmotorn för Supply Chain Management för tillverkningsscenarier

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | För att förbättra prestanda och minimera inläsning av SQL-databas under huvudplaneringskörning, ersätts den inbyggda huvudplaneringsmotorn för Supply Chain Management med planeringsoptimering. Planeringsoptimering möjliggör snabba planeringskörningar som kan utföras även under kontorstid. Då kan planeraren omedelbart reagera vid ändringar i efterfrågan eller planeringsparametrar. |
| **Ersatt av en annan funktion?**   | Ja, planeringsoptimering kommer att ersätta befintliga inbyggda huvudplaneringsmotorn för Supply Chain Management. |
| **Produktområden som påverkas**         | Supply Chain Management – Huvudplanering |
| **Distribueringsalternativ**              | Endast i molnet. Planeringsoptimering stöds inte för lokala distributioner. |
| **Status**                         | Inaktuell. I oktober 2021 kommer tillverkningsscenarier inte längre att stödjas med inbyggda Dynamics 365 Supply Chain Management huvudplaneringsmotor. För tillverkningsscenarier måste kunder använda planeringsoptimering för huvudplanering. Mer information finns i [dokumentationen för planeringsoptimering](https://go.microsoft.com/fwlink/?linkid=2105830). Kunder med lokala distributioner av Dynamics 365 Supply Chain Management kan fortsätta att använda Supply Chain Managements huvudplaneringsmotor för tillverkningsscenarier efter oktober 2021. Det sker dock inga fler förbättringar av funktionen. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Borttagna eller föråldrade funktioner i Supply Chain Management version 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Användning av den inbyggda huvudplaneringsmotorn för Supply Chain Management för distributionsscenarier

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | För att förbättra prestanda och minimera inläsning av SQL-databas under huvudplaneringskörning, ersätts den inbyggda huvudplaneringsmotorn för Supply Chain Management med planeringsoptimering. Planeringsoptimering möjliggör snabba planeringskörningar som kan utföras även under kontorstid. Då kan planeraren omedelbart reagera vid ändringar i efterfrågan eller planeringsparametrar. |
| **Ersatt av en annan funktion?**   | Ja, planeringsoptimering kommer att ersätta befintliga inbyggda huvudplaneringsmotorn för Supply Chain Management. |
| **Produktområden som påverkas**         | Supply Chain Management – Huvudplanering |
| **Distribueringsalternativ**              | Endast i molnet. Planeringsoptimering stöds inte för lokala distributioner. |
| **Status**                         | Inaktuell. 1 april 2021 kommer distributionsscenarier inte längre att stödjas med inbyggda Dynamics 365 Supply Chain Management huvudplaneringsmotor. För distributionsscenarier måste kunder använda planeringsoptimering för huvudplanering. Mer information finns i [dokumentationen för planeringsoptimering](https://go.microsoft.com/fwlink/?linkid=2105830). Kunder med lokala distributioner av Dynamics 365 Supply Chain Management kan fortsätta att använda Supply Chain Managements huvudplaneringsmotor för distributionsscenarier efter april 2021. Det sker dock inga fler förbättringar av funktionen. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner

Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]