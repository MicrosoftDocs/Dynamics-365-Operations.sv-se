---
title: Ställ in orsakskoder
description: Dynamics 365 Human Resources använder orsakskoder för att förklara varför en medarbetares förmåner ändras.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae82c8312d344f5380adec8413766304681a0a05
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114277"
---
# <a name="set-up-reason-codes"></a><span data-ttu-id="bf399-103">Ställ in orsakskoder</span><span class="sxs-lookup"><span data-stu-id="bf399-103">Set up reason codes</span></span>

<span data-ttu-id="bf399-104">Dynamics 365 Human Resources använder orsakskoder för att förklara varför en medarbetares förmåner ändras.</span><span class="sxs-lookup"><span data-stu-id="bf399-104">Dynamics 365 Human Resources uses reason codes to explain why an employee’s benefits are changing.</span></span>

> [!NOTE]
> <span data-ttu-id="bf399-105">Från och med januari 2021 migrerar orsakskoderna till arbetsytan **Personalhantering** istället för till arbetsytan **Förmånshantering**.</span><span class="sxs-lookup"><span data-stu-id="bf399-105">As of January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="bf399-106">Mer information finns i [Flytta orsakskoder till Personalhantering manuellt](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span><span class="sxs-lookup"><span data-stu-id="bf399-106">For more information, see [Manually migrate reason codes to Personnel management](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span></span>

## <a name="create-reason-codes"></a><span data-ttu-id="bf399-107">Skapa orsakskoder</span><span class="sxs-lookup"><span data-stu-id="bf399-107">Create reason codes</span></span>

1. <span data-ttu-id="bf399-108">I arbetsytan **Personalhantering** (eller arbetsytan **Förmånshantering**, om dina orsakskoder ännu inte har migrerats) väljer du **Länkar** och sedan **Orsakskoder**.</span><span class="sxs-lookup"><span data-stu-id="bf399-108">In the **Personnel management** workspace (or **Benefits management** workspace if your reason codes haven't yet migrated), select **Links**, and then select **Reason codes**.</span></span>

2. <span data-ttu-id="bf399-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bf399-109">Select **New**.</span></span>

3. <span data-ttu-id="bf399-110">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="bf399-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="bf399-111">Fält</span><span class="sxs-lookup"><span data-stu-id="bf399-111">Field</span></span> | <span data-ttu-id="bf399-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bf399-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="bf399-113">**Orsakskod**</span><span class="sxs-lookup"><span data-stu-id="bf399-113">**Reason code**</span></span> | <span data-ttu-id="bf399-114">Ett unikt namn som identifierar orsaken till att en medarbetare ändrar en anmälan av förmånsplan.</span><span class="sxs-lookup"><span data-stu-id="bf399-114">A unique name to identify the reason an employee would change a benefit plan enrollment.</span></span> |
   | <span data-ttu-id="bf399-115">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="bf399-115">**Description**</span></span> | <span data-ttu-id="bf399-116">En beskrivning av orsakskoden.</span><span class="sxs-lookup"><span data-stu-id="bf399-116">A description of the reason code.</span></span> |

4. <span data-ttu-id="bf399-117">Under **Tillämpliga scenarier** anger du **Förmånshantering** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bf399-117">Under **Applicable scenarios**, set **Benefits management** to **Yes**.</span></span> <span data-ttu-id="bf399-118">(Ej tillämpligt om orsakskoderna ännu inte migrerat till arbetsytan **Personalhantering**)</span><span class="sxs-lookup"><span data-stu-id="bf399-118">(Not applicable if your reason codes haven't yet migrated to the **Personnel management** workspace.)</span></span>

5. <span data-ttu-id="bf399-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bf399-119">Select **Save**.</span></span>

## <a name="manually-migrate-reason-codes-to-personnel-management"></a><span data-ttu-id="bf399-120">Flytta orsakskoder till Personalhantering manuellt</span><span class="sxs-lookup"><span data-stu-id="bf399-120">Manually migrate reason codes to Personnel management</span></span>

<span data-ttu-id="bf399-121">I januari 2021 migrerar orsakskoderna till arbetsytan **Personalhantering** istället för till arbetsytan **Förmånshantering**.</span><span class="sxs-lookup"><span data-stu-id="bf399-121">In January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="bf399-122">De flesta orsakskoddata migrerar automatiskt i din miljö.</span><span class="sxs-lookup"><span data-stu-id="bf399-122">Most reason code data will automatically migrate in your environment.</span></span> <span data-ttu-id="bf399-123">Vissa orsakskoddata kanske inte migrerar.</span><span class="sxs-lookup"><span data-stu-id="bf399-123">Some reason code data might not migrate.</span></span> <span data-ttu-id="bf399-124">Exempelvis har orsakskoder nu högst 15 tecken, varför orsakskoder som är längre än 15 tecken inte migrerar automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bf399-124">For example, reason codes now have a 15-character maximum, so any reason codes longer than 15 characters won't migrate automatically.</span></span>

<span data-ttu-id="bf399-125">Du kommer att se en banner på sidan **Länkar** i arbetsytan **Förmånshantering** som informerar dig om migreringen och om någon orsakskod inte migrerar.</span><span class="sxs-lookup"><span data-stu-id="bf399-125">You'll see a banner on the **Links** page of the **Benefits management** workspace informing you about the migration and whether any reason codes didn't migrate.</span></span>

1. <span data-ttu-id="bf399-126">Välj **Orsakskoder** om du vill ha mer information om migreringsstatus.</span><span class="sxs-lookup"><span data-stu-id="bf399-126">Select **Reason codes** for details about migration status.</span></span>

   <span data-ttu-id="bf399-127">[![Orsakskoder](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span><span class="sxs-lookup"><span data-stu-id="bf399-127">[![Reason codes](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span></span>

2. <span data-ttu-id="bf399-128">Välj en orsakskod som inte migrerade.</span><span class="sxs-lookup"><span data-stu-id="bf399-128">Select a reason code that failed to migrate.</span></span>

   <span data-ttu-id="bf399-129">[![Status för orsakskodsmigrering](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span><span class="sxs-lookup"><span data-stu-id="bf399-129">[![Reason code migration status](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span></span>

3. <span data-ttu-id="bf399-130">Välj **Orsakskod för migrering**.</span><span class="sxs-lookup"><span data-stu-id="bf399-130">Select **Migrate reason code**.</span></span>

   <span data-ttu-id="bf399-131">[![Migrera orsakskod](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span><span class="sxs-lookup"><span data-stu-id="bf399-131">[![Migrate reason code](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span></span>

4. <span data-ttu-id="bf399-132">I fönstret **Migrering av orsakskod för förmån** har du två alternativ för att mappa till en orsakskod för personalhantering:</span><span class="sxs-lookup"><span data-stu-id="bf399-132">In the **Benefit reason code migration** pane, you have two options for mapping to a Personnel management reason code:</span></span>

   - <span data-ttu-id="bf399-133">Om du vill använda en befintlig orsakskod i Personalhantering kan du välja en från listrutan **Använd befintlig orsakskod**.</span><span class="sxs-lookup"><span data-stu-id="bf399-133">To use an existing reason code in Personnel management, choose one from the **Use existing reason code** dropdown.</span></span>
     > [!NOTE]
     > <span data-ttu-id="bf399-134">Du kan bara använda en befintlig orsakskod i Personalhantering om en annan orsakskod för förmånshantering inte redan har migrerats till den.</span><span class="sxs-lookup"><span data-stu-id="bf399-134">You can only use an existing reason code in Personnel management if another Benefits management reason code hasn't already migrated to it.</span></span>
   - <span data-ttu-id="bf399-135">Om du vill skapa en ny orsakskod i Personalhantering anger du en ny i **Ny orsakskod** innan du anger en beskrivning i **Ny beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="bf399-135">To create a new reason code in Personnel management, enter a new one in **New reason code**, and then enter a description in **New description**.</span></span>

   <span data-ttu-id="bf399-136">[![Mappa till en orsakskod för personalhantering](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span><span class="sxs-lookup"><span data-stu-id="bf399-136">[![Map to a Personnel management reason code](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span></span>

<span data-ttu-id="bf399-137">När orsakskoderna migrerar till Personalhantering ställs alternativet för användning av dem i Förmånshantering automatiskt in som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bf399-137">After reason codes migrate to Personnel management, the option for using them in Benefits management is automatically set to **Yes**.</span></span>

<span data-ttu-id="bf399-138">[![Använd orsakskoder i Förmånshantering](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span><span class="sxs-lookup"><span data-stu-id="bf399-138">[![Use reason code in Benefits management](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span></span>