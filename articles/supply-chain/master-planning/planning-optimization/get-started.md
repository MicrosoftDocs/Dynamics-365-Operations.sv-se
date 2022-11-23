---
title: Kom i gång med huvudplanering
description: Denna artikel beskriver hur du använder funktionen huvudplanering i Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 4b986461e90b356580da8a136c1da95e7dc64696
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780418"
---
# <a name="get-started-with-master-planning"></a>Kom i gång med huvudplanering

[!include [banner](../../includes/banner.md)]

Huvudplaneringen i Supply Chain Management tillhandahålls av en extern tjänst som kallas tillägget Planeringsoptimering för Dynamics 365 Supply Chain Management. Detta ämne förklarar hur du hämtar och ställer in den tjänster.

## <a name="availability"></a>Tillgänglighet

Planeringsoptimering är för närvarande tillgänglig i följande Azure-områden: USA, Kanada, Brasilien, Europa, Frankrike, Storbritannien, Norge, Schweiz, Australien, Asien och Stillahavsområdet, Japan samt Indien. Om du försöker installera tillägget från ett annat geografiskt område visas ett meddelande om att detta geografiska område inte stöds. Mer information om Azure-områden och relaterade regioner finns i [Azure-områden](https://azure.microsoft.com/global-infrastructure/geographies/#geographies).

Observera att Planeringsoptimering inte har stöd för lokala distributioner av Dynamics 365 Supply Chain Management.

## <a name="licensing"></a>Licensiering

Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda Planeringsoptimering.

## <a name="install-and-enable-planning-optimization"></a>Installera och aktivera Planeringsoptimeringen

Om du vill använda Planeringsoptimering måste du kontrollera att alla förutsättningar finns i systemet och sedan aktivera licensnyckeln och installera tillägget Planeringsoptimering för Dynamics 365 Supply Chain Management.

### <a name="prerequisites"></a>Förutsättningar

Innan du installerar tillägget Planeringsoptimering måste följande förutsättningar finnas på plats:

- Du måste köra Supply Chain Management på en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare. Om du försöker installera tillägget i en OneBox-miljö kommer installationen inte att slutföras och du måste avbryta installationen.

- Ditt system måste ha ställts in för Power Platform-integrering. Mer information finns i [Microsoft Power Platform-integrering med appar för ekonomi och drift](../../../fin-ops-core/dev-itpro/power-platform/overview.md).

### <a name="enable-the-planning-optimization-license"></a>Aktivera licensen för Planeringsoptimeringen

Om du vill använda Planeringsoptimering måste du aktivera dess konfigurationsnyckel. Så här går det till:

1. Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. På fliken **Konfigurationsnycklar** markera kryssrutan för **Planeringsoptimering**.
1. Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="install-the-planning-optimization-add-in"></a>Installera tillägget Planeringsoptimering

Du måste installera tillägget från LCS-projektet och aktivera funktionen för Planeringsoptimering från användargränssnittet för Supply Chain Management.

För att installera tillägget Planeringsoptimering:

1. Logga in på LCS och öppna den önskade miljön.
1. Gå till **Fullständiga detaljer**.
1. Bläddra till snabbfliken **miljötillägg**.
1. Välj **installera ett nytt tillägg**.
1. Välj **Rådgivning om optimering**.
1. Följ installationsguiden och godkänn villkoren.
1. Välj **Installera**.
1. På snabbfliken **miljötillägg** ser du till att Planeringsoptimeringen installeras.
1. När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan). När installationen är klar kan du aktivera Planeringsoptimering i Dynamics 365 Supply Chain Management.

Det huvudsakliga syftet med tillägget att installera tilläggsprogrammet för Planeringsoptimering är att ansluta tjänsten och miljön. Därför måste du installera tillägget separat för varje miljö där du vill använda Planeringsoptimering, oavsett vilken kod som flyttas mellan miljöerna.

## <a name="integrate-planning-optimization-with-your-system"></a>Integrera Planeringsoptimering med systemet

Om du vill konfigurera om tillägget för Planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för Planeringsoptimering**.

### <a name="connection-status"></a>Anslutningsstatus

Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och Planeringsoptimerinstjänsten. Följande tabell visar de möjliga värdena.

| Anslutningsstatus | Beskrivning | Kan Planeringsoptimering användas? |
|---|---|---|
| Ansluten | En anslutning har upprättats mellan Planeringsoptimerinstjänsten och Supply Chain Management. | Ja |
| Aktiverar anslutning | En begäran om att aktivera anslutningen till Planeringsoptimerinstjänsten pågår just nu. | Nej |
| Frånkopplad | Det finns ingen anslutning till Planeringsoptimerinstjänsten. Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i denna artikel. | Nej |
| Inaktiverar anslutning | En begäran om att inaktivera anslutningen till Planeringsoptimerinstjänsten pågår just nu. | Nej |
| Hämtar status | Systemet väntar på statusinformation från Planeringsoptimerinstjänsten. | Nej |

### <a name="the-use-planning-optimization-option"></a>Alternativet Använd Planeringsoptimering

Inställningen av alternativet **Använd Planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:

- **Ja** – Planeringsoptimering används för huvudplanering.
- **Nej** – den inaktuella huvudplaneringsmotorn används för huvudplanering.

Den här inställningen gäller för alla juridiska personer (företag). Det är inte möjligt att använda Planeringsoptimering i vissa juridiska personer och den inaktuella huvudplaneringsmotorn i andra juridiska personer.

> [!NOTE]
> Om befintliga planeringsbatchjobb som har skapats för den inaktuella huvudplaneringsmotorn utlöses medan alternativet **Använd Planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.

### <a name="integration-with-the-setup"></a>Integrering med inställningen

Om Planeringsoptimeringen är aktiverad görs huvudplanering med tillägget Planeringsoptimering. I det här fallet påverkas huvudplaneringens resultat och funktioner.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
