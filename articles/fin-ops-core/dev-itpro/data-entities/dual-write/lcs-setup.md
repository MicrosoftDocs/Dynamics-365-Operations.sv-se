---
title: Inställning av dubbelriktad skrivning från Lifecycle Services
description: I den här artikeln beskrivs hur du ställer in en dubbelriktad anslutning från Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 05/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: a002bae22044ea10be30340a87a191305f6c6b92
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111983"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Inställning av dubbelriktad skrivning från Lifecycle Services

[!include [banner](../../includes/banner.md)]



I den här artikeln beskrivs hur du aktiverar en dubbelriktad skrivning från Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Förutsättningar

Kunder måste slutföra Power Platform-integreringen enligt beskrivningen i följande avsnitt:

- Om du ännu inte använder Microsoft Power Platform men vill expandera dina ekonomi- och driftmiljöer genom att lägga till plattformsfunktionerna, se då [Power Platform-integrering- Aktivera under miljödistributionen](../../power-platform/enable-power-platform-integration.md#enable-during-deploy).
- Om du redan har Dataverse- och Power Platform-miljöer och vill ansluta dessa till ekonomi- och driftmiljöer, se då [Power Platform-integrering – Aktivera efter distribution av miljön](../../power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="set-up-dual-write-for-new-or-existing-dataverse-environments"></a>Ställ in dubbelriktad för ny eller befintlig Dataverse-miljö

Följ dessa steg när du vill ställa in dubbelriktad skrivning från LCS **miljöinformation**:

1. På sidan **Miljöinformation** visa avsnittet **Power Platform-integrering**.

2. Välj knappen **dubbelriktad skrivning för app**.

    ![Power Platform-integrering.](media/powerplat_integration_step2.png)

3. Granska villkoren och markera sedan **Konfigurera**.

4. Välj **OK** om du vill fortsätta.

5. Du kan övervaka förloppet genom att regelbundet uppdatera sidan för miljöinformation. Inställningen tar normalt 30 minuter eller mindre.  

6. När inställningen är slutförd visas ett meddelande om processen lyckades eller om fel uppstår. Om inställningen misslyckades visas ett relaterat felmeddelande. Du måste åtgärda eventuella fel innan du går vidare till nästa steg.

7. Välj **Länk till Power Platform miljö** om du vill skapa en länk mellan Dataverse och den aktuella miljöns databaser. Detta tar normalt mindre än 5 minuter.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Länk till Power Platform-miljö.":::

8. När länkningen är slutförd visas en hyperlänk. Använd länken för att logga in i administrationsområdet för dubbelriktad skrivning i Ekonomi och Drift-miljön. Därifrån kan du ställa in enhetsmappningar.

## <a name="linking-mismatch"></a>Koppla matchningsfel

Det är möjligt att din arbetsmiljö är länkad till en Dataverse instans medan LCS inte har ställts in för Power Platform integration. Detta kan leda till oväntade beteende. Det rekommenderas att LCS-miljödetaljer matchar det du är ansluten till i dubbelriktad skrivning så att samma anslutning kan användas av affärshändelser, virtuella tabeller och tillägg.

Om din miljö har en matchningsfel, visar LCS en varning som liknar följande exempel på din miljöinformationssida "Microsoft har upptäckt att din miljö är kopplad via Webbplatsskrivning till en annan destination än den som angetts i Power Platform integreringen, och det rekommenderas inte".

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Power Platform integreringslänk stämmer inte överens.":::

Om du får den här varningen försöker du med någon av följande lösningar:

- Om din LCS-miljö aldrig har ställts in för Power Platform integration kan du ansluta till Dataverse instansen som är konfigurerad i dubbelriktad skrivning genom att följa instruktionerna i den här artikeln.
- Om din LCS-miljö redan är inställd för Power Platform integration, bör du koppla bort dual-write och återansluta den till den som specificeras av LCS med hjälp av [Scenario: Återställ eller ändra länkning](relink-environments.md#scenario-reset-or-change-linking).

Tidigare var ett manuellt alternativ för supportbegäran tillgängligt, men det var före alternativen 1 ovan.  Microsoft stöder inte längre manuella omkopplingar av förfrågningar via supportbegäran.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

