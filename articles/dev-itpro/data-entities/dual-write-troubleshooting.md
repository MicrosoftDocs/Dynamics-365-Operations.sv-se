---
title: Felsökningsguide för dataintegrering
description: Det här avsnittet innehåller felsökningsinformation om dataintegrering mellan Microsoft Dynamics 365 for Finance and Operations och Common Data Service.
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
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797285"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="2fdf3-103">Felsökningsguide för dataintegrering</span><span class="sxs-lookup"><span data-stu-id="2fdf3-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a><span data-ttu-id="2fdf3-104">Möjliggöra plugin-spårning i Common Data Service och kontrollera den dubbelriktade skrivning plugin-feldetaljer</span><span class="sxs-lookup"><span data-stu-id="2fdf3-104">Enable Plugin Trace in Common Data Service and check the dual-write Plugin error details</span></span>

<span data-ttu-id="2fdf3-105">Om du står inför ett problem eller ett fel med synkronisering av dubbelriktad skrivning kan du inspektera felen i spårningsloggen:</span><span class="sxs-lookup"><span data-stu-id="2fdf3-105">If you are facing an issue or error with dual-write synchronization, you can inspect the errors in the trace log:</span></span>

1. <span data-ttu-id="2fdf3-106">Innan du kan inspektera felen måste du aktivera plugin-spårning med hjälp av instruktionerna i [registrera plugin-program](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) för att aktivera spårning av plugin-spårning.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-106">Before you can inspect the errors, you must enable Plugin trace using the instructions in [Register plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) to enable Plugin trace.</span></span> <span data-ttu-id="2fdf3-107">Nu kan du inspektera felen.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-107">Now you can inspect the errors.</span></span>
2. <span data-ttu-id="2fdf3-108">Logga in på Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-108">Login to Dynamics 365 for Sales.</span></span>
3. <span data-ttu-id="2fdf3-109">Klicka på inställningsikonen (ett kugghjul) och välj **avancerade inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-109">Click on the Settings icon (a gear), and select **Advanced Settings**.</span></span>
4. <span data-ttu-id="2fdf3-110">I menyn **inställningar** väljer du **anpassning > spårningslogg för plugin-program**.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-110">In the **Settings** menu, choose **Customization > Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="2fdf3-111">Klicka på typnamnet **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** för att vVisa felinformationen.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-111">Click the type name **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** to display the error details.</span></span>

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a><span data-ttu-id="2fdf3-112">Kontrollera synkroniseringsfel med dubbelriktade skrivningar i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2fdf3-112">Check dual-write synchronization errors in Finance and Operations</span></span>

<span data-ttu-id="2fdf3-113">Du kan kontrollera felen under testningen genom att följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="2fdf3-113">You can check the errors during testing by following these steps:</span></span>

+ <span data-ttu-id="2fdf3-114">Logga in på LifeCycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="2fdf3-114">Login to LifeCycle Services (LCS).</span></span>
+ <span data-ttu-id="2fdf3-115">Öppna LCS-projektet som du valde att utföra testning av dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-115">Open the LCS project that you chose to perform dual-write testing.</span></span>
+ <span data-ttu-id="2fdf3-116">Gå till molnstyrda miljöer.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-116">Go to Cloud Hosted Environments.</span></span>
+ <span data-ttu-id="2fdf3-117">Fjärrskrivbord till Finance and Operations VM med lokalt konto som visas i LCS.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-117">Remote desktop to Finance and Operations VM using local account that is displayed in LCS.</span></span>
+ <span data-ttu-id="2fdf3-118">Öppna händelsevisningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-118">Open the event viewer.</span></span> 
+ <span data-ttu-id="2fdf3-119">Navigera till **program- och tjänstloggar > Microsoft > Dynamics > AX-DualWriteSync > Drift**.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-119">Navigate to **Applications and Services logs > Microsoft > Dynamics > AX-DualWriteSync > Operational**.</span></span> <span data-ttu-id="2fdf3-120">Felen och detaljerna visas.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-120">The errors and details are displayed.</span></span>

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a><span data-ttu-id="2fdf3-121">Ta bort länken till och länka en annan Common Data Service-miljö från Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2fdf3-121">How to unlink and link another Common Data Service environment from Finance and Operations</span></span>

<span data-ttu-id="2fdf3-122">Du kan uppdatera länkarna genom att följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="2fdf3-122">You can update links by following these steps:</span></span>

+ <span data-ttu-id="2fdf3-123">Navigera till Finance and Operations-miljön.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-123">Navigate to the Finance and Operations environment.</span></span>
+ <span data-ttu-id="2fdf3-124">Öppna datahantering.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-124">Open Data Management.</span></span>
+ <span data-ttu-id="2fdf3-125">Klicka på **Länkatill CDS för appar**.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-125">Click on **Link to CDS for apps**.</span></span>
+ <span data-ttu-id="2fdf3-126">Markera alla mappningar som körs och klicka på **stoppa**.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-126">Select all the running mappings and click **Stop**.</span></span> 
+ <span data-ttu-id="2fdf3-127">Markera alla mappningar och klicka på **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-127">Select all the mappings and click **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2fdf3-128">Alternativet **ta bort** visas inte om mallen **CustomerV3-konto** har valts.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-128">The **Delete** option will not appear if **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="2fdf3-129">Avmarkera om det behövs.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-129">Unselect it if needed.</span></span> <span data-ttu-id="2fdf3-130">**CustomerV3-konto** är en äldre etablerad mall och fungerar med lösningen potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-130">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="2fdf3-131">Eftersom den släpps globalt visas den under alla mallar.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-131">Because it is globally released, it shows up under all templates.</span></span>

+ <span data-ttu-id="2fdf3-132">Klicka på **Ta bort länk till miljö**.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-132">Click **Unlink environment**.</span></span>
+ <span data-ttu-id="2fdf3-133">Klicka på **ja** för bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-133">Click **Yes** for confirmation.</span></span>
+ <span data-ttu-id="2fdf3-134">Följ stegen i [installationsguiden](https://aka.ms/dualwrite-docs) om du vill länka den nya miljön.</span><span class="sxs-lookup"><span data-stu-id="2fdf3-134">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>

