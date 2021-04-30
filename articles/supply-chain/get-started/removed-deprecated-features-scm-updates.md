---
title: Borttagna och utfasade funktioner i Dynamics 365 Supply Chain Management
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning i Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 785f9055c44110d88b9494b5066647511840b646
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909657"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Borttagna och utfasade funktioner i Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Det här ämnet kommer att uppdateras när nya borttagna eller inaktuella funktioner dokumenteras för Dynamics 365 Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull.

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](/dynamics/s-e/). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Borttagna eller föråldrade funktioner i Supply Chain Management version 10.0.18

### <a name="dynamics-365-for-finance-and-operations---warehousing-the-warehouse-app"></a>Dynamics 365 for Finance and Operations - Lagerhållning (distributionslagerappen)

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Gäller från april 2021, *Dynamics  365 for Finance and Operations - Lagerhållning* (distributionslagerappen) är inaktuell och stöds inte efter april 2022. Den ersätts nu av *Mobilappen för distributionslagerhantering*, som släpps med version 10.0.17 av Supply Chain Management. Den nya appen är en fullständig ersättning, men använder samma underliggande ramverk, vilket gör migreringen enkel. De två apparna kan vid behov användas sida vid sida för att hjälpa användarna att gradvis justera när de lär sig använda det nya programmet.<br><br>För mer information om den nya mobilappen för distributionslagerhantering, se [Mobilappen för distributionslagerhantering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) och [Installera och anslut mobilappen för distributionslagerhantering](../warehousing/install-configure-warehouse-management-app.md). |
| **Ersatt av en annan funktion?**   | Ja, ersätts av det nya mobilappen för distributionslagerhantering. |
| **Produktområden som påverkas**         | Supply Chain Management - distributionslagerapp |
| **Distribueringsalternativ**              | Moln och lokal |
| **Status**                         | Inaktuell. Distributionslagerappen får stöd med åtgärds- och säkerhetskorrigeringar, men funktionsutökningar tillhandahålls inte längre. Efter april 2022 stöds inte längre den gamla istributionslagerappen och kunderna uppmanas att flytta till den nya mobilappen för distributionslagerhantering. Det gamla distributionslagerappen tas då bort från Microsoft Store och Google Play store.  |

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
| **Status**                         | Inaktuell. Från och med den 1 april 2022 kommer tillverkningsscenarier inte längre att stödjas med den inbyggda huvudplaneringsmotorn för Dynamics 365 Supply Chain Management. För tillverkningsscenarier måste kunder använda planeringsoptimering för huvudplanering. Mer information finns i [dokumentationen för planeringsoptimering](../master-planning/planning-optimization/planning-optimization-overview.md). Kunder med lokala distributioner av Dynamics 365 Supply Chain Management kan fortsätta att använda Supply Chain Managements huvudplaneringsmotor för tillverkningsscenarier även efter april 2022. Det sker dock inga fler förbättringar av funktionen. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Borttagna eller föråldrade funktioner i Supply Chain Management version 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Användning av den inbyggda huvudplaneringsmotorn för Supply Chain Management för distributionsscenarier

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | För att förbättra prestanda och minimera inläsning av SQL-databas under huvudplaneringskörning, ersätts den inbyggda huvudplaneringsmotorn för Supply Chain Management med planeringsoptimering. Planeringsoptimering möjliggör snabba planeringskörningar som kan utföras även under kontorstid. Då kan planeraren omedelbart reagera vid ändringar i efterfrågan eller planeringsparametrar. |
| **Ersatt av en annan funktion?**   | Ja, planeringsoptimering kommer att ersätta befintliga inbyggda huvudplaneringsmotorn för Supply Chain Management. |
| **Produktområden som påverkas**         | Supply Chain Management – Huvudplanering |
| **Distribueringsalternativ**              | Endast i molnet. Planeringsoptimering stöds inte för lokala distributioner. |
| **Status**                         | Inaktuell. 1 april 2021 kommer distributionsscenarier inte längre att stödjas med inbyggda Dynamics 365 Supply Chain Management huvudplaneringsmotor. För distributionsscenarier måste kunder använda planeringsoptimering för huvudplanering. Mer information finns i [dokumentationen för planeringsoptimering](../master-planning/planning-optimization/planning-optimization-overview.md). Kunder med lokala distributioner av Dynamics 365 Supply Chain Management kan fortsätta att använda Supply Chain Managements huvudplaneringsmotor för distributionsscenarier efter april 2021. Det sker dock inga fler förbättringar av funktionen. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner

Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]