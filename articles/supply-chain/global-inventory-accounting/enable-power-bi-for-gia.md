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
# <a name="enable-power-bi-for-global-inventory-accounting"></a><span data-ttu-id="9591c-103">Aktivera Power BI för global lagerredovisning</span><span class="sxs-lookup"><span data-stu-id="9591c-103">Enable Power BI for Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="9591c-104">Du kan fästa paneler, instrumentpaneler och rapporter från ditt [PowerBI.com](https://powerbi.com/) konto till ditt Microsoft Dynamics 365 programarbetsytan.</span><span class="sxs-lookup"><span data-stu-id="9591c-104">You can pin tiles, dashboards, and reports from your [PowerBI.com](https://powerbi.com/) account to your Microsoft Dynamics 365 application workspace.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9591c-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="9591c-105">Prerequisites</span></span>

<span data-ttu-id="9591c-106">Följande förutsättningar måste uppfyllas innan du kan aktivera Power BI rapporteringen:</span><span class="sxs-lookup"><span data-stu-id="9591c-106">The following prerequisites must be in place before you can enable Power BI reporting:</span></span>

- <span data-ttu-id="9591c-107">Du måste vara systemadministratör i programmet Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9591c-107">You must be a system administrator in the Dynamics 365 application.</span></span>
- <span data-ttu-id="9591c-108">Du måste ha ett [PowerBI.com](https://powerbi.com/) konto.</span><span class="sxs-lookup"><span data-stu-id="9591c-108">You must have a [PowerBI.com](https://powerbi.com/) account.</span></span>
- <span data-ttu-id="9591c-109">Du måste ha minst en instrumentpanel och en rapport i Power BI kontot.</span><span class="sxs-lookup"><span data-stu-id="9591c-109">You must have at least one dashboard and one report in your Power BI account.</span></span>
- <span data-ttu-id="9591c-110">Du måste vara administratör för ditt Azure Active Directory (Azure AD) konto.</span><span class="sxs-lookup"><span data-stu-id="9591c-110">You must be an administrator for your Azure Active Directory (Azure AD) account.</span></span>
- <span data-ttu-id="9591c-111">Domänen Azure AD måste vara samma domän som du använde för [PowerBI.com](https://powerbi.com/) kontot.</span><span class="sxs-lookup"><span data-stu-id="9591c-111">The Azure AD domain must be the same domain that you used for your [PowerBI.com](https://powerbi.com/) account.</span></span>

## <a name="setup"></a><span data-ttu-id="9591c-112">Ställ in</span><span class="sxs-lookup"><span data-stu-id="9591c-112">Setup</span></span>

<span data-ttu-id="9591c-113">För att ställa in Power BI-integrationen, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="9591c-113">To set up the Power BI integration, follow these steps.</span></span>

1. <span data-ttu-id="9591c-114">Logga in på [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="9591c-114">Sign in to [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="9591c-115">Gå till **Bibliotek för gemensam tillgång**, välj **Power BI rapportmodell** som tillgångstyp och hämta paketet **Global lagerredovisning**.</span><span class="sxs-lookup"><span data-stu-id="9591c-115">Go to **Shared asset library**, select **Power BI report model** as the asset type, and download the **Global Inventory Accounting** package.</span></span> 
1. <span data-ttu-id="9591c-116">Logga in på [PowerBI.com](https://app.powerbi.com/)  och överför rapportfilen **Global lagerredovisning** Power BI så här:</span><span class="sxs-lookup"><span data-stu-id="9591c-116">Sign in to [PowerBI.com](https://app.powerbi.com/), and upload the **Global Inventory Accounting** Power BI report file by following these steps:</span></span>

    1. <span data-ttu-id="9591c-117">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9591c-117">Select **New**.</span></span>
    1. <span data-ttu-id="9591c-118">Välj **Överför en fil**.</span><span class="sxs-lookup"><span data-stu-id="9591c-118">Select **Upload a file**.</span></span>
    1. <span data-ttu-id="9591c-119">Välj rapportfilen **Global lagerredovisning** Power BI.</span><span class="sxs-lookup"><span data-stu-id="9591c-119">Select the **Global Inventory Accounting** Power BI report file.</span></span>

1. <span data-ttu-id="9591c-120">Konfigurera rapporten **Global lagerredovisning** Power BI genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="9591c-120">Configure the **Global Inventory Accounting** Power BI report by following these steps:</span></span>

    1. <span data-ttu-id="9591c-121">Gå till **Min arbetsyta**, hitta datauppsättningen för Global lagerredovisning och sedan i menyn **Alternativ** välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="9591c-121">Go to **My workspace**, find the dataset for Global Inventory Accounting, and then, on the **Options** menu, select **Settings**.</span></span>
    1. <span data-ttu-id="9591c-122">I **Inställningar för global lagerredovisning** expanderar du **Parametrar** och uppdaterar alla parametrar efter behov.</span><span class="sxs-lookup"><span data-stu-id="9591c-122">In **Settings for Global inventory accounting**, expand **Parameters**, and update all parameters as required.</span></span>

1. <span data-ttu-id="9591c-123">Registrera ansökan enligt beskrivningen i [Konfigurera PowerBI.com-integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span><span class="sxs-lookup"><span data-stu-id="9591c-123">Register the application as described in [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span></span>
1. <span data-ttu-id="9591c-124">Integrera rapportfilen **Global lagerredovisning** Power BI i Dynamics 365 Supply Chain Management genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="9591c-124">Integrate the **Global Inventory Accounting** Power BI report file into Dynamics 365 Supply Chain Management by following these steps:</span></span>

    1. <span data-ttu-id="9591c-125">Öppna **Systemadministration \> Inställningar \> PowerBI.com konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9591c-125">Go to **System administration \> Setup \> PowerBI.com configuration**.</span></span>
    1. <span data-ttu-id="9591c-126">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9591c-126">Select **Edit**.</span></span>
    1. <span data-ttu-id="9591c-127">Välj **Aktivera PowerBI.Com-integration**.</span><span class="sxs-lookup"><span data-stu-id="9591c-127">Select **Enable PowerBI.Com integration**.</span></span>
    1. <span data-ttu-id="9591c-128">I fälten **App-ID** anger du app-ID.</span><span class="sxs-lookup"><span data-stu-id="9591c-128">In the **Application ID** field, enter the application ID.</span></span>
    1. <span data-ttu-id="9591c-129">I fälten **Appnyckel** anger du appnyckel.</span><span class="sxs-lookup"><span data-stu-id="9591c-129">In the **Application key** field, enter the application key.</span></span>
    1. <span data-ttu-id="9591c-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9591c-130">Select **Save**.</span></span>

1. <span data-ttu-id="9591c-131">Uppdatera sidan så att dialogrutan Power BI för inloggning visas.</span><span class="sxs-lookup"><span data-stu-id="9591c-131">Refresh the page so that the Power BI sign-in dialog box appears.</span></span>
1. <span data-ttu-id="9591c-132">På fliken **Alternativ**, välj **Öppna rapportkatalog** och välj sedan **Global lagerredovisning** Power BI rapportfil som du laddade upp tidigare.</span><span class="sxs-lookup"><span data-stu-id="9591c-132">On the **Options** tab, select **Open report catalog**, and then select the **Global Inventory Accounting** Power BI report file that you uploaded earlier.</span></span>
1. <span data-ttu-id="9591c-133">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="9591c-133">Refresh the page.</span></span> <span data-ttu-id="9591c-134">Du bör se att rapporten har lagts till.</span><span class="sxs-lookup"><span data-stu-id="9591c-134">You should see that your report has been added.</span></span>
1. <span data-ttu-id="9591c-135">Under **Power BI rapportet**, välj länken **Global lagerredovisning**.</span><span class="sxs-lookup"><span data-stu-id="9591c-135">Under **Power BI reports**, select the **Global Inventory Accounting** link.</span></span>

<span data-ttu-id="9591c-136">Mer information finns i [Konfigurera PowerBI.com-integrering](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span><span class="sxs-lookup"><span data-stu-id="9591c-136">For more information, see [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span></span>
