---
title: Funktioner för avvikelser
description: I detta ämne beskrivs hur du skapar och använder funktioner för avvikelser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9a6cc88b80f82d77edac0341cb6a3c0db4b42ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022214"
---
# <a name="operations-for-nonconformances"></a><span data-ttu-id="52358-103">Funktioner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="52358-103">Operations for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52358-104">I detta ämne beskrivs hur du skapar och använder funktioner för avvikelser.</span><span class="sxs-lookup"><span data-stu-id="52358-104">This topic describes how to create and use operations for nonconformances.</span></span>

<span data-ttu-id="52358-105">Du kan använda sidan **Funktioner** för att definiera klassificeringen av det arbete som kan utföras för en godkänd avvikelse.</span><span class="sxs-lookup"><span data-stu-id="52358-105">You can use the **Operations** page to define classifications of the work that can be performed for an approved nonconformance.</span></span> <span data-ttu-id="52358-106">När en relaterad funktion tilldelas till en avvikelse kan du definiera detaljerad information om tillhörande material, arbetstid och avgifter som krävs för att funktionen ska kunna genomföras.</span><span class="sxs-lookup"><span data-stu-id="52358-106">When you assign a related operation to a nonconformance, you can provide details such as the associated material, labor hours, and charges that are required to do the operation.</span></span> <span data-ttu-id="52358-107">Systemet använder denna information för att beräkna en uppskattad kostnad för funktionen.</span><span class="sxs-lookup"><span data-stu-id="52358-107">The system uses this information to calculate an estimated cost for the operation.</span></span> <span data-ttu-id="52358-108">Den detaljerade informationen och de uppskattade kostnaderna anges i referenssyfte.</span><span class="sxs-lookup"><span data-stu-id="52358-108">The detailed information and estimated costs are for reference.</span></span> <span data-ttu-id="52358-109">Relaterade kvalitetsoperationer skiljer sig från de operationer som kan definieras för ett produktionsflöde.</span><span class="sxs-lookup"><span data-stu-id="52358-109">The related operations for quality differ from the operations that can be defined for a production route.</span></span>

> [!NOTE]
> <span data-ttu-id="52358-110">Även om du kan spåra kostnader, tid och artiklar som används i en funktion som hör till en avvikelse är de data som du anger bara information.</span><span class="sxs-lookup"><span data-stu-id="52358-110">Although you can track costs, time, and the items that are used in an operation that is related to a nonconformance, the data that you enter is only informational.</span></span> <span data-ttu-id="52358-111">Datan integreras inte automatiskt med redovisningen, lagerredovisningen eller modulen **Tid och närvaro**.</span><span class="sxs-lookup"><span data-stu-id="52358-111">It isn't automatically integrated with the general ledger, inventory subledger, or the **Time and attendance** module.</span></span>

## <a name="examples-of-operations"></a><span data-ttu-id="52358-112">Exempel på funktioner</span><span class="sxs-lookup"><span data-stu-id="52358-112">Examples of operations</span></span>

<span data-ttu-id="52358-113">Du arbetar för ett tillverkningsföretag.</span><span class="sxs-lookup"><span data-stu-id="52358-113">You work for a manufacturing company.</span></span> <span data-ttu-id="52358-114">En avvikelse har skapats och godkänts för artiklar som misslyckats i ett kvalitetstest.</span><span class="sxs-lookup"><span data-stu-id="52358-114">A nonconformance was created and approved for items that failed a quality test.</span></span> <span data-ttu-id="52358-115">En korrigering har skapats för att visa att problemet berodde på ett trasigt lager på en maskin.</span><span class="sxs-lookup"><span data-stu-id="52358-115">A correction was created to indicate that the problem was related to a bad bearing on a machine.</span></span> <span data-ttu-id="52358-116">Flera steg krävs för att ersätta lagret, och ansvarsområdet för varje funktion spåras.</span><span class="sxs-lookup"><span data-stu-id="52358-116">Several steps are required to replace the bearing, and the responsibility for each operation is tracked.</span></span> <span data-ttu-id="52358-117">Följande steg kan till exempel krävas:</span><span class="sxs-lookup"><span data-stu-id="52358-117">For example, the following steps might be required:</span></span>

1. <span data-ttu-id="52358-118">Produktionsraden stoppas och rensningsrutinen utförs.</span><span class="sxs-lookup"><span data-stu-id="52358-118">The production line is stopped, and the clean-out routine is performed.</span></span>
1. <span data-ttu-id="52358-119">Underhållspersonal ersätter lagret.</span><span class="sxs-lookup"><span data-stu-id="52358-119">Maintenance personnel replace the bearing.</span></span>
1. <span data-ttu-id="52358-120">Kvalitetssäkringspersonal inspekterar maskinen innan den återaktiveras.</span><span class="sxs-lookup"><span data-stu-id="52358-120">Quality assurance personnel inspect the machine before it's turned back on.</span></span>

<span data-ttu-id="52358-121">I det här exemplet kan följande funktioner skapas i syfte att representera det arbete som måste utföras:</span><span class="sxs-lookup"><span data-stu-id="52358-121">For this example, the following operations can be created to represent the work that must be done:</span></span>

- <span data-ttu-id="52358-122">Stoppa produktionsraden.</span><span class="sxs-lookup"><span data-stu-id="52358-122">Stop the production line.</span></span>
- <span data-ttu-id="52358-123">Rensa produktionsraden.</span><span class="sxs-lookup"><span data-stu-id="52358-123">Clean out the production line.</span></span>
- <span data-ttu-id="52358-124">Utföra maskinunderhåll.</span><span class="sxs-lookup"><span data-stu-id="52358-124">Perform machine maintenance.</span></span>
- <span data-ttu-id="52358-125">Inspektera maskinen.</span><span class="sxs-lookup"><span data-stu-id="52358-125">Inspect the machine.</span></span>

## <a name="create-an-operation"></a><span data-ttu-id="52358-126">Skapa en funktion</span><span class="sxs-lookup"><span data-stu-id="52358-126">Create an operation</span></span>

1. <span data-ttu-id="52358-127">Gå till **Lagerhantering \> Inställningar \> Kvalitetshantering \> Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="52358-127">Go to **Inventory management \> Setup \> Quality management \> Operations**.</span></span>
1. <span data-ttu-id="52358-128">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="52358-128">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="52358-129">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="52358-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="52358-130">**Funktion** – Ange ett unikt ID eller namn för funktionen.</span><span class="sxs-lookup"><span data-stu-id="52358-130">**Operation** – Enter a unique ID or name for the operation.</span></span>
    - <span data-ttu-id="52358-131">**Beskrivning** – Ange en detaljerad beskrivning av funktionen.</span><span class="sxs-lookup"><span data-stu-id="52358-131">**Description** – Enter a detailed description of the operation.</span></span>
    - <span data-ttu-id="52358-132">**Typ** – Om åtgärden bara kan användas för avvikelser som är relaterade till en viss ordertyp väljer du ordertypen (*inköpsorder* eller *försäljningsorder*).</span><span class="sxs-lookup"><span data-stu-id="52358-132">**Type** – If the operation can be used only with nonconformances that are related to a specific type of order, select the order type (*Purchase order* or *Sales order*).</span></span>

1. <span data-ttu-id="52358-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="52358-133">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52358-134">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="52358-134">Additional resources</span></span>

- [<span data-ttu-id="52358-135">Kvalitetshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="52358-135">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="52358-136">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="52358-136">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="52358-137">Skapa och bearbeta avvikelser</span><span class="sxs-lookup"><span data-stu-id="52358-137">Create and process nonconformances</span></span>](tasks/create-process-non-conformance.md)
- [<span data-ttu-id="52358-138">Medarbetare som ansvarar för godkännande av avvikelser</span><span class="sxs-lookup"><span data-stu-id="52358-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="52358-139">Karantänzoner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="52358-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="52358-140">Diagnostyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="52358-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="52358-141">Kvalitetsavgifter för avvikelser</span><span class="sxs-lookup"><span data-stu-id="52358-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="52358-142">Problemtyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="52358-142">Problem types for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="52358-143">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="52358-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
