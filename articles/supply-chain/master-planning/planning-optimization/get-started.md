---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 05/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 04b39469ccf4f088bb33bdfc73ce40eece6f5f2e
ms.sourcegitcommit: cde71bc7d14ea6cdff2c4e991057d39a6a0473d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2020
ms.locfileid: "3887274"
---
# <a name="get-started-with-planning-optimization"></a>Kom igång med planeringsoptimering

[!include [banner](../../includes/banner.md)]

Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Microsoft Dynamics 365 Supply Chain Management. Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav. Som standard är funktionen planeringsoptimering inte aktiverad i Dynamics Lifecycle Services (LCS). Därför har du möjlighet att utföra utvärderingen innan den är aktiverad.

Planeringsoptimering kommer till slut att ersätta befintliga inbyggda planeringsmotorn för Supply Chain Management.

Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering. Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).

### <a name="availability"></a>Tillgänglighet
Planeringsoptimering är för närvarande tillgänglig i följande Azure-områden: USA, Kanada, Europa, Storbritannien och Australien. Om du försöker installera tillägget från ett annat geografiskt område visas ett meddelande om att detta geografiska område inte stöds.

Observera att planeringsoptimering inte har stöd för lokala distributioner av Dynamics 365 Supply Chain Management.

### <a name="licensing"></a>Licensiering

Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.

### <a name="install-the-add-in"></a>Installera tillägget

Om du vill använda planeringsoptimering installerar du tillägget för planeringsoptimering för Dynamics 365 Supply Chain Management. Du kan komma åt tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.

> [!NOTE]
> Kravet på planeringsoptimering är en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare. Om du försöker installera tillägget i en OneBox-miljö kommer installationen inte att slutföras och du måste avbryta installationen.

1. Logga in på LCS och öppna den önskade miljön.
1. Gå till **Fullständiga detaljer**.
1. Bläddra till snabbfliken **miljötillägg**.
1. Välj **installera ett nytt tillägg**.
1. Välj **Rådgivning om optimering**.
1. Följ installationsguiden och godkänn villkoren.
1. Välj **Installera**.
1. På snabbfliken **miljötillägg** ser du till att planeringsoptimeringen installeras.
1. När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan). När installationen är klar kan du aktivera planeringsoptimering i Dynamics 365 Supply Chain Management.

### <a name="planning-optimization-integration"></a>Planera optimeringsintegration

Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för planeringsoptimering**.

#### <a name="connection-status"></a>Anslutningsstatus

Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten. Följande tabell visar de möjliga värdena.

| Anslutningsstatus | Beskrivning | Kan planeringsoptimering användas? |
|---|---|---|
| Ansluten | En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management. | Ja |
| Aktiverar anslutning | En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu. | Nej |
| Frånkopplad | Det finns ingen anslutning till planeringsoptimeringstjänsten. Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet. | Nej |
| Inaktiverar anslutning | En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu. | Nej |
| Hämtar status | Systemet väntar på statusinformation från planeringsoptimeringstjänsten. | Nej |

#### <a name="the-use-planning-optimization-option"></a>Alternativet Använd planeringsoptimering

Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:

- **Ja** – planeringsoptimering används för huvudplanering.
- **Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.

> [!NOTE]
> Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.

### <a name="integration-with-the-setup"></a>Integration med inställningen

Om förhandsgranskningen av planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering. I det här fallet påverkas huvudplaneringens resultat och funktioner.

## <a name="additional-resources"></a>Ytterligare resurser

[Villkor för förhandsgranskning](https://go.microsoft.com/fwlink/?linkid=2015274)

[Planeringsoptimering – översikt](planning-optimization-overview.md)

[Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)
