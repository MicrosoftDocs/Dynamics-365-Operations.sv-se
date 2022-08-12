---
title: Kom i gång med Global lagerredovisning
description: I denna artikel beskrivs hur du kommer igång med global lagerredovisning.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 463a66002ec7a6536c9ff829f9ea2c3734138eae
ms.sourcegitcommit: 6221a25f81aa83ab335de7cb6b6c3014dbec0116
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/19/2022
ms.locfileid: "9177161"
---
# <a name="get-started-with-global-inventory-accounting"></a>Kom i gång med Global lagerredovisning

[!include [banner](../includes/banner.md)]

Global lagerredovisning låter dig utföra flera lagerredovisningar i de globala lagerredovisningar som du har skapat. Du kopplar varje redovisning med en Global lagerredovisning till en *konvention*. En konvention är en samling av följande typer av redovisningsprinciper:

- Kostnadsobjekt
- Inmatningsmåttbas
- Antagande för kostnadsflöde
- Kostnadselement

> [!NOTE]
> Även när du har aktiverat Global lagerredovisning kan du fortfarande göra lagerredovisningen i Microsoft Dynamics 365 Supply Chain Management som vanligt.

Global lagerredovisning är ett tillägg. För att göra funktionerna tillgängliga måste du installera det från Microsoft Dynamics Lifecycle Services (LCS). Därför kan du välja att utvärdera den i en testmiljö innan du aktiverar den för produktionsmiljöer.

Global lagerredovisning har för närvarande inte stöd för alla kostnadshanteringsfunktioner som är inbyggda i Supply Chain Management. Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen ska uppfylla dina krav.

## <a name="how-to-get-the-global-inventory-accounting-add-in"></a><a name="sign-up"></a>Så här hämtar du tillägget för global lagerredovisning

> [!IMPORTANT]
> Om du vill använda global lagerredovisning måste du ha en LCS-aktiverad miljö med hög tillgänglighet (inte en OneBox-miljö). Du måste dessutom köra Supply Chain Management version 10.0.19 eller senare.

### <a name="supply-chain-management-version-10019-to-10026"></a>Supply Chain Management version 10.0.19 till 10.0.26

Om du vill installera Global Lagerredovisning för Supply Chain Management version 10.0.19 till 10.0.26 ska du börja med att [installera tillägget](#install). Skicka sedan ditt LCS-miljö-ID och ditt företagsnamn via e-post till [teamet för global lagerredovisning](mailto:GlobalInvAccount@microsoft.com). Teamet kommer att skicka ett uppföljningsmeddelande till dig via e-post som innehåller dina tjänsteslutpunkter för Global lagerredovisning.

### <a name="supply-chain-management-version-10027-and-later"></a>Supply Chain Management version 10.0.27 eller senare

Om du vill installera Global Lagerredovisning för Supply Chain Management version 10.0.27 eller senare behöver du bara [installera tillägget](#install). För dessa versioner av Supply Chain Management kommer slutpunkterna för den globala lagerredovisningstjänsten att ställas in automatiskt, så du behöver inte hitta dem manuellt. Om du upplever problem när du konfigurerar tillägget kan du kontakta det [globala lagerredovisningsteamet](mailto:GlobalInvAccount@microsoft.com).

## <a name="licensing"></a>Licensiering

Global lagerredovisning licensieras tillsammans med de standardfunktioner i lagerredovisningen som är tillgängliga för Supply Chain Management. Du behöver inte köpa ytterligare en licens för att kunna använda Global lagerredovisning.

## <a name="prerequisites"></a>Förutsättningar

### <a name="set-up-microsoft-power-platform-integration"></a>Ställ in Microsoft Power Platform-integrering

Innan du kan aktivera tilläggsfunktionen måste du integrera Microsoft Power Platform med följande steg.

1. Öppna LCS-miljön där du vill lägga till tjänsten.
1. Gå till **Fullständiga detaljer**.
1. I avsnittet **Power Platform-integrering** väljer du **Konfigurera**.
1. Markera kryssrutan i dialogrutan **Inställning av Power platform miljö** och välj sedan **Inställningar**. Normalt tar inställningen mellan 60 och 90 minuter.
1. När inställningen av Microsoft Power Platform miljön är klar, visar sidan namnet på din miljö. Dessutom visar avsnittet **Power Platform-integrering** visar instruktionen, "Power Platform miljöinställningen är klar." Global lagerredovisning behöver inte ha något program för global lagerredovisning.

Mer information finns i [Aktivera efter utveckling av miljön](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="install-or-update-the-add-in-and-solution"></a><a name="install"></a>Installera eller uppdatera tillägget och lösningen

Använd följande procedur för att installera eller uppdatera tillägget och lösningen för global lagerredovisning. Den del av proceduren du ska följa beror på om du installerar för första gången eller bara behöver uppdatera lösningen för en befintlig installation.

- Om du aldrig har installerat tillägget tidigare följer du hela proceduren för att installera både tillägget och lösningen.
- Om du redan använder global lagerredovisning men behöver uppdatera lösningen i [administrationscentret för Power Platform](https://admin.powerplatform.microsoft.com), ska du bara utföra steg 6 och hoppa över alla andra steg.

För att installera eller uppdatera tillägget och lösningen:

1. Logga in på [LCS](https://lcs.dynamics.com/Logon/Index).
1. Öppna LCS-miljön där du vill lägga till tjänsten.
1. Gå till **Fullständiga detaljer**.
1. Gå till **Power Platform-integrering** och välj **Inställningar**.
1. Markera kryssrutan i dialogrutan **Inställning av Power platform miljö** och välj sedan **Inställningar**. Normalt tar inställningen mellan 60 och 90 minuter.
1. När inställningen av Microsoft Power Platform-miljön är klar loggar du in på [administrationscentret för Power Platform](https://admin.powerplatform.microsoft.com) och installerar eller uppdaterar sedan tillägget för global lagerredovisning genom att utföra följande steg:
   1. Välj den miljö där du vill installera eller uppdatera lösningen.
   1. Välj **Dynamics 365-program**.
   1. Välj **Installera program**.
   1. Välj **Dynamics 365 Global lagerredovisning**.
   1. Klicka på **Nästa** när du vill installera.
1. När lösningen är helt installerad går du tillbaka till LCS-miljön. På snabbfliken **Miljötillägg** välj **Installera ett nytt tillägg**.
1. Välj **Global lagerredovisning**.
1. Följ installationsguiden och godkänn villkoren.
1. Välj **Installera**.
1. På snabbfliken **Miljötillägg** bör du se att Global lagerredovisning installeras. Efter några minuter bör statusen ändras från *installera* till *installerad*. (Du kan behöva uppdatera sidan för att se ändringen.) Vid den tidpunkten är Global lagerredovisning klar för användning.

Om standardspråket i installationen Dataverse inte är engelska följer du dessa anvisningar:

1. Gå till **Avancerad inställning \> Administration \> Språk**.
1. Välj *Engelska* (*LanguageCode=1033*) och sedan **Verkställ**.

## <a name="set-up-the-integration"></a>Inställning och integrering

Följ anvisningarna nedan och ställ in integreringen mellan Global Lagerredovisning och Supply Chain Management.

1. Logga in på Supply Chain Management.
1. Gå till **Systemadministration \> Funktionshantering**.
1. Välj **Sök efter uppdateringar**.
1. På fliken **Alla** söker du efter den funktion som kallas *(Förhandsversion) Global lagerredovisning*.
1. Välj **Aktivera nu**.
1. Gå till **Global lagerredovisning \> Inställningar \> Parametrar för global lagerredovisning \> Integreringsparametrar**.
1. Beroende på vilken version av Supply Chain Management du kör ska du utföra ett av följande steg:
    - **Supply Chain Management version 10.0.19 till 10.0.26**: I fälten **Slutpunkt för datatjänst** och **Slutpunkt för global lagerredovisning** anger du de URL:er som tidigare skickades till dig via e-post från teamet för global lagerredovisning (se också [Så här skaffar du tillägget för global lagerredovisning](#sign-up)).
    - **Supply Chain Management version 10.0.27 och senare**: Du behöver inte ange slutpunkterna, så du kan hoppa över detta steg.

Global lagerredovisning är nu klar att användas.
