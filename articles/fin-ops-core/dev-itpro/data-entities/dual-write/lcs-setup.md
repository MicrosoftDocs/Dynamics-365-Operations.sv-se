---
title: Inställning av dubbelriktad skrivning från Lifecycle Services
description: I det här avsnittet beskrivs hur du ställer in en dubbelriktad anslutning från Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e604e1491bbafa041fa3f52ad0f8b454c63d47de
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359373"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Inställning av dubbelriktad skrivning från Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I det här avsnittet beskrivs hur du aktiverar en dubbelriktad skrivning från Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Förutsättningar

Du måste slutföra Power Platform-integrationen enligt beskrivningen i följande avsnitt:

+ [Power Platform-integration - Aktivera under utveckling av miljön](../../power-platform/overview.md#enable-during-environment-deployment)
+ [Power Platform-integration - Ställ in efter utveckling av miljön](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Ställ in dubbelriktad skrivning för nya Dataverse-miljöer

Följ dessa steg när du vill ställa in dubbelriktad skrivning från LCS **miljöinformation**:

1. På sidan **Miljöinformation** visa avsnittet **Power Platform-integration**.

2. Välj knappen **dubbelriktad skrivning för app**.

    ![Power Platform-integrering.](media/powerplat_integration_step2.png)

3. Granska villkoren och markera sedan **Konfigurera**.

4. Välj **OK** om du vill fortsätta.

5. Du kan övervaka förloppet genom att regelbundet uppdatera sidan för miljöinformation. Inställningen tar normalt 30 minuter eller mindre.  

6. När inställningen är slutförd visas ett meddelande om processen lyckades eller om fel uppstår. Om inställningen misslyckades visas ett relaterat felmeddelande. Du måste åtgärda eventuella fel innan du går vidare till nästa steg.

7. Välj **Länk till Power Platform miljö** om du vill skapa en länk mellan Dataverse och den aktuella miljöns databaser. Detta tar normalt mindre än 5 minuter.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Länk till Power Platform-miljö.":::

8. När länkningen är slutförd visas en hyperlänk. Använd länken för att logga in på administrationsområdet för dubbelriktad skrivning i Finance and Operations-miljön. Därifrån kan du ställa in enhetsmappningar.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Ställ in dubbelriktad skrivning för en befintlig Dataverse-miljö

Om du vill ställa in dubbelriktad skrivning för en befintlig Dataverse-miljö måste du skapa ett Microsoft [supportärende](../../lifecycle-services/lcs-support.md). Ärendet måste innehålla:

+ Ditt Finance and Operations miljö-ID.
+ Ditt miljönamn från Lifecycle Services.
+ Dataverse organisations-ID eller Power Platform miljö-ID från Power Platform administrationscenter. Begär att ID:t ska vara den instans som används för integration på din Power Platform-integration.

> [!NOTE]
> Du kan inte avlänka miljöer med hjälp av LCS. Om du vill ta bort länken för en miljö, öppna arbetsytan **Dataintegration** i Finance and Operations-miljön och välj sen **Ta bort länk**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
