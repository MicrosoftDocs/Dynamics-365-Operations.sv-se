---
title: "Initiera startdata i en ny detaljhandelsmiljö"
description: "Den här artikeln beskriver de data som skapas under initieringsprocessen för Microsoft Dynamics 365 for Operations."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ac4f651cd7e5df912ea2535eafd5e54c11377253
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a><span data-ttu-id="ba889-103">Initiera startdata i en ny detaljhandelsmiljö</span><span class="sxs-lookup"><span data-stu-id="ba889-103">Initialize seed data in a new Retail environment</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="ba889-104">Den här artikeln beskriver de data som skapas under initieringsprocessen för Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="ba889-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="ba889-105">Efter återförsäljarlösning har spridits via Microsoft Dynamics Lifecycle Services (LCS), måste du initiera retail konfiguration för att skapa grundläggande konfigurationsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ba889-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span> <span data-ttu-id="ba889-106">**Viktigt!** Innan du initierar butikskonfiguration, kontrollera att du har angett ett språk och en postadress för varje juridisk enhet där du ställer upp butiker.</span><span class="sxs-lookup"><span data-stu-id="ba889-106">**Important:** Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="ba889-107">Detta steg måste genomföras för varje juridisk enhet som du använder för butik.</span><span class="sxs-lookup"><span data-stu-id="ba889-107">This step must be completed for each legal entity that you use for retail.</span></span> <span data-ttu-id="ba889-108">För att initiera retail konfiguration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ba889-108">To initialize the retail configuration, follow these steps.</span></span>

1.  <span data-ttu-id="ba889-109">Starta Dynamics 365 for Retail-klienten.</span><span class="sxs-lookup"><span data-stu-id="ba889-109">Start the Dynamics 365 for Retail client.</span></span>
2.  <span data-ttu-id="ba889-110">Klicka på **Butiker** &gt; **Inställningar för huvudkontor** &gt; **Parametrar** &gt; **Detaljhandelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="ba889-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3.  <span data-ttu-id="ba889-111">Klicka på **Initiera**.</span><span class="sxs-lookup"><span data-stu-id="ba889-111">Click **Initialize**.</span></span>

<span data-ttu-id="ba889-112">Initiering skapar följande standard konfigurationsdata:</span><span class="sxs-lookup"><span data-stu-id="ba889-112">Initialization creates the following default configuration data:</span></span>

-   <span data-ttu-id="ba889-113">Retail scheduler jobb och subjobs</span><span class="sxs-lookup"><span data-stu-id="ba889-113">Retail scheduler jobs and subjobs</span></span>
-   <span data-ttu-id="ba889-114">Schema för butikskanal</span><span class="sxs-lookup"><span data-stu-id="ba889-114">Retail channel schema</span></span>
-   <span data-ttu-id="ba889-115">butik scheman</span><span class="sxs-lookup"><span data-stu-id="ba889-115">Retail distribution schedules</span></span>
-   <span data-ttu-id="ba889-116">Standard skärmlayouter, vilket inkluderar knappen raster, bilder och teman</span><span class="sxs-lookup"><span data-stu-id="ba889-116">Default screen layouts, which include button grids, images, and themes</span></span>
-   <span data-ttu-id="ba889-117">Tidzonsinformation</span><span class="sxs-lookup"><span data-stu-id="ba889-117">Time zone information</span></span>
-   <span data-ttu-id="ba889-118">Pointen-of-sale (POS)</span><span class="sxs-lookup"><span data-stu-id="ba889-118">Point-of-sale (POS) operations</span></span>
-   <span data-ttu-id="ba889-119">Kassabehörigheter</span><span class="sxs-lookup"><span data-stu-id="ba889-119">POS permissions</span></span>
-   <span data-ttu-id="ba889-120">Kanalrapporter</span><span class="sxs-lookup"><span data-stu-id="ba889-120">Channel reports</span></span>
-   <span data-ttu-id="ba889-121">Attributmetadata</span><span class="sxs-lookup"><span data-stu-id="ba889-121">Attribute metadata</span></span>
-   <span data-ttu-id="ba889-122">Enhet validering mallar</span><span class="sxs-lookup"><span data-stu-id="ba889-122">Entity validation templates</span></span>
-   <span data-ttu-id="ba889-123">Bakgrundsjobbet ska rensa handel Data Exchange sessionshistorik</span><span class="sxs-lookup"><span data-stu-id="ba889-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="ba889-124">Dessutom aktiveras loggar som är relaterade till PCI (Payment Card Industry; betalkortsbranschen) för Dynamics 365 for Retail-databasen.</span><span class="sxs-lookup"><span data-stu-id="ba889-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span> <span data-ttu-id="ba889-125">**Obs!** Det finns ett alternativ till separat konfigurering av butiksplanering.</span><span class="sxs-lookup"><span data-stu-id="ba889-125">**Note:** There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="ba889-126">Det här alternativet låter dig återställa Retail scheduler konfigurationen till standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="ba889-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span> <span data-ttu-id="ba889-127">Efter initialiseringen är klar måste du konfigurera ytterligare retail data.</span><span class="sxs-lookup"><span data-stu-id="ba889-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="ba889-128">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="ba889-128">Here are some examples:</span></span>

-   <span data-ttu-id="ba889-129">Butiksparametrar</span><span class="sxs-lookup"><span data-stu-id="ba889-129">Retail parameters</span></span>
-   <span data-ttu-id="ba889-130">Parametrar för Butik schemaläggare</span><span class="sxs-lookup"><span data-stu-id="ba889-130">Retail scheduler parameters</span></span>
-   <span data-ttu-id="ba889-131">Butikskanaler</span><span class="sxs-lookup"><span data-stu-id="ba889-131">Retail channels</span></span>
-   <span data-ttu-id="ba889-132">Register och enheter</span><span class="sxs-lookup"><span data-stu-id="ba889-132">Registers and devices</span></span>
-   <span data-ttu-id="ba889-133">Sortiment</span><span class="sxs-lookup"><span data-stu-id="ba889-133">Assortments</span></span>





