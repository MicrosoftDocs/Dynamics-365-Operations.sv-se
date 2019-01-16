---
title: "Initiera startdata i nya detaljhandelsmiljöer"
description: "Den här artikeln beskriver de data som skapas under initieringsprocessen för Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 52f0c52748958f0bebb6c40df01cfac10c0ed427
ms.contentlocale: sv-se
ms.lasthandoff: 01/04/2019

---

# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="4d60e-103">Initiera startdata i nya detaljhandelsmiljöer</span><span class="sxs-lookup"><span data-stu-id="4d60e-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4d60e-104">Den här artikeln beskriver de data som skapas under initieringsprocessen för Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="4d60e-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="4d60e-105">Efter återförsäljarlösning har spridits via Microsoft Dynamics Lifecycle Services (LCS), måste du initiera retail konfiguration för att skapa grundläggande konfigurationsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="4d60e-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d60e-106">Innan du initierar butikskonfiguration, kontrollera att du har angett ett språk och en postadress för varje juridisk enhet där du ställer upp butiker.</span><span class="sxs-lookup"><span data-stu-id="4d60e-106">Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="4d60e-107">Detta steg måste genomföras för varje juridisk enhet som du använder för butik.</span><span class="sxs-lookup"><span data-stu-id="4d60e-107">This step must be completed for each legal entity that you use for retail.</span></span>

<span data-ttu-id="4d60e-108">För att initiera retail konfiguration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="4d60e-108">To initialize the retail configuration, follow these steps.</span></span>

1. <span data-ttu-id="4d60e-109">Starta Dynamics 365 for Retail-klienten.</span><span class="sxs-lookup"><span data-stu-id="4d60e-109">Start the Dynamics 365 for Retail client.</span></span>
2. <span data-ttu-id="4d60e-110">Klicka på **Butiker** &gt; **Inställningar för huvudkontor** &gt; **Parametrar** &gt; **Detaljhandelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="4d60e-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3. <span data-ttu-id="4d60e-111">Klicka på **Initiera**.</span><span class="sxs-lookup"><span data-stu-id="4d60e-111">Click **Initialize**.</span></span>

<span data-ttu-id="4d60e-112">Initiering skapar följande standard konfigurationsdata:</span><span class="sxs-lookup"><span data-stu-id="4d60e-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="4d60e-113">Retail scheduler jobb och subjobs</span><span class="sxs-lookup"><span data-stu-id="4d60e-113">Retail scheduler jobs and subjobs</span></span>
- <span data-ttu-id="4d60e-114">Schema för butikskanal</span><span class="sxs-lookup"><span data-stu-id="4d60e-114">Retail channel schema</span></span>
- <span data-ttu-id="4d60e-115">butik scheman</span><span class="sxs-lookup"><span data-stu-id="4d60e-115">Retail distribution schedules</span></span>
- <span data-ttu-id="4d60e-116">Standard skärmlayouter, vilket inkluderar knappen raster, bilder och teman</span><span class="sxs-lookup"><span data-stu-id="4d60e-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="4d60e-117">Tidzonsinformation</span><span class="sxs-lookup"><span data-stu-id="4d60e-117">Time zone information</span></span>
- <span data-ttu-id="4d60e-118">Pointen-of-sale (POS)</span><span class="sxs-lookup"><span data-stu-id="4d60e-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="4d60e-119">Kassabehörigheter</span><span class="sxs-lookup"><span data-stu-id="4d60e-119">POS permissions</span></span>
- <span data-ttu-id="4d60e-120">Kanalrapporter</span><span class="sxs-lookup"><span data-stu-id="4d60e-120">Channel reports</span></span>
- <span data-ttu-id="4d60e-121">Attributmetadata</span><span class="sxs-lookup"><span data-stu-id="4d60e-121">Attribute metadata</span></span>
- <span data-ttu-id="4d60e-122">Enhet validering mallar</span><span class="sxs-lookup"><span data-stu-id="4d60e-122">Entity validation templates</span></span>
- <span data-ttu-id="4d60e-123">Bakgrundsjobbet ska rensa handel Data Exchange sessionshistorik</span><span class="sxs-lookup"><span data-stu-id="4d60e-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="4d60e-124">Dessutom aktiveras loggar som är relaterade till PCI (Payment Card Industry; betalkortsbranschen) för Dynamics 365 for Retail-databasen.</span><span class="sxs-lookup"><span data-stu-id="4d60e-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span>

> [!NOTE]
> <span data-ttu-id="4d60e-125">Det finns ett alternativ till separat konfigurering av butiksplanering.</span><span class="sxs-lookup"><span data-stu-id="4d60e-125">There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="4d60e-126">Det här alternativet låter dig återställa Retail scheduler konfigurationen till standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="4d60e-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span>

<span data-ttu-id="4d60e-127">Efter initialiseringen är klar måste du konfigurera ytterligare retail data.</span><span class="sxs-lookup"><span data-stu-id="4d60e-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="4d60e-128">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="4d60e-128">Here are some examples:</span></span>

- <span data-ttu-id="4d60e-129">Butiksparametrar</span><span class="sxs-lookup"><span data-stu-id="4d60e-129">Retail parameters</span></span>
- <span data-ttu-id="4d60e-130">Parametrar för Butik schemaläggare</span><span class="sxs-lookup"><span data-stu-id="4d60e-130">Retail scheduler parameters</span></span>
- <span data-ttu-id="4d60e-131">Butikskanaler</span><span class="sxs-lookup"><span data-stu-id="4d60e-131">Retail channels</span></span>
- <span data-ttu-id="4d60e-132">Register och enheter</span><span class="sxs-lookup"><span data-stu-id="4d60e-132">Registers and devices</span></span>
- <span data-ttu-id="4d60e-133">Sortiment</span><span class="sxs-lookup"><span data-stu-id="4d60e-133">Assortments</span></span>

