---
title: Strömlinjeformad medarbetarinmatning och navigering
description: Dataregistrering för arbetare i Dynamics 365 Talent har förbättrats för att möjliggöra snabbregistrering för alla medarbetare, tidigare, aktiva eller framtida. En förenklad/konsoliderad navigeringsmodell har uppdaterats för att snabbt hitta relaterad information och visa och göra nödvändiga uppdateringar.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: b73b420c2eb75077814fbfeb6cd17404c7efc11e
ms.sourcegitcommit: 436731d8b3889bebfe6f17922b0a31b1994f6796
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2020
ms.locfileid: "4462651"
---
# <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="fe6b6-104">Strömlinjeformad medarbetarinmatning och navigering</span><span class="sxs-lookup"><span data-stu-id="fe6b6-104">Streamlined employee entry and navigation</span></span>

<span data-ttu-id="fe6b6-105">Dynamics 365 Talent gör det möjligt att registrera medarbetar- och anställningsdata effektivt.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-105">Dynamics 365 Talent allows efficient entry of employee and employment data.</span></span> <span data-ttu-id="fe6b6-106">Du kan snabbt uppdatera information om arbetshistorik för tidigare, aktiva och framtida medarbetare och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-106">You can quickly update work history information for past, active, and future employees and contractors.</span></span>

<span data-ttu-id="fe6b6-107">Du kan också aktivera en förenklad navigeringsupplevelse om du snabbt vill hitta relaterad information och göra nödvändiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-107">You can also enable a simplified navigation experience to quickly find related information and make any necessary changes.</span></span> <span data-ttu-id="fe6b6-108">Den här funktionen är nu tillgänglig i alla miljöer med begränsat läge.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-108">This functionality is now available in all environments.</span></span> <span data-ttu-id="fe6b6-109">Om du vill aktivera funktionen navigerar du till **Systemadministration > funktionshantering > ny > strömlinjeformad medarbetarpost > aktivera**.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-109">To turn this feature on, navigate to **System administration > Feature Management > New > Streamlined employee entry > Enable**.</span></span> <span data-ttu-id="fe6b6-110">Detta aktiverar dessa ändringar för alla användare.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-110">This will enable these changes for all users.</span></span> <span data-ttu-id="fe6b6-111">Du kan stänga av det här alternativet när du vill.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-111">You can turn this option off at any time.</span></span>

## <a name="view-options"></a><span data-ttu-id="fe6b6-112">Visningsalternativ</span><span class="sxs-lookup"><span data-stu-id="fe6b6-112">View options</span></span>

<span data-ttu-id="fe6b6-113">Du kan använda **visningsalternativen** i arbetarens formulär för att välja valfri kombination av medarbetare och leverantörer från en enda lista.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-113">You can use **View options** on the worker form to select any combination of employees and contractors from a single list.</span></span> <span data-ttu-id="fe6b6-114">Med dessa alternativ kan du visa arbetare över juridiska personer eller för den juridiska personen som du för närvarande är inloggad i.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-114">These options allow you to view workers across legal entities or for the legal entity you're currently signed into.</span></span> <span data-ttu-id="fe6b6-115">Du kan även visa aktiva, pågående och avslutade arbetare och du kan begränsa resultaten baserat på typen av arbetare (medarbetare eller leverantör).</span><span class="sxs-lookup"><span data-stu-id="fe6b6-115">You can also view active, pending, and exited workers, and you can restrict results based on the type of worker (employee or contractor).</span></span> <span data-ttu-id="fe6b6-116">Om avancerad säkerhet är aktiverad visas endast medarbetare och leverantörer i de juridiska personer som du har tillgång till.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-116">If advanced security is enabled, you will only see those employees and contractors in the legal entities you have access to.</span></span>

<span data-ttu-id="fe6b6-117">Kolumnerna i listvyn ändras utifrån dina val.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-117">Columns in the list view change based on your selections.</span></span> <span data-ttu-id="fe6b6-118">När du t.ex. visar avslutade medarbetare visas uppsägningsdatum och orsakskoder som ytterligare kolumner i listan.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-118">For example, when viewing exited employees, the termination date and reason codes display as additional columns in the list.</span></span> 

<span data-ttu-id="fe6b6-119">[![Visningsalternativ](./media/Worker-view-option.png)](./media/worker-view-option.png)</span><span class="sxs-lookup"><span data-stu-id="fe6b6-119">[![View options](./media/Worker-view-option.png)](./media/worker-view-option.png)</span></span>

## <a name="navigation-and-banner"></a><span data-ttu-id="fe6b6-120">Navigering och banderoll</span><span class="sxs-lookup"><span data-stu-id="fe6b6-120">Navigation and banner</span></span>

<span data-ttu-id="fe6b6-121">En banderoll visar viktig information för varje arbetare.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-121">A banner displays key information for each worker.</span></span> <span data-ttu-id="fe6b6-122">Banderollen för aktiva arbetare visar följande fält:</span><span class="sxs-lookup"><span data-stu-id="fe6b6-122">The banner for active workers displays the following fields:</span></span>

- <span data-ttu-id="fe6b6-123">**Rubrik**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-123">**Title**</span></span>
- <span data-ttu-id="fe6b6-124">**Avdelning**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-124">**Department**</span></span>
- <span data-ttu-id="fe6b6-125">**Befattningstyp**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-125">**Position type**</span></span>
- <span data-ttu-id="fe6b6-126">**Typ av arbetare**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-126">**Worker type**</span></span>
- <span data-ttu-id="fe6b6-127">**VD**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-127">**Manager**</span></span>
- <span data-ttu-id="fe6b6-128">**Juridisk person**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-128">**Legal entity**</span></span>

<span data-ttu-id="fe6b6-129">Banderollen för avslutade arbetare visar följande fält:</span><span class="sxs-lookup"><span data-stu-id="fe6b6-129">The banner for exited workers displays the following fields:</span></span>

- <span data-ttu-id="fe6b6-130">**Avslutat den**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-130">**Exited date**</span></span>
- <span data-ttu-id="fe6b6-131">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-131">**Reason**</span></span>

<span data-ttu-id="fe6b6-132">Banderollen för väntande arbetare visar följande fält:</span><span class="sxs-lookup"><span data-stu-id="fe6b6-132">The banner for pending employees displays the following fields:</span></span>

- <span data-ttu-id="fe6b6-133">**Rubrik**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-133">**Title**</span></span>
- <span data-ttu-id="fe6b6-134">**Avdelning**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-134">**Department**</span></span>
- <span data-ttu-id="fe6b6-135">**Befattningstyp**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-135">**Position type**</span></span>
- <span data-ttu-id="fe6b6-136">**VD**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-136">**Manager**</span></span>
- <span data-ttu-id="fe6b6-137">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-137">**Starting date**</span></span>
- <span data-ttu-id="fe6b6-138">**Juridisk person**</span><span class="sxs-lookup"><span data-stu-id="fe6b6-138">**Legal entity**</span></span>

<span data-ttu-id="fe6b6-139">Åtgärdsfönstret på arbetarsidan har ordnats om så att färre alternativ kan användas.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-139">The action pane of the worker page has been re-organized to include fewer options.</span></span> <span data-ttu-id="fe6b6-140">Informationen ordnas nu i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="fe6b6-140">Information is now organized in the following categories:</span></span> 

- <span data-ttu-id="fe6b6-141">Arbete</span><span class="sxs-lookup"><span data-stu-id="fe6b6-141">Work</span></span>
- <span data-ttu-id="fe6b6-142">Person</span><span class="sxs-lookup"><span data-stu-id="fe6b6-142">Person</span></span>
- <span data-ttu-id="fe6b6-143">Tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="fe6b6-143">Leave</span></span>
- <span data-ttu-id="fe6b6-144">Kompensation</span><span class="sxs-lookup"><span data-stu-id="fe6b6-144">Compensation</span></span>
- <span data-ttu-id="fe6b6-145">Förmåner</span><span class="sxs-lookup"><span data-stu-id="fe6b6-145">Benefits</span></span>
- <span data-ttu-id="fe6b6-146">Regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="fe6b6-146">Compliance</span></span>

<span data-ttu-id="fe6b6-147">Dessutom ger en ny flik **länk** på huvudarbetarsidan användare en central plats för åtkomst till all relaterad information för en arbetare.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-147">In addition, a new **Links** tab on the main worker page gives users a central location to access all related information for a worker.</span></span>

<span data-ttu-id="fe6b6-148">På grund av dessa ändringar kan information visas på en annan plats än du brukar.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-148">Due to these changes, information may appear in a different location than you're used to.</span></span> <span data-ttu-id="fe6b6-149">Löneinformation som tidigare har visats i formuläret arbetare visas till exempel i åtgärdsfönstret under **kompensation > lön** och fliken **personliga uppgifter** innehåller nu knappen **mer information** om du vill dölja fält som ofta används.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-149">For example, payroll information that previously displayed on the worker form now appears in the action pane under **Compensation > Payroll**, and the **Personal information** tab now has a **More information** button to hide fields that aren't accessed often.</span></span>

<span data-ttu-id="fe6b6-150">[![Banner](./media/Banner.png)](./media/Banner.png)</span><span class="sxs-lookup"><span data-stu-id="fe6b6-150">[![Banner](./media/Banner.png)](./media/Banner.png)</span></span>

## <a name="work-history"></a><span data-ttu-id="fe6b6-151">Arbetshistorik</span><span class="sxs-lookup"><span data-stu-id="fe6b6-151">Work history</span></span>

<span data-ttu-id="fe6b6-152">Fliken **Arbetshistorik** visar arbetshistoriken för alla juridiska personer och den är tillgänglig för stängning, aktiv och väntande medarbetare och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-152">The **Work history** tab shows work history across all legal entities and is available for exited, active, and pending employees and contractors.</span></span> <span data-ttu-id="fe6b6-153">Du kan nu visa all arbetshistorik samtidigt för de juridiska personer som du har tillgång till.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-153">You can now view all work history at once for the legal entities you have access to.</span></span> <span data-ttu-id="fe6b6-154">Dessutom kan du redigera information för varje post i arbetshistorik utan att ändra datakontexten.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-154">In addition, you can edit information for each of the work history entries without changing the data context.</span></span> <span data-ttu-id="fe6b6-155">Du kan uppdatera all information direkt på sidan.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-155">You can update all information directly on the page.</span></span> 

<span data-ttu-id="fe6b6-156">[![Arbetshistorik](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span><span class="sxs-lookup"><span data-stu-id="fe6b6-156">[![Work history](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span></span>

## <a name="position-history"></a><span data-ttu-id="fe6b6-157">Positionshistorik</span><span class="sxs-lookup"><span data-stu-id="fe6b6-157">Position history</span></span>

<span data-ttu-id="fe6b6-158">Fliken **befattningar** på huvudarbetarsidan ger en fullständig översikt över alla befattningar inom organisationen, inklusive tidigare, närvarande och eventuella framtida tilldelningar.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-158">The **Positions** tab on the main worker page provides a full view of all positions held within the organization, including past, present, and any future assignments.</span></span> <span data-ttu-id="fe6b6-159">Du kan fortfarande gå direkt till arbetarens befattningshistorik i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fe6b6-159">You can still navigate directly to the worker's position history in the action pane as well.</span></span>

<span data-ttu-id="fe6b6-160">[![Befattningar](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span><span class="sxs-lookup"><span data-stu-id="fe6b6-160">[![Positions](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span></span>

