---
title: Kom igång med kostnadsredovisningstjänst
description: Det här avsnittet innehåller licensieringsinformation och Installationsinstruktioner för kostnadsredovisningstjänst.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276964"
---
# <a name="get-started-with-the-cost-accounting-service"></a>Kom igång med kostnadsredovisningstjänst

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> Funktionen som beskrivs i det här avsnittet är tillgänglig som en del av en privat förhandsversion. Innehållet i det här avsnittet och den funktionalitet som det beskrivs i kan ändras. Mer information om förhandsversioner finns i [Frågor och svar om tjänstuppdateringar för en version](../../fin-ops-core/fin-ops/get-started/one-version.md).

Med hjälp av kostnadsredovisningstjänsten kan du utföra flera lagerredovisning i de kostnadsredovisning som du har skapat. Du kopplar varje redovisning med en kostnadsredovisning till en *konvention*. En konvention är en samling av följande typer av redovisningsprinciper:

- Kostnadsobjekt
- Inmatningsmåttbas
- Antagande för kostnadsflöde
- Kostnadselement

> [!NOTE]
> Även när du har aktiverat kostnadsredovisningstjänsten kan du fortfarande göra lagerredovisningen i Microsoft Dynamics 365 Supply Chain Management som vanligt.

Kostnadsredovisningstjänsten är ett tillägg. För att göra funktionerna tillgängliga måste du installera det från Microsoft Dynamics Lifecycle Services (LCS). Därför kan du välja att utvärdera den i en testmiljö innan du aktiverar den för produktionsmiljöer.

Kostnadsredovisningstjänsten stöder för närvarande inte alla kostnads hanteringsfunktioner som är inbyggda i Dynamics 365 Supply Chain Management. Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen ska uppfylla dina krav.

## <a name="licensing"></a>Licensiering

Kostnadsredovisningstjänsten licensieras tillsammans med de standardfunktioner i lagerredovisningen som är tillgängliga för Supply Chain Management. Du behöver inte köpa ytterligare en licens för att kunna använda kostnadsredovisningstjänsten.

## <a name="install-the-add-in"></a>Installera tillägget

> [!IMPORTANT]
> För att kunna använda kostnadsredovisningstjänsten måste du ha en LCS hög tillgänglighetsmiljö (inte en OneBox-miljö) och du måste köra Dynamics 365 Supply Chain Management version 10.0.11 eller senare.

Om du vill använda kostnadsredovisningstjänsten installerar du tillägget kostnadsredovisningstjänst för Supply Chain Management enligt beskrivningen i följande procedur.

1. Logga in på LCS.

1. Gå till **Hantering av förhandsgranskningsfunktioner**.

1. Välj plustecknet (**+**).

1. I fältet **kod** anger du betanyckeln för tillägget för kostnadsredovisningstjänsten. (Du bör ha tagit emot nyckeln via e-post.)

1. Välj **Avblockera**.

1. Öppna LCS-miljön där du vill lägga till tjänsten.

1. Gå till **Fullständiga detaljer**.

1. Bläddra till snabbfliken **miljötillägg**.

1. Välj **installera ett nytt tillägg**.

1. Välj **kostnadsredovisningstjänst**.

1. Följ installationsguiden och godkänn villkoren.

1. Välj **Installera**.

1. På snabbfliken **Miljötillägg** bör du se att kostnadsredovisningstjänsten installeras. Efter några minuter bör statusen ändras från **installera** till **installerad**. (Du kan behöva uppdatera sidan för att se ändringen.) Vid den tidpunkten är kostnadsredovisningstjänsten klar för användning.

## <a name="set-up-the-integration"></a>Inställning och integrering

Så här ställer du in integrationen mellan kostnadsredovisningstjänsten och Dynamics 365 Supply Chain Management:

1. Gå till **Systemadministration > Funktionshantering**.

1. Välj **Sök efter uppdateringar**.

1. Öppna fliken **alla** och sök efter funktionen *kostnadsredovisningstjänst*.

1. Välj **Aktivera nu**.

1. Gå till **Kostnadsredovisning > kostnadsredovisningstjänst > inställningar > parametrar för kostnadsredovisningtjänst > integrationsparametrar**.

1. I fälten **App-ID** anger du följande kod:<br> 08231eb2-a501-4edb-b3c5-aede5e5e0c3f

1. I fältet **Datatjänstslutpunkt** anger du följande URL:<br>https://operationsdataservice.operations365.dynamics.com/

1. I fältet **Slutpunkt för kostnadsredovisningstjänst** anger du följande URL:<br>https://costaccountingservice.operations365.dynamics.com/

1. Kostnadsredovisningstjänsten är nu klar att användas.

## <a name="related-resources"></a>Relaterade resurser

[Startsida för kostnadsredovisningstjänst](cost-accounting-service-home.md)
