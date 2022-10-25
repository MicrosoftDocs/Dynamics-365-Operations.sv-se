---
title: Sensor Data Intelligence-startsida
description: Den här artikeln ger en översikt över Sensor Data Intelligence. Organisationer kan använda den här funktionen för att köra affärsprocesser i Microsoft Dynamics 365 Supply Chain Management, baserat på IoT (Sakernas internet) från maskiner och utrustning i produktionsgolvet.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: ba030364056db8b0524de22aacbc6528ef77813b
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689868"
---
# <a name="sensor-data-intelligence-home-page"></a>Sensor Data Intelligence-startsida

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Sensor Data Intelligence för Microsoft Dynamics 365 Supply Chain Management gör det möjligt för organisationer att driva affärsprocesser inom Supply Chain Management, baserat på Sakernas internet (IoT)-signaler från maskiner och utrustning på produktionsgolvet. Det är en uppdaterad version av *IoT-intelligens*-funktionen som tidigare var tillgänglig för Supply Chain Management.

Sensor Data Intelligence låter dig utföra följande uppgifter:

- Samla in information från maskiner och utrustning för att uppdatera värden från räknare för underhållstillgångar i Supply Chain Management och köra förebyggande underhåll.
- Konfigurera lösningen med en enkel guide, i stället för att manuellt installera och konfigurera komponenter i Microsoft Dynamics Lifecycle Services (LCS).
- Distribuera komponenter för ditt eget abonnemang, så att du har mer flexibilitet när du hanterar Azure-komponenter.
- Konfigurera, anpassa och utöka lösningen som affärslogik som körs med komponenter i Azure. Komponenterna hanteras nu på ditt eget abonnemang. Därför kan du anpassa dem efter eget behov.

## <a name="business-scenarios"></a>Affärsscenarier

Med Sensor Data Intelligence kan du använda flera olika typer av funktioner, som alla representeras av ett specifikt *scenario* i systemet. Varje scenario innehåller en specialiserad uppsättning konfigurationsalternativ i systemet, enligt vad som beskrivs i tabellen nedan.

| Scenario | Beskrivning |
|---|---|
| [Tillgångsdriftstopp](sdi-scenario-asset-downtime.md) | Spåra maskintillgångarns effektivitet korrekt med hjälp av sensordata för att spåra maskinens drifttid. |
| [Tillgångsunderhåll](sdi-scenario-asset-maintenance.md) | Minimera underhållskostnaderna och förläng anläggningens livslängd genom att förbättra underhållsplaner baserade på sensoravläsningar av kritiska kontrollpunkter för maskintillgångar. |
| [Maskinstatus](sdi-scenario-equipment-downtime.md) | Se till att operationen blir effektiv genom att använda sensoravläsningar för att meddela planerarna om maskinavbrott och ge alternativ för att begränsa eventuella förseningar. |
| [Produktkvalitet](sdi-scenario-product-quality.md) | Säkerställa kvaliteten på produktbatcharna genom att jämföra sensoravläsningar för de faktiska egenskaperna för varje produktbatch, till exempel temperatur eller anpassade kvalitetsmått. Systemet meddelar användarna när avvikelser inträffar. |
| [Produktionsförseningar](sdi-scenario-production-delays.md) | Använd sensoravläsningar om du vill jämföra faktisk cykeltid med planerad cykeltid, och meddela arbetsledare när produktionen inte stämmer i tid. Därefter kan arbetsledare säkerställa maximal effektivitet. |

## <a name="architecture"></a>Arkitektur

Följande arkitekturdiagram ger en översikt över lösningen och dess komponenter.

![Sensor Data Intelligence arkitekturdiagram.](media/sdi-architecture.png "Sensor Data Intelligence arkitekturdiagram")
