---
title: Installera tillägget för IoT-information i LCS
description: I det här avsnittet beskrivs hur du installerar IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 87d04c3df22e2d9ef56acb61e26304731a2a17a2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206062"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="eb896-103">Installera tillägget för IoT-information i LCS</span><span class="sxs-lookup"><span data-stu-id="eb896-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eb896-104">I det här avsnittet beskrivs hur du installerar IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="eb896-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="eb896-105">Lägg märke till att tillägg inte kan installeras i en demo/utvärderingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="eb896-105">Note that add-ins cannot be installed on a demo/trial environment.</span></span> <span data-ttu-id="eb896-106">Innan du kan installera tillägget måste du [skapa Azure-resurserna](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="eb896-106">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="eb896-107">Konfigurera LCS-miljö</span><span class="sxs-lookup"><span data-stu-id="eb896-107">Set up the LCS environment</span></span>

1. <span data-ttu-id="eb896-108">Öppna LCS och gå till din Microsoft Dynamics 365 Supply Chain Management-miljö.</span><span class="sxs-lookup"><span data-stu-id="eb896-108">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="eb896-109">Bläddra till avsnittet **Miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="eb896-109">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="eb896-110">Välj **Installera ett nytt tillägg** om du vill visa listan över tillägg som har aktiverats för miljön.</span><span class="sxs-lookup"><span data-stu-id="eb896-110">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="eb896-111">I dialogrutan **Välj ett tillägg att installera** väljer du **IoT-information**.</span><span class="sxs-lookup"><span data-stu-id="eb896-111">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="eb896-112">I dialogrutan **Tillägg för inställningar** anger du information om IoT-navet och Redis-cachen.</span><span class="sxs-lookup"><span data-stu-id="eb896-112">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="eb896-113">Du hittar erforderliga värden i det nyckelvalv som du skapade i [Skapa Azure-resurser](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="eb896-113">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="eb896-114">**ID för klientorganisation** – Gå till nyckelvalvet i Azure-portalen och välj sedan **Översikt** i det vänstra navigeringsfönstret. Kopiera sedan värdet för **Katalog-ID**.</span><span class="sxs-lookup"><span data-stu-id="eb896-114">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="eb896-115">Klistra in värdet i dialogrutan **Tillägg för konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="eb896-115">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="eb896-116">**IoT Event Hub-kompatibel URI för slutpunktsnyckelvalv** – Gå till nyckelvalvet, välj **Översikt** i det vänstra navigeringsfönstret och kopiera värdet för **DNS-namn**.</span><span class="sxs-lookup"><span data-stu-id="eb896-116">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="eb896-117">Klistra in värdet i dialogrutan **Tillägg för konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="eb896-117">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="eb896-118">**IoT Event Hub-kompatibelt namn för slutpunktshemlighet** – Gå till nyckelvalvet, välj **Hemligheter** i det vänstra navigeringsfönstret och kopiera namnet på den hemlighet där anslutningssträngen i händelsenavet för IoT-navet lagras.</span><span class="sxs-lookup"><span data-stu-id="eb896-118">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="eb896-119">Klistra in värdet i dialogrutan **Tillägg för konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="eb896-119">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="eb896-120">**Nyckelvärdes-URI för Redis-cache** – Gå till nyckelvalvet, välj **Översikt** i det vänstra navigeringsfönstret och kopiera värdet för **DNS-namn**.</span><span class="sxs-lookup"><span data-stu-id="eb896-120">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="eb896-121">Klistra in värdet i dialogrutan **Tillägg för konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="eb896-121">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="eb896-122">**Hemligt slutpunktsnamn för Redis-cache** – Gå till nyckelvalvet, välj **Hemligheter** i det vänstra navigeringsfönstret och kopiera namnet på den hemlighet där anslutningssträngen i händelsenavet för Redis-cache lagras.</span><span class="sxs-lookup"><span data-stu-id="eb896-122">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="eb896-123">Klistra in värdet i dialogrutan **Tillägg för konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="eb896-123">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="eb896-124">Markera kryss rutan om du vill acceptera villkoren.</span><span class="sxs-lookup"><span data-stu-id="eb896-124">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="eb896-125">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="eb896-125">Select **Install**.</span></span>
8. <span data-ttu-id="eb896-126">En meddelanderuta visas med statusen "Tillägget har aktiverats för installation".</span><span class="sxs-lookup"><span data-stu-id="eb896-126">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="eb896-127">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb896-127">Select **OK**.</span></span>

<span data-ttu-id="eb896-128">LCS-konfigurationen har nu slutförts.</span><span class="sxs-lookup"><span data-stu-id="eb896-128">LCS setup is now completed.</span></span> <span data-ttu-id="eb896-129">Nästa steg är att [ställa in scenarierna](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="eb896-129">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="eb896-130">Avinstallera tillägget</span><span class="sxs-lookup"><span data-stu-id="eb896-130">Uninstall the add-in</span></span>

1. <span data-ttu-id="eb896-131">[Avaktivera scenarierna](iot-scenario-setup.md#disable-a-scenario) i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="eb896-131">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#disable-a-scenario).</span></span>
2. <span data-ttu-id="eb896-132">I LCS går du till informationen för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="eb896-132">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="eb896-133">Bläddra till avsnittet **Miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="eb896-133">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="eb896-134">Välj **Avinstallera** för tilläggsprogrammet för IoT-information.</span><span class="sxs-lookup"><span data-stu-id="eb896-134">Select **Uninstall** for the IoT Intelligence add-in.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]