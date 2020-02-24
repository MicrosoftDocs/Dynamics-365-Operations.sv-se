---
title: Felsökningsguide för dataintegrering
description: Det här avsnittet innehåller felsökningsinformation för dataintegrering mellan Finance and Operations-appar och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 87bdb72024c1c3844ff61e832a92f7edcc77c5d6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020021"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="e8cdf-103">Felsökningsguide för dataintegrering</span><span class="sxs-lookup"><span data-stu-id="e8cdf-103">Troubleshooting guide for data integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a><span data-ttu-id="e8cdf-104">Möjliggöra plugin-spårningsloggar i Common Data Service och inspektera de dubbelriktade skrivning plugin-feldetaljerna</span><span class="sxs-lookup"><span data-stu-id="e8cdf-104">Enable plug-in trace logs in Common Data Service and inspect the dual-write plug-in error details</span></span>

<span data-ttu-id="e8cdf-105">Om det uppstår ett problem eller fel under en synkronisering med dubbelriktad skrivning följer du stegen nedan för att granska felen i spårningsloggen.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-105">If you experience an issue or error during dual-write synchronization, follow these steps to inspect the errors in the trace log.</span></span>

1. <span data-ttu-id="e8cdf-106">Innan du kan undersöka felen måste du aktivera spårningsloggar för plugin-program.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-106">Before you can inspect the errors, you must enable plug-in trace logs.</span></span> <span data-ttu-id="e8cdf-107">Instruktioner finns i avsnittet "Visa spårningsloggar" i [Självstudier: Skriv och registrera ett plugin-program](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="e8cdf-107">For instructions, see the "View trace logs" section of [Tutorial: Write and register a plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span></span>

    <span data-ttu-id="e8cdf-108">Nu kan du inspektera felen.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-108">You can now inspect the errors.</span></span>

2. <span data-ttu-id="e8cdf-109">Logga in på Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-109">Sign in to Microsoft Dynamics 365 Sales.</span></span>
3. <span data-ttu-id="e8cdf-110">Välj knappen **Inställningar** (växelsymbolen) och sedan **Avancerade inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-110">Select the **Settings** button (the gear symbol), and then select **Advanced Settings**.</span></span>
4. <span data-ttu-id="e8cdf-111">På menyn **Inställningar** väljer du **Anpassning \> spårningslogg för plugin-program**.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-111">On the **Settings** menu, select **Customization \> Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="e8cdf-112">Välj **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** som typnamn för att visa felinformationen.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-112">Select **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** as the type name to show the error details.</span></span>

## <a name="inspect-dual-write-synchronization-errors"></a><span data-ttu-id="e8cdf-113">Inspektera synkroniseringsfel vid dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="e8cdf-113">Inspect dual-write synchronization errors</span></span>

<span data-ttu-id="e8cdf-114">Följ dessa steg för att inspektera fel under testningen.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-114">Follow these steps to inspect errors during testing.</span></span>

1. <span data-ttu-id="e8cdf-115">Logga in på Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e8cdf-115">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="e8cdf-116">Öppna LCS-projektet som du vill dubbelriktad skrivtestning för.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-116">Open the LCS project to do dual-write testing for.</span></span>
3. <span data-ttu-id="e8cdf-117">Välj **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-117">Select **Cloud-hosted environments**.</span></span>
4. <span data-ttu-id="e8cdf-118">Gör en fjärrskrivbordsanslutning till den virtuella datorn (VM) för appen med hjälp av ett lokalt konto som visas i LCS.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-118">Make a Remote desktop connection to the application virtual machine (VM) by using local account that is shown in LCS.</span></span>
5. <span data-ttu-id="e8cdf-119">Öppna händelsevisningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-119">Open Event Viewer.</span></span> 
6. <span data-ttu-id="e8cdf-120">Gå till **Program- och tjänstloggar \> Microsoft \> Dynamics \> AX-DualWriteSync \> Drift**.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-120">Go to **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span> <span data-ttu-id="e8cdf-121">Felen och detaljerna visas.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-121">The errors and details are shown.</span></span>

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a><span data-ttu-id="e8cdf-122">Ta bort länken till en Common Data Service-miljö från appen och länka en annan miljö</span><span class="sxs-lookup"><span data-stu-id="e8cdf-122">Unlink one Common Data Service environment from the application and link another environment</span></span>

<span data-ttu-id="e8cdf-123">Följ dessa steg om för att uppdatera länkar.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-123">Follow these steps to update links.</span></span>

1. <span data-ttu-id="e8cdf-124">Gå till programmiljön.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-124">Go to the application environment.</span></span>
2. <span data-ttu-id="e8cdf-125">Öppna datahantering.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-125">Open Data Management.</span></span>
3. <span data-ttu-id="e8cdf-126">Välj **Länka till CDS för appar**.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-126">Select **Link to CDS for apps**.</span></span>
4. <span data-ttu-id="e8cdf-127">Välj alla mappningar som körs och välj sedan **Stopp**.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-127">Select all the mappings that are running, and then select **Stop**.</span></span>
5. <span data-ttu-id="e8cdf-128">Välj alla mappningarna och välj sedan **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-128">Select all the mappings, and then select **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e8cdf-129">Alternativet **Ta bort** är inte tillgängligt om mallen **CustomerV3-konto** har valts.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-129">The **Delete** option isn't available if the **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="e8cdf-130">Ta bort valet av den här mallen om det behövs.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-130">Clear the selection of this template as required.</span></span> <span data-ttu-id="e8cdf-131">**CustomerV3-konto** är en äldre etablerad mall och fungerar med lösningen potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-131">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="e8cdf-132">Eftersom den släpps globalt visas den under alla mallar.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-132">Because it's globally released, it appears under all templates.</span></span>

6. <span data-ttu-id="e8cdf-133">Välj **Ta bort länk till miljö**.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-133">Select **Unlink environment**.</span></span>
7. <span data-ttu-id="e8cdf-134">Välj **Ja** för att bekräfta åtgärden.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-134">Select **Yes** to confirm the operation.</span></span>
8. <span data-ttu-id="e8cdf-135">Följ stegen i [installationsguiden](https://aka.ms/dualwrite-docs) om du vill länka den nya miljön.</span><span class="sxs-lookup"><span data-stu-id="e8cdf-135">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>
