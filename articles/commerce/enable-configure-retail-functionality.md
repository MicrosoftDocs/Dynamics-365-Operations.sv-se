---
title: Initiera startdata i nya Commerce-miljöer
description: Den här artikeln beskriver de data som har skapats som en del av initieringsprocessen för Dynamics 365 Commerce.
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
ms.openlocfilehash: 24d4d49c51738203bb89a9844d57f644b8afd4b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415742"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a><span data-ttu-id="3220f-103">Initiera startdata i nya Commerce-miljöer</span><span class="sxs-lookup"><span data-stu-id="3220f-103">Initialize seed data in new Commerce environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3220f-104">Den här artikeln beskriver de data som har skapats som en del av initieringsprocessen för Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3220f-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3220f-105">Efter lösning har spridits via Microsoft Dynamics Lifecycle Services (LCS), måste du initiera handelskonfiguration för att skapa grundläggande konfigurationsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3220f-105">After the Commerce solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the Commerce configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3220f-106">Innan du initierar handelskonfiguration, kontrollera att du har angett ett språk och en postadress för varje juridisk enhet där du ställer upp butiker.</span><span class="sxs-lookup"><span data-stu-id="3220f-106">Before you initialize the commerce configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up stores.</span></span> <span data-ttu-id="3220f-107">Detta steg måste genomföras för varje juridisk enhet som du använder för handel.</span><span class="sxs-lookup"><span data-stu-id="3220f-107">This step must be completed for each legal entity that you use for commerce.</span></span>

<span data-ttu-id="3220f-108">För att initiera konfiguration, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="3220f-108">To initialize the configuration, follow these steps.</span></span>

1. <span data-ttu-id="3220f-109">Starta Handelsklienten.</span><span class="sxs-lookup"><span data-stu-id="3220f-109">Start the Commerce client.</span></span>
2. <span data-ttu-id="3220f-110">Klicka på **Butik och handel** &gt; **Administrationsinställning** &gt; **Parametrar** &gt; **Handelparametrar**.</span><span class="sxs-lookup"><span data-stu-id="3220f-110">Click **Retail and Commerce** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Commerce parameters**.</span></span>
3. <span data-ttu-id="3220f-111">Klicka på **Initiera**.</span><span class="sxs-lookup"><span data-stu-id="3220f-111">Click **Initialize**.</span></span>

<span data-ttu-id="3220f-112">Initiering skapar följande standard konfigurationsdata:</span><span class="sxs-lookup"><span data-stu-id="3220f-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="3220f-113">Handelsschemaläggare jobb och deljobb</span><span class="sxs-lookup"><span data-stu-id="3220f-113">Commerce scheduler jobs and subjobs</span></span>
- <span data-ttu-id="3220f-114">Handelskanalschema</span><span class="sxs-lookup"><span data-stu-id="3220f-114">Commerce channel schema</span></span>
- <span data-ttu-id="3220f-115">Distributionsplaner för handel</span><span class="sxs-lookup"><span data-stu-id="3220f-115">Commerce distribution schedules</span></span>
- <span data-ttu-id="3220f-116">Standard skärmlayouter, vilket inkluderar knappen raster, bilder och teman</span><span class="sxs-lookup"><span data-stu-id="3220f-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="3220f-117">Tidzonsinformation</span><span class="sxs-lookup"><span data-stu-id="3220f-117">Time zone information</span></span>
- <span data-ttu-id="3220f-118">Pointen-of-sale (POS)</span><span class="sxs-lookup"><span data-stu-id="3220f-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="3220f-119">Kassabehörigheter</span><span class="sxs-lookup"><span data-stu-id="3220f-119">POS permissions</span></span>
- <span data-ttu-id="3220f-120">Kanalrapporter</span><span class="sxs-lookup"><span data-stu-id="3220f-120">Channel reports</span></span>
- <span data-ttu-id="3220f-121">Attributmetadata</span><span class="sxs-lookup"><span data-stu-id="3220f-121">Attribute metadata</span></span>
- <span data-ttu-id="3220f-122">Enhet validering mallar</span><span class="sxs-lookup"><span data-stu-id="3220f-122">Entity validation templates</span></span>
- <span data-ttu-id="3220f-123">Batch-jobb för att ta bort Commerce Data Exchange-sessionshistorik</span><span class="sxs-lookup"><span data-stu-id="3220f-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="3220f-124">Dessutom loggar som är relaterad till PCI (Payment Card Industry) är aktiverad för handelsdatabasen.</span><span class="sxs-lookup"><span data-stu-id="3220f-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Commerce database.</span></span>

> [!NOTE]
> <span data-ttu-id="3220f-125">Det finns ett alternativ till separat konfigurering av handelsschemaläggare.</span><span class="sxs-lookup"><span data-stu-id="3220f-125">There is an option to separately configure the Commerce scheduler.</span></span> <span data-ttu-id="3220f-126">Det här alternativet låter dig återställa konfigurationen av handelsschemaläggare till standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="3220f-126">This option lets you reset the Commerce scheduler configuration to its default settings.</span></span>

<span data-ttu-id="3220f-127">Efter initialiseringen är klar måste du konfigurera ytterligare handelsdata.</span><span class="sxs-lookup"><span data-stu-id="3220f-127">After initialization is completed, you must configure additional commerce data.</span></span> <span data-ttu-id="3220f-128">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="3220f-128">Here are some examples:</span></span>

- <span data-ttu-id="3220f-129">Handelsparametrar</span><span class="sxs-lookup"><span data-stu-id="3220f-129">Commerce parameters</span></span>
- <span data-ttu-id="3220f-130">Parametrar för handelsschemaläggare</span><span class="sxs-lookup"><span data-stu-id="3220f-130">Commerce scheduler parameters</span></span>
- <span data-ttu-id="3220f-131">Handelskanaler</span><span class="sxs-lookup"><span data-stu-id="3220f-131">Commerce channels</span></span>
- <span data-ttu-id="3220f-132">Register och enheter</span><span class="sxs-lookup"><span data-stu-id="3220f-132">Registers and devices</span></span>
- <span data-ttu-id="3220f-133">Sortiment</span><span class="sxs-lookup"><span data-stu-id="3220f-133">Assortments</span></span>
