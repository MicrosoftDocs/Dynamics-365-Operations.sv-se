---
title: Initiera startdata i nya detaljhandelsmiljöer
description: Den här artikeln beskriver de data som har skapats som en del av initieringsprocessen för Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 49b21d81437ebd7cc55076444ee71ae1143bfac0
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025526"
---
# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="40abf-103">Initiera startdata i nya Retail-miljöer</span><span class="sxs-lookup"><span data-stu-id="40abf-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="40abf-104">Den här artikeln beskriver de data som har skapats som en del av initieringsprocessen för Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="40abf-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Retail.</span></span>

<span data-ttu-id="40abf-105">Efter återförsäljarlösning har spridits via Microsoft Dynamics Lifecycle Services (LCS), måste du initiera butikskonfiguration för att skapa grundläggande konfigurationsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="40abf-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40abf-106">Innan du initierar butikskonfiguration, kontrollera att du har angett ett språk och en postadress för varje juridisk enhet där du ställer upp butiker.</span><span class="sxs-lookup"><span data-stu-id="40abf-106">Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="40abf-107">Detta steg måste genomföras för varje juridisk enhet som du använder för butik.</span><span class="sxs-lookup"><span data-stu-id="40abf-107">This step must be completed for each legal entity that you use for retail.</span></span>

<span data-ttu-id="40abf-108">För att initiera retail konfiguration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="40abf-108">To initialize the retail configuration, follow these steps.</span></span>

1. <span data-ttu-id="40abf-109">Starta Retail-klienten.</span><span class="sxs-lookup"><span data-stu-id="40abf-109">Start the Retail client.</span></span>
2. <span data-ttu-id="40abf-110">Klicka på **Butiker** &gt; **Inställningar för huvudkontor** &gt; **Parametrar** &gt; **Detaljhandelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="40abf-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3. <span data-ttu-id="40abf-111">Klicka på **Initiera**.</span><span class="sxs-lookup"><span data-stu-id="40abf-111">Click **Initialize**.</span></span>

<span data-ttu-id="40abf-112">Initiering skapar följande standard konfigurationsdata:</span><span class="sxs-lookup"><span data-stu-id="40abf-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="40abf-113">Retail scheduler jobb och subjobs</span><span class="sxs-lookup"><span data-stu-id="40abf-113">Retail scheduler jobs and subjobs</span></span>
- <span data-ttu-id="40abf-114">Schema för butikskanal</span><span class="sxs-lookup"><span data-stu-id="40abf-114">Retail channel schema</span></span>
- <span data-ttu-id="40abf-115">butik scheman</span><span class="sxs-lookup"><span data-stu-id="40abf-115">Retail distribution schedules</span></span>
- <span data-ttu-id="40abf-116">Standard skärmlayouter, vilket inkluderar knappen raster, bilder och teman</span><span class="sxs-lookup"><span data-stu-id="40abf-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="40abf-117">Tidzonsinformation</span><span class="sxs-lookup"><span data-stu-id="40abf-117">Time zone information</span></span>
- <span data-ttu-id="40abf-118">Pointen-of-sale (POS)</span><span class="sxs-lookup"><span data-stu-id="40abf-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="40abf-119">Kassabehörigheter</span><span class="sxs-lookup"><span data-stu-id="40abf-119">POS permissions</span></span>
- <span data-ttu-id="40abf-120">Kanalrapporter</span><span class="sxs-lookup"><span data-stu-id="40abf-120">Channel reports</span></span>
- <span data-ttu-id="40abf-121">Attributmetadata</span><span class="sxs-lookup"><span data-stu-id="40abf-121">Attribute metadata</span></span>
- <span data-ttu-id="40abf-122">Enhet validering mallar</span><span class="sxs-lookup"><span data-stu-id="40abf-122">Entity validation templates</span></span>
- <span data-ttu-id="40abf-123">Batch-jobb för att ta bort Commerce Data Exchange-sessionshistorik</span><span class="sxs-lookup"><span data-stu-id="40abf-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="40abf-124">Dessutom loggar som är relaterad till PCI (Payment Card Industry) är aktiverad för Retail-databasen.</span><span class="sxs-lookup"><span data-stu-id="40abf-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Retail database.</span></span>

> [!NOTE]
> <span data-ttu-id="40abf-125">Det finns ett alternativ till separat konfigurering av butiksplanering.</span><span class="sxs-lookup"><span data-stu-id="40abf-125">There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="40abf-126">Det här alternativet låter dig återställa Retail scheduler konfigurationen till standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="40abf-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span>

<span data-ttu-id="40abf-127">Efter initialiseringen är klar måste du konfigurera ytterligare retail data.</span><span class="sxs-lookup"><span data-stu-id="40abf-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="40abf-128">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="40abf-128">Here are some examples:</span></span>

- <span data-ttu-id="40abf-129">Butiksparametrar</span><span class="sxs-lookup"><span data-stu-id="40abf-129">Retail parameters</span></span>
- <span data-ttu-id="40abf-130">Parametrar för Butik schemaläggare</span><span class="sxs-lookup"><span data-stu-id="40abf-130">Retail scheduler parameters</span></span>
- <span data-ttu-id="40abf-131">Butikskanaler</span><span class="sxs-lookup"><span data-stu-id="40abf-131">Retail channels</span></span>
- <span data-ttu-id="40abf-132">Register och enheter</span><span class="sxs-lookup"><span data-stu-id="40abf-132">Registers and devices</span></span>
- <span data-ttu-id="40abf-133">Sortiment</span><span class="sxs-lookup"><span data-stu-id="40abf-133">Assortments</span></span>
