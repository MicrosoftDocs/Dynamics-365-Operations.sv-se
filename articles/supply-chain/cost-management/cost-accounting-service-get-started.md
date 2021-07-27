---
title: Kom igång med kostnadsredovisningstjänsten (privat förhandsvisning)
description: Det här avsnittet innehåller licensieringsinformation och Installationsinstruktioner för kostnadsredovisningstjänst.
author: AndersGirke
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 207c9dfe9e49b845d2c98040c1571099e01b43f7
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "6337706"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a>Kom igång med kostnadsredovisningstjänsten (privat förhandsvisning)

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

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a>Så här kommer du igång med kostnadsredovisningstjänsten (privat förhandsvisning)

> [!IMPORTANT]
> För att kunna använda kostnadsredovisningstjänsten måste du ha en LCS hög tillgänglighetsmiljö (inte en OneBox-miljö) och du måste köra Dynamics 365 Supply Chain Management version 10.0.11 eller senare.

Om du vill registrera dig för privatförhandsvisning för kostnadsredovisningstjänsten skickar du ditt ID för LCS-miljö via e-post till [Kostnadsredovisningstjänst (privat förhandsvisning)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29). När vi godkänner dig för programmet kommer vi att skicka ett uppföljningsmail till dig som innehåller en betanyckel för kostnadsredovisningtjänsten. När du tar emot betanyckeln kan du fortsätta genom att [installera tillägget](#install).

## <a name="licensing"></a>Licensiering

Kostnadsredovisningstjänsten licensieras tillsammans med de standardfunktioner i lagerredovisningen som är tillgängliga för Supply Chain Management. Du behöver inte köpa ytterligare en licens för att kunna använda kostnadsredovisningstjänsten.

## <a name="install-the-add-in"></a><a name="install"></a>Installera tillägget

Om du vill använda kostnadsredovisningstjänsten installerar du tillägget kostnadsredovisningstjänst för Supply Chain Management enligt beskrivningen i följande procedur.

1. [Registrera dig](#sign-up) för kostnadsredovisningstjänsten (privat förhandsvisning).

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]