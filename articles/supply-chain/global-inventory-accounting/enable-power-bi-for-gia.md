---
title: Aktivera Power BI för global lagerredovisning
description: I det här avsnittet beskrivs hur du aktiverar Microsoft Power BI för global lagerredovisningen.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273227"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Aktivera Power BI för global lagerredovisning

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Du kan fästa paneler, instrumentpaneler och rapporter från ditt [PowerBI.com](https://powerbi.com/) konto till ditt Microsoft Dynamics 365 programarbetsytan.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas innan du kan aktivera Power BI rapporteringen:

- Du måste vara systemadministratör i programmet Dynamics 365.
- Du måste ha ett [PowerBI.com](https://powerbi.com/) konto.
- Du måste ha minst en instrumentpanel och en rapport i Power BI kontot.
- Du måste vara administratör för ditt Azure Active Directory (Azure AD) konto.
- Domänen Azure AD måste vara samma domän som du använde för [PowerBI.com](https://powerbi.com/) kontot.

## <a name="setup"></a>Ställ in

För att ställa in Power BI-integrationen, följ dessa steg.

1. Logga in på [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Gå till **Bibliotek för gemensam tillgång**, välj **Power BI rapportmodell** som tillgångstyp och hämta paketet **Global lagerredovisning**. 
1. Logga in på [PowerBI.com](https://app.powerbi.com/)  och överför rapportfilen **Global lagerredovisning** Power BI så här:

    1. Välj **Ny**.
    1. Välj **Överför en fil**.
    1. Välj rapportfilen **Global lagerredovisning** Power BI.

1. Konfigurera rapporten **Global lagerredovisning** Power BI genom att följa stegen nedan:

    1. Gå till **Min arbetsyta**, hitta datauppsättningen för Global lagerredovisning och sedan i menyn **Alternativ** välj **Inställningar**.
    1. I **Inställningar för global lagerredovisning** expanderar du **Parametrar** och uppdaterar alla parametrar efter behov.

1. Registrera ansökan enligt beskrivningen i [Konfigurera PowerBI.com-integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).
1. Integrera rapportfilen **Global lagerredovisning** Power BI i Dynamics 365 Supply Chain Management genom att följa stegen nedan:

    1. Öppna **Systemadministration \> Inställningar \> PowerBI.com konfiguration**.
    1. Välj **Redigera**.
    1. Välj **Aktivera PowerBI.Com-integration**.
    1. I fälten **App-ID** anger du app-ID.
    1. I fälten **Appnyckel** anger du appnyckel.
    1. Välj **Spara**.

1. Uppdatera sidan så att dialogrutan Power BI för inloggning visas.
1. På fliken **Alternativ**, välj **Öppna rapportkatalog** och välj sedan **Global lagerredovisning** Power BI rapportfil som du laddade upp tidigare.
1. Uppdatera sidan. Du bör se att rapporten har lagts till.
1. Under **Power BI rapportet**, välj länken **Global lagerredovisning**.

Mer information finns i [Konfigurera PowerBI.com-integrering](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).
