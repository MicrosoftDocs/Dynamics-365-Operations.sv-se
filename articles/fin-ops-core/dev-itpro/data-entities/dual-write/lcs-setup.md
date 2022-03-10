---
title: Inställning av dubbelriktad skrivning från Lifecycle Services
description: I det här avsnittet beskrivs hur du ställer in en dubbelriktad anslutning från Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 08/03/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 825d6a4b3462077d0f4b3f4275792ea0fe5152df
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063682"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Inställning av dubbelriktad skrivning från Lifecycle Services

[!include [banner](../../includes/banner.md)]



I det här avsnittet beskrivs hur du aktiverar en dubbelriktad skrivning från Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Förutsättningar

Du måste slutföra Power Platform-integreringen enligt beskrivningen i följande avsnitt:

+ [Power Platform-integrering – Aktivera under utveckling av miljön](../../power-platform/enable-power-platform-integration.md#enable-during-deploy)
+ [Power Platform-integrering – Aktivera efter utveckling av miljön](../../power-platform/enable-power-platform-integration.md#enable-after-deploy)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Ställ in dubbelriktad skrivning för nya Dataverse-miljöer

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

8. När länkningen är slutförd visas en hyperlänk. Använd länken för att logga in på administrationsområdet för dubbelriktad skrivning i Ekonomi och Drift-miljön. Därifrån kan du ställa in enhetsmappningar.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Ställ in dubbelriktad skrivning för en befintlig Dataverse-miljö

Om du vill ställa in dubbelriktad skrivning för en befintlig Dataverse-miljö måste du skapa ett Microsoft [supportärende](../../lifecycle-services/lcs-support.md). Ärendet måste innehålla:

+ Ditt Ekonomi och Drift miljö-ID.
+ Ditt miljönamn från Lifecycle Services.
+ Dataverse organisations-ID eller Power Platform miljö-ID från Power Platform administrationscenter. Begär att ID:t ska vara den instans som används för integrering på din Power Platform-integrering.

> [!NOTE]
> Du kan inte avlänka miljöer med hjälp av LCS. Om du vill ta bort länken för en miljö, öppna arbetsytan **Dataintegrering** i Ekonomi och Drift-miljön och väljer **Ta bort länk**.

## <a name="linking-mismatch"></a>Koppla matchningsfel

Det är möjligt att din LCS-miljö är länkad till en Dataverse instans, medan din skrivmiljö är kopplad till en annan Dataverse instans. Denna koppling av matchningsfel kan orsaka oväntade beteende, och det kan sluta med att data skickas till fel miljö. Den rekommenderade miljön att använda för dubbelriktad skrivning är den som skapas som en del av Power Platform-integreringen, och på längre sikt är detta det enda sättet att upprätta en länk mellan olika miljöer.

Om din miljö har en matchningsfel, visar LCS en varning på din miljöinformationssida, som liknar "Microsoft har upptäckt att din miljö är kopplad via Webbplatsskrivning till en annan destination än den som angetts i Power Platform integreringen, och det rekommenderas inte":

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Power Platform integreringslänk stämmer inte överens.":::

Om du stöter på det här felet finns det två alternativ, baserat på dina behov:

+ [Ta bort länken och koppla om dubbelskrivningsmiljöer (Återställ eller ändra länkning)](relink-environments.md#scenario-reset-or-change-linking) enligt specifikationen på din LCS -miljöinformation. Detta är det bästa alternativet, eftersom du kan köra det utan Microsofts stöd.  
+ Om du vill behålla din länk vid dubbelskrivning kan du be om hjälp från Microsofts support för att ändra Power Platform-integreringen i syfte att använda din befintliga Dataverse-miljö enligt dokumenterat i föregående avsnitt.  

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
