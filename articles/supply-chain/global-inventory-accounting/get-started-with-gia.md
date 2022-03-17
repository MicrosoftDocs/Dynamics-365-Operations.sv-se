---
title: Kom i gång med Global lagerredovisning
description: I det här avsnittet beskrivs hur du kommer igång med global lagerredovisningen.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88f1e9ef8c8b2aa494c44ea3b33713adc470eb96
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384807"
---
# <a name="get-started-with-global-inventory-accounting"></a>Kom i gång med Global lagerredovisning

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Global lagerredovisning låter dig utföra flera lagerredovisningar i de globala lagerredovisningar som du har skapat. Du kopplar varje redovisning med en Global lagerredovisning till en *konvention*. En konvention är en samling av följande typer av redovisningsprinciper:

- Kostnadsobjekt
- Inmatningsmåttbas
- Antagande för kostnadsflöde
- Kostnadselement

> [!NOTE]
> Även när du har aktiverat Global lagerredovisning kan du fortfarande göra lagerredovisningen i Microsoft Dynamics 365 Supply Chain Management som vanligt.

Global lagerredovisning är ett tillägg. För att göra funktionerna tillgängliga måste du installera det från Microsoft Dynamics Lifecycle Services (LCS). Därför kan du välja att utvärdera den i en testmiljö innan du aktiverar den för produktionsmiljöer.

Global lagerredovisning har för närvarande inte stöd för alla kostnadshanteringsfunktioner som är inbyggda i Supply Chain Management. Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen ska uppfylla dina krav.

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>Så här hämtar du offentlig förhandsgranskning av global lagerredovisning

> [!IMPORTANT]
> Om du vill använda global lagerredovisning måste du ha en LCS-aktiverad miljö med hög tillgänglighet (inte en OneBox-miljö). Du måste dessutom köra Supply Chain Management version 10.0.19 eller senare.

Om du vill registrera dig för offentlig förhandsgranskning av global lagerredovisning skickar du ditt LCS-miljö-ID med e-post till [Global lagerredovisning teamet](mailto:GlobalInvAccount@microsoft.com). När du har godkänts för programmet skickar teamet ett uppföljningsmeddelande med en nyckel för Global lagerredovisning och dina tjänsteslutpunkter. När du har fått nyckeln kan du [installera tillägget](#install).

## <a name="licensing"></a>Licensiering

Global lagerredovisning licensieras tillsammans med de standardfunktioner i lagerredovisningen som är tillgängliga för Supply Chain Management. Du behöver inte köpa ytterligare en licens för att kunna använda Global lagerredovisning.

## <a name="prerequisites"></a>Förutsättningar

### <a name="set-up-microsoft-power-platform-integration"></a>Ställ in Microsoft Power Platform-integrering

Innan du kan aktivera tilläggsfunktionen måste du integrera Microsoft Power Platform med följande steg.

1. Öppna LCS-miljön där du vill lägga till tjänsten.
1. Gå till **Fullständiga detaljer**.
1. I avsnittet **Power Platform-integrering** väljer du **Konfigurera**.
1. Markera kryssrutan i dialogrutan **Inställning av Power platform miljö** och välj sedan **Inställningar**. Normalt tar inställningen mellan 60 och 90 minuter.
1. När inställningen av Microsoft Power Platform miljön är klar, visar sidan namnet på din miljö. Dessutom visar avsnittet **Power Platform-integration** visar instruktionen, "Power Platform miljöinställningen är klar." Global lagerredovisning behöver inte ha något program för global lagerredovisning.

Mer information finns i [Aktivera efter utveckling av miljön](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

### <a name="set-up-dataverse"></a>Ställ in Dataverse

Innan du ställer in Dataverse lägger du till serviceprinciperna för global lagerredovisning till din innehavare genom att följa stegen nedan.

1. Installera Azure AD-modul för Windows PowerShell v2 enligt beskrivningen i [Installera Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2).
1. Kör följande PowerShell-kommando.

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

Skapa sedan programanvändare för Global lagerredovisning i Dataverse genom att följa stegen nedan.

1. Öppna URL-adressen för din Dataverse miljö.
1. Gå till **Avancerade inställningar \> System \> Säkerhet \> Användare** och skapa en programanvändare. Använd fältet **Vy** för att ändra sidvisningen till *appanvändare*.
1. Välj **Ny**.
1. Ange fältet **App-ID** till *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.
1. Välj **Tilldela roll** och välj sedan *Systemadministratör*. Om det finns en roll med namnet *Common Data Service Användare* väljer du den också.
1. Upprepa föregående steg, men ställ in fältet **Program-ID** på *5f58fc56-0202-49a8-ac9e-0946b049718b*.

Mer information finns i [Skapa en appanvändare](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

Om standardspråket i installationen Dataverse inte är engelska följer du dessa anvisningar.

1. Gå till **Avancerad inställning \> Administration \> Språk**.
1. Välj *Engelska* (*LanguageCode=1033*) och sedan **Verkställ**.

## <a name="install-the-add-in"></a><a name="install"></a>Installera tillägget

Följ dessa steg för att installera tillägget så att du kan använda global lagerredovisning.

1. [Logga in](#sign-up) för offentlig förhandsgranskning av global lagerredovisning.
1. Logga in på [LCS](https://lcs.dynamics.com/Logon/Index).
1. Gå till **Hantering av förhandsgranskningsfunktioner**.
1. Välj plustecknet (**+**).
1. I fältet **kod** anger du betanyckeln för tillägget för Global lagerredovisning. (Du bör ha fått nyckeln via e-post när du har registrerat dig.)
1. Välj **Avblockera**.
1. Öppna LCS-miljön där du vill lägga till tjänsten.
1. Gå till **Fullständiga detaljer**.
1. Gå till **Power Platform-integration** och välj **Inställningar**.
1. Markera kryssrutan i dialogrutan **Inställning av Power platform miljö** och välj sedan **Inställningar**. Normalt tar inställningen mellan 60 och 90 minuter.
1. När inställningen av Microsoft Power Platform-miljön är klar väljer du på snabbfliken **Miljötillägg** välj **Installera ett nytt tillägg**.
1. Välj **Global lagerredovisning**.
1. Följ installationsguiden och godkänn villkoren.
1. Välj **Installera**.
1. På snabbfliken **Miljötillägg** bör du se att Global lagerredovisning installeras. Efter några minuter bör statusen ändras från *installera* till *installerad*. (Du kan behöva uppdatera sidan för att se ändringen.) Vid den tidpunkten är Global lagerredovisning klar för användning.

## <a name="set-up-the-integration"></a>Inställning och integrering

Följ anvisningarna nedan och ställ in integreringen mellan Global Lagerredovisning och Supply Chain Management.

1. Logga in på Supply Chain Management.
1. Gå till **Systemadministration \> Funktionshantering**.
1. Välj **Sök efter uppdateringar**.
1. På fliken **Alla** söker du efter den funktion som kallas *(Förhandsversion) Global lagerredovisning*.
1. Välj **Aktivera nu**.
1. Gå till **Global lagerredovisning \> Inställningar \> Parametrar för global lagerredovisning \> Integrationsparametrar**.
1. I fälten **Datatjänstslutpunkt** och **Slutpunkt för global lagerredovisning** ange webbadresserna från det e-postmeddelande som Global lagerredovisning-teamet skickade när du registrerade dig för förhandsgranskningen.

Global lagerredovisning är nu klar att användas.
