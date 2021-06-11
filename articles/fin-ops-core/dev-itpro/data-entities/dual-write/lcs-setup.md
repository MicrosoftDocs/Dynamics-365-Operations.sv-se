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
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103579"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="5b343-103">Inställning av dubbelriktad skrivning från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="5b343-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="5b343-104">I det här avsnittet beskrivs hur du aktiverar en dubbelriktad skrivning från Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5b343-104">This topic explains how to enable dual-write from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b343-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="5b343-105">Prerequisites</span></span>

<span data-ttu-id="5b343-106">Du måste slutföra Power Platform-integrationen enligt beskrivningen i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="5b343-106">You must complete the Power Platform integration as described in the following topics:</span></span>

+ [<span data-ttu-id="5b343-107">Power Platform-integration - Aktivera under utveckling av miljön</span><span class="sxs-lookup"><span data-stu-id="5b343-107">Power Platform Integration - Enable during environment deployment</span></span>](../../power-platform/overview.md#enable-during-environment-deployment)
+ [<span data-ttu-id="5b343-108">Power Platform-integration - Ställ in efter utveckling av miljön</span><span class="sxs-lookup"><span data-stu-id="5b343-108">Power Platform integration - Set up after environment deployment</span></span>](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a><span data-ttu-id="5b343-109">Ställ in dubbelriktad skrivning för nya Dataverse-miljöer</span><span class="sxs-lookup"><span data-stu-id="5b343-109">Set up dual-write for new Dataverse environments</span></span>

<span data-ttu-id="5b343-110">Följ dessa steg när du vill ställa in dubbelriktad skrivning från LCS **miljöinformation**:</span><span class="sxs-lookup"><span data-stu-id="5b343-110">Follow these steps to set up dual-write from LCS **Environment Details** page:</span></span>

1. <span data-ttu-id="5b343-111">På sidan **Miljöinformation** visa avsnittet **Power Platform-integration**.</span><span class="sxs-lookup"><span data-stu-id="5b343-111">On the **Environment Details** page, expand the **Power Platform Integration** section.</span></span>

2. <span data-ttu-id="5b343-112">Välj knappen **dubbelriktad skrivning för app**.</span><span class="sxs-lookup"><span data-stu-id="5b343-112">Select the **Dual-write application** button.</span></span>

    ![Power Platform-integration](media/powerplat_integration_step2.png)

3. <span data-ttu-id="5b343-114">Granska villkoren och markera sedan **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="5b343-114">Review the terms and conditions, and then select **Configure**.</span></span>

4. <span data-ttu-id="5b343-115">Välj **OK** om du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="5b343-115">Select **OK** to continue.</span></span>

5. <span data-ttu-id="5b343-116">Du kan övervaka förloppet genom att regelbundet uppdatera sidan för miljöinformation.</span><span class="sxs-lookup"><span data-stu-id="5b343-116">You can monitor the progress by periodically refreshing the environment details page.</span></span> <span data-ttu-id="5b343-117">Inställningen tar normalt 30 minuter eller mindre.</span><span class="sxs-lookup"><span data-stu-id="5b343-117">Setup typically takes 30 minutes or less.</span></span>  

6. <span data-ttu-id="5b343-118">När inställningen är slutförd visas ett meddelande om processen lyckades eller om fel uppstår.</span><span class="sxs-lookup"><span data-stu-id="5b343-118">When the setup is complete, a message will inform you if the process was successful or if there was a failure.</span></span> <span data-ttu-id="5b343-119">Om inställningen misslyckades visas ett relaterat felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="5b343-119">If the setup failed, then a related error message is displayed.</span></span> <span data-ttu-id="5b343-120">Du måste åtgärda eventuella fel innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="5b343-120">You must fix any errors before moving to the next step.</span></span>

7. <span data-ttu-id="5b343-121">Välj **Länk till Power Platform miljö** om du vill skapa en länk mellan Dataverse och den aktuella miljöns databaser.</span><span class="sxs-lookup"><span data-stu-id="5b343-121">Select **Link to Power Platform environment** to create a link between Dataverse and the current environment's databases.</span></span> <span data-ttu-id="5b343-122">Detta tar normalt mindre än 5 minuter.</span><span class="sxs-lookup"><span data-stu-id="5b343-122">This typically takes less than 5 minutes.</span></span>

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Länka till Power Platform miljö":::

8. <span data-ttu-id="5b343-124">När länkningen är slutförd visas en hyperlänk.</span><span class="sxs-lookup"><span data-stu-id="5b343-124">When the linking is complete, a hyperlink is displayed.</span></span> <span data-ttu-id="5b343-125">Använd länken för att logga in på administrationsområdet för dubbelriktad skrivning i Finance and Operations-miljön.</span><span class="sxs-lookup"><span data-stu-id="5b343-125">Use the link to sign in to the dual-write administration area in the Finance and Operations environment.</span></span> <span data-ttu-id="5b343-126">Därifrån kan du ställa in enhetsmappningar.</span><span class="sxs-lookup"><span data-stu-id="5b343-126">From there, you can set up entity mappings.</span></span>

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a><span data-ttu-id="5b343-127">Ställ in dubbelriktad skrivning för en befintlig Dataverse-miljö</span><span class="sxs-lookup"><span data-stu-id="5b343-127">Set up dual-write for an existing Dataverse environment</span></span>

<span data-ttu-id="5b343-128">Om du vill ställa in dubbelriktad skrivning för en befintlig Dataverse-miljö måste du skapa ett Microsoft [supportärende](../../lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="5b343-128">To set up dual-write for an existing Dataverse environment, you must create a Microsoft [support ticket](../../lifecycle-services/lcs-support.md).</span></span> <span data-ttu-id="5b343-129">Ärendet måste innehålla:</span><span class="sxs-lookup"><span data-stu-id="5b343-129">The ticket must include:</span></span>

+ <span data-ttu-id="5b343-130">Ditt Finance and Operations miljö-ID.</span><span class="sxs-lookup"><span data-stu-id="5b343-130">Your Finance and Operations environment ID.</span></span>
+ <span data-ttu-id="5b343-131">Ditt miljönamn från Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="5b343-131">Your environment name from Lifecycle Services.</span></span>
+ <span data-ttu-id="5b343-132">Dataverse organisations-ID eller Power Platform miljö-ID från Power Platform administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="5b343-132">The Dataverse organization ID or Power Platform Environment ID from Power Platform Admin Center.</span></span> <span data-ttu-id="5b343-133">Begär att ID:t ska vara den instans som används för integration på din Power Platform-integration.</span><span class="sxs-lookup"><span data-stu-id="5b343-133">In your ticket, request that the ID be the instance used for Power Platform integration.</span></span>

> [!NOTE]
> <span data-ttu-id="5b343-134">Du kan inte avlänka miljöer med hjälp av LCS.</span><span class="sxs-lookup"><span data-stu-id="5b343-134">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="5b343-135">Om du vill ta bort länken för en miljö, öppna arbetsytan **Dataintegration** i Finance and Operations-miljön och välj sen **Ta bort länk**.</span><span class="sxs-lookup"><span data-stu-id="5b343-135">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
