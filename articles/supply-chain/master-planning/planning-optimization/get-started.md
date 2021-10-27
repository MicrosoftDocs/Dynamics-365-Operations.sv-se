---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 8681ef80166f7d5f108c9424b53fa5c6f5324467
ms.sourcegitcommit: fcb1aa39e933216dea9e586b552bce6057f416a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645792"
---
# <a name="get-started-with-planning-optimization"></a>Kom igång med planeringsoptimering

[!include [banner](../../includes/banner.md)]

Som [tidigare presenterade](../../get-started/removed-deprecated-features-scm-updates.md#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios) planeringsoptimeringen till att ersätta den befintliga inbyggda huvudplaneringsmotorn.

Om du använder den inbyggda huvudplaneringsmotorn för närvarande bör du börja planera migreringen för planeringsoptimering nu. Det är viktigt att du startar flyttningen direkt eftersom dina åtgärder kan påverkas när utgångsmetoden är aktiverad. Vi rekommenderar starkt att du slutför migreringen före den 1 december 2020 för att undvika problem med sista minuten när utgången är aktiverad. 

Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Supply Chain Management. Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav. Funktionen för planeringsoptimering är för närvarande inte aktive rad som standard i Dynamics Lifecycle Services (LCS), så du har möjlighet att utföra utvärderingen innan funktionen är aktiverad.

> [!NOTE]
> Du måste begära ett undantag från migrering till planeringsoptimering om huvudplaneringsprocessen inte innehåller någon produktion (huvudplanering genererade planerade produktionsorder) och du behöver den inbyggda huvudplaneringsmotorn utöver version 10.0.15. Från och med version 10.0.16 visas ett felmeddelande i miljöer vid körning av inbyggd huvudplanering utan att planerade tillverkningsorder genereras. Planeringsoptimering ska användas för alla nya distributioner som inte genererar planerade tillverkningsorder under huvudplaneringen. Ägare till befintliga miljöer som kör den inbyggda huvudplaneringsmotorn utan att generera planerade tillverkningsorder får ett e-postmeddelande med information om undantagsprocessen. Vi rekommenderar att du arbetar med en partner för att utvärdera och planera migreringen till planeringsoptimering.

Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering. Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).

## <a name="availability"></a>Tillgänglighet

Planeringsoptimering är för närvarande tillgänglig i följande Azure-områden: USA, Kanada, Europa, Storbritannien, Australien och Asien och Stillahavsområdet, samt Japan. Om du försöker installera tillägget från ett annat geografiskt område visas ett meddelande om att detta geografiska område inte stöds. Mer information om Azure-områden och relaterade regioner finns i [Azure-områden](https://azure.microsoft.com/global-infrastructure/geographies/#geographies).

Observera att planeringsoptimering inte har stöd för lokala distributioner av Dynamics 365 Supply Chain Management.

## <a name="licensing"></a>Licensiering

Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.

## <a name="install-and-enable-planning-optimization"></a>Installera och aktivera planeringsoptimeringen

Om du vill använda Planeringsoptimering måste du kontrollera att alla förutsättningar finns i systemet och sedan aktivera licensnyckeln och installera tillägget Planeringsoptimering för Dynamics 365 Supply Chain Management.

### <a name="prerequisites"></a>Förutsättningar

Innan du installerar tillägget Planeringsoptimering måste följande förutsättningar finnas på plats:

- Du måste köra Supply Chain Management på en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare. Om du försöker installera tillägget i en OneBox-miljö kommer installationen inte att slutföras och du måste avbryta installationen.

- Ditt system måste ha ställts in för Power Platform-integration. Mer information finns i [Microsoft Power Platform-integrering med Finance and Operations-appar](../../../fin-ops-core/dev-itpro/power-platform/overview.md).

### <a name="enable-the-planning-optimization-license"></a>Aktivera licensen för planeringsoptimeringen

Om du vill använda Planeringsoptimering måste du aktivera dess konfigurationsnyckel. Så här går det till:

1. Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. På fliken **Konfigurationsnycklar** markera kryssrutan för **Planeringsoptimering**.
1. Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="install-the-planning-optimization-add-in"></a>Installera tillägget Planeringsoptimering

Du måste installera tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.

För att installera tillägget Planeringsoptimering:

1. Logga in på LCS och öppna den önskade miljön.
1. Gå till **Fullständiga detaljer**.
1. Bläddra till snabbfliken **miljötillägg**.
1. Välj **installera ett nytt tillägg**.
1. Välj **Rådgivning om optimering**.
1. Följ installationsguiden och godkänn villkoren.
1. Välj **Installera**.
1. På snabbfliken **miljötillägg** ser du till att planeringsoptimeringen installeras.
1. När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan). När installationen är klar kan du aktivera planeringsoptimering i Dynamics 365 Supply Chain Management.

Det huvudsakliga syftet med tillägget att installera tilläggsprogrammet för planeringsoptimering är att ansluta tjänsten och miljön. Därför måste du installera tillägget separat för varje miljö där du vill använda planeringsoptimering, oavsett vilken kod som flyttas mellan miljöerna.

## <a name="integrate-planning-optimization-with-your-system"></a>Integrera Planeringsoptimering med systemet

Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för planeringsoptimering**.

### <a name="connection-status"></a>Anslutningsstatus

Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten. Följande tabell visar de möjliga värdena.

| Anslutningsstatus | Beskrivning | Kan planeringsoptimering användas? |
|---|---|---|
| Ansluten | En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management. | Ja |
| Aktiverar anslutning | En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu. | Nej |
| Frånkopplad | Det finns ingen anslutning till planeringsoptimeringstjänsten. Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet. | Nej |
| Inaktiverar anslutning | En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu. | Nej |
| Hämtar status | Systemet väntar på statusinformation från planeringsoptimeringstjänsten. | Nej |

### <a name="the-use-planning-optimization-option"></a>Alternativet Använd planeringsoptimering

Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:

- **Ja** – planeringsoptimering används för huvudplanering.
- **Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.

Den här inställningen gäller för alla juridiska personer (företag). Det är inte möjligt att använda Planeringsoptimering i vissa juridiska personer och den inbyggda huvudplaneringen i andra juridiska personer.

> [!NOTE]
> Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.

### <a name="integration-with-the-setup"></a>Integration med inställningen

Om planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering. I det här fallet påverkas huvudplaneringens resultat och funktioner.

## <a name="additional-resources"></a>Ytterligare resurser

[Villkor för förhandsgranskning](https://go.microsoft.com/fwlink/?linkid=2015274)

[Planeringsoptimering – översikt](planning-optimization-overview.md)

[Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
