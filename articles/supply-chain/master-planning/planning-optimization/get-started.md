---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
manager: AnnBe
ms.date: 01/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 3e0371c6addc0412dc2fc105891b012941e92a06
ms.sourcegitcommit: e5a3c85a322a9216b8f176536d664fef40ae0bec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/17/2020
ms.locfileid: "2971474"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a>Kom igång med planeringsoptimering

Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Microsoft Dynamics 365 Supply Chain Management. Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav. Som standard är funktionen planeringsoptimering inte aktiverad i Dynamics Lifecycle Services (LCS). Därför har du möjlighet att utföra utvärderingen innan den är aktiverad.

Planeringsoptimering kommer till slut att ersätta befintliga inbyggda planeringsmotorn för Supply Chain Management.

Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering. Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).

### <a name="licensing"></a>Licensiering

Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.

### <a name="install-the-add-in"></a>Installera tillägget

Om du vill använda planeringsoptimering installerar du tillägget för planeringsoptimering för Dynamics 365 Supply Chain Management. Du kan komma åt tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.

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

## <a name="related-resources"></a>Relaterade resurser

[Villkor för förhandsgranskning](https://go.microsoft.com/fwlink/?linkid=2015274)

[Rådgivning om optimering – översikt](planning-optimization-overview.md)

[Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)
