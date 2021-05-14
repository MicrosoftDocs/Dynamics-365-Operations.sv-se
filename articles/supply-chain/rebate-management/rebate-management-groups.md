---
title: Rabatthanteringsgrupper
description: I det här avsnittet beskrivs hur du ställer in Rabatthanteringsgrupper. Rabatthanteringsgrupper kan användas under rabattberäkningar och kan kopplas till en huvudpost.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: cef7abbbf2a94e26b6b9e66492cd7347d3b4d1f2
ms.sourcegitcommit: 890a0b3eb3c1f48d786b0789e5bb8641e0b8455e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920071"
---
# <a name="rebate-management-groups"></a><span data-ttu-id="b4238-104">Rabatthanteringsgrupper</span><span class="sxs-lookup"><span data-stu-id="b4238-104">Rebate management groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4238-105">Rabatt- och avdragsberäkningar kan baseras på grupper.</span><span class="sxs-lookup"><span data-stu-id="b4238-105">Rebate and deduction calculations can be driven by groups.</span></span> <span data-ttu-id="b4238-106">Rabatthanteringsgrupper kan skapas för kunder, leverantörer och artiklar.</span><span class="sxs-lookup"><span data-stu-id="b4238-106">Rebate management groups can be created for customers, vendors, and items.</span></span> <span data-ttu-id="b4238-107">De kan kopplas till en huvudpost.</span><span class="sxs-lookup"><span data-stu-id="b4238-107">They can be attached to a master record.</span></span>

## <a name="rebate-management-customer-groups"></a><span data-ttu-id="b4238-108">Rabatthanteringsgrupper för kunder</span><span class="sxs-lookup"><span data-stu-id="b4238-108">Rebate management customer groups</span></span>

<span data-ttu-id="b4238-109">Beräkningen för en grupp av kunder skapas ofta för en företagskedja, till exempel en kedja eller ett franchiseföretag.</span><span class="sxs-lookup"><span data-stu-id="b4238-109">The calculation for a group of customers is often created for a chain of companies, such as a supermarket chain or a franchise company.</span></span> <span data-ttu-id="b4238-110">Den här typen av beräkning hör vanligtvis till en rabatt.</span><span class="sxs-lookup"><span data-stu-id="b4238-110">This type of calculation is usually related to a rebate.</span></span>

<span data-ttu-id="b4238-111">Ett avdrag beräknas ofta utan hänsyn till vem den godkända ordern såldes till.</span><span class="sxs-lookup"><span data-stu-id="b4238-111">A deduction is often calculated without considering who the qualifying order was sold to.</span></span> <span data-ttu-id="b4238-112">Det finns dock några undantag.</span><span class="sxs-lookup"><span data-stu-id="b4238-112">However, there are exceptions.</span></span> <span data-ttu-id="b4238-113">En licenstagare kan exempelvis skapa ett avdragsschema där kundgrupp A får 4 procent, men kundgrupp B får bara tre procent.</span><span class="sxs-lookup"><span data-stu-id="b4238-113">For example, a licensee might create a deduction scheme where customer group A will receive 4 percent, but customer group B will receive only 3 percent.</span></span>

### <a name="set-up-customer-groups"></a><span data-ttu-id="b4238-114">Ställ in kundgrupper</span><span class="sxs-lookup"><span data-stu-id="b4238-114">Set up customer groups</span></span>

<span data-ttu-id="b4238-115">Om du vill arbeta med kundgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Kundgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-115">To work with Rebate management customer groups, go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span> <span data-ttu-id="b4238-116">Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov.</span><span class="sxs-lookup"><span data-stu-id="b4238-116">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="b4238-117">För varje grupp anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="b4238-117">For each group, set the following fields:</span></span>

- <span data-ttu-id="b4238-118">**Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-118">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="b4238-119">**Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.</span><span class="sxs-lookup"><span data-stu-id="b4238-119">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-customer-group-assignments"></a><span data-ttu-id="b4238-120">Hantera kundgruppstilldelningar</span><span class="sxs-lookup"><span data-stu-id="b4238-120">Manage customer group assignments</span></span>

<span data-ttu-id="b4238-121">Varje kund kan tillhöra ett val annat antal rabatthanteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="b4238-121">Each customer can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="b4238-122">Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller kundlistan.</span><span class="sxs-lookup"><span data-stu-id="b4238-122">To view and assign group members, you can start from either the group list or the customer list.</span></span>

<span data-ttu-id="b4238-123">Följ de här stegen om du vill visa, lägga till eller ta bort kunder för den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-123">To view, add, or remove customers for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="b4238-124">Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Kundgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-124">Go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span>
1. <span data-ttu-id="b4238-125">Markera gruppen som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="b4238-125">Select the group to manage.</span></span>
1. <span data-ttu-id="b4238-126">I åtgärdsfönstret, välj **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="b4238-126">On the Action Pane, select **Customers**.</span></span> <span data-ttu-id="b4238-127">Sidan **Rabatthanteringsgrupper** visas och visar en lista med kunder som redan är medlemmar i den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-127">The **Rebate management groups** page appears and shows a list of customers that are already members of the selected group.</span></span>
1. <span data-ttu-id="b4238-128">Välj om du vill lägga till en ny kund i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b4238-128">To add a new customer to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="b4238-129">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="b4238-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b4238-130">**Kundkonto** – Välj kundkonto-ID.</span><span class="sxs-lookup"><span data-stu-id="b4238-130">**Customer account** – Select the customer account ID.</span></span>
    - <span data-ttu-id="b4238-131">**Namn** – Ange ett namn och/eller en beskrivning av kunden.</span><span class="sxs-lookup"><span data-stu-id="b4238-131">**Name** – Enter a name and/or description of the customer.</span></span>

1. <span data-ttu-id="b4238-132">Om du vill ta bort en kund från gruppen markerar du kunden och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-132">To remove a customer from the group, select the customer, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="b4238-133">Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald kund.</span><span class="sxs-lookup"><span data-stu-id="b4238-133">To view, add, or remove group assignments for a selected customer, follow these steps.</span></span>

1. <span data-ttu-id="b4238-134">Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="b4238-134">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="b4238-135">Välj den kund du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="b4238-135">Select the customer to work with.</span></span>
1. <span data-ttu-id="b4238-136">I åtgärdsfönstret på fliken **Kund** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-136">On the Action Pane, on the **Customer** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="b4238-137">Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda kunden redan tillhör.</span><span class="sxs-lookup"><span data-stu-id="b4238-137">The **Rebate management groups** page appears and shows a list of groups that the selected customer already belongs to.</span></span>
1. <span data-ttu-id="b4238-138">Välj om du vill lägga till en ny kund i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b4238-138">To add the customer to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="b4238-139">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="b4238-139">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b4238-140">**Rabatthanteringsgrupp** – Välj den grupp som kunden ska läggas till i.</span><span class="sxs-lookup"><span data-stu-id="b4238-140">**Rebate management group** – Select the group to add the customer to.</span></span>
    - <span data-ttu-id="b4238-141">**Beskrivning** – Ange en beskrivning av gruppen (till exempel för att förklara varför kunden är medlem i den).</span><span class="sxs-lookup"><span data-stu-id="b4238-141">**Description** – Enter a description of the group (for example, to explain why the customer is a member of it).</span></span>

1. <span data-ttu-id="b4238-142">Om du vill ta bort en kund från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-142">To remove a customer from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="rebate-management-vendor-groups"></a><span data-ttu-id="b4238-143">Rabatthantering för leverantörsgrupper</span><span class="sxs-lookup"><span data-stu-id="b4238-143">Rebate management vendor groups</span></span>

<span data-ttu-id="b4238-144">Beräkningen för en grupp av leverantörer skapas ofta för en grupp med leveranspunkter.</span><span class="sxs-lookup"><span data-stu-id="b4238-144">The calculation for a group of vendors is often created for a group of delivery points.</span></span> <span data-ttu-id="b4238-145">Den här typen av beräkning hör vanligtvis till en rabatt.</span><span class="sxs-lookup"><span data-stu-id="b4238-145">This type of calculation is usually related to a rebate.</span></span>

### <a name="set-up-vendor-groups"></a><span data-ttu-id="b4238-146">Ställ in leverantörsgrupper</span><span class="sxs-lookup"><span data-stu-id="b4238-146">Set up vendor groups</span></span>

<span data-ttu-id="b4238-147">Om du vill arbeta med leverantörsgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Leverantörsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-147">To work with Rebate management vendor groups, go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span> <span data-ttu-id="b4238-148">Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov.</span><span class="sxs-lookup"><span data-stu-id="b4238-148">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="b4238-149">För varje grupp anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="b4238-149">For each group, set the following fields:</span></span>

- <span data-ttu-id="b4238-150">**Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-150">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="b4238-151">**Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.</span><span class="sxs-lookup"><span data-stu-id="b4238-151">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-vendor-group-assignments"></a><span data-ttu-id="b4238-152">Hantera leverantörsgruppstilldelningar</span><span class="sxs-lookup"><span data-stu-id="b4238-152">Manage vendor group assignments</span></span>

<span data-ttu-id="b4238-153">Varje leverantör kan tillhöra ett val annat antal rabatthanteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="b4238-153">Each vendor can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="b4238-154">Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller leverantörlistan.</span><span class="sxs-lookup"><span data-stu-id="b4238-154">To view and assign group members, you can start from either the group list or the vendor list.</span></span>

<span data-ttu-id="b4238-155">Följ de här stegen om du vill visa, lägga till eller ta bort leverantör för den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-155">To view, add, or remove vendors for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="b4238-156">Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Leverantörsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-156">Go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span>
1. <span data-ttu-id="b4238-157">Markera gruppen som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="b4238-157">Select the group to manage.</span></span>
1. <span data-ttu-id="b4238-158">Klicka på **Leverantörer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-158">On the Action Pane, select **Vendors**.</span></span> <span data-ttu-id="b4238-159">Sidan **Rabatthanteringsgrupper** visas och visar en lista med leverantör som redan är medlemmar i den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-159">The **Rebate management groups** page appears and shows a list of vendors that are already members of the selected group.</span></span>
1. <span data-ttu-id="b4238-160">Välj om du vill lägga till en ny leverantör i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b4238-160">To add a new vendor to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="b4238-161">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="b4238-161">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b4238-162">**Leverantörskonto** – Välj leverantörskonto-ID.</span><span class="sxs-lookup"><span data-stu-id="b4238-162">**Vendor account** – Select the vendor account ID.</span></span>
    - <span data-ttu-id="b4238-163">**Namn** – Ange ett namn och/eller en beskrivning av leverantör.</span><span class="sxs-lookup"><span data-stu-id="b4238-163">**Name** – Enter a name and/or description of the vendor.</span></span>

1. <span data-ttu-id="b4238-164">Om du vill ta bort en leverantör från gruppen markerar du leverantören och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-164">To remove a vendor from the group, select the vendor, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="b4238-165">Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald leverantör.</span><span class="sxs-lookup"><span data-stu-id="b4238-165">To view, add, or remove group assignments for a selected vendor, follow these steps.</span></span>

1. <span data-ttu-id="b4238-166">Gå till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="b4238-166">Go to **Accounts payable \> Vendors \> All vendors**.</span></span>
1. <span data-ttu-id="b4238-167">Välj den leverantör du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="b4238-167">Select the vendor to work with.</span></span>
1. <span data-ttu-id="b4238-168">I åtgärdsfönstret på fliken **Leverantör** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-168">On the Action Pane, on the **Vendor** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="b4238-169">Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda leverantör redan tillhör.</span><span class="sxs-lookup"><span data-stu-id="b4238-169">The **Rebate management groups** page appears and shows a list of groups that the selected vendor already belongs to.</span></span>
1. <span data-ttu-id="b4238-170">Välj om du vill lägga till en leverantör i en ny grupp, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b4238-170">To add the vendor to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="b4238-171">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="b4238-171">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b4238-172">**Rabatthanteringsgrupp** – Välj den grupp som leverantören ska läggas till i.</span><span class="sxs-lookup"><span data-stu-id="b4238-172">**Rebate management group** – Select the group to add the vendor to.</span></span>
    - <span data-ttu-id="b4238-173">**Beskrivning** – Ange en beskrivning av gruppen (till exempel för att förklara varför leverantören är medlem i den).</span><span class="sxs-lookup"><span data-stu-id="b4238-173">**Description** – Enter a description of the group (for example, to explain why the vendor is a member of it).</span></span>

1. <span data-ttu-id="b4238-174">Om du vill ta bort en leverantör från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-174">To remove a vendor from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="item-rebate-groups"></a><span data-ttu-id="b4238-175">Artikelrabattgrupper</span><span class="sxs-lookup"><span data-stu-id="b4238-175">Item rebate groups</span></span>

<span data-ttu-id="b4238-176">Genom att gruppera artiklar blir du mer flexibel när rabatter och avdrag beräknas.</span><span class="sxs-lookup"><span data-stu-id="b4238-176">By grouping items, you have more flexibility when rebates and deductions are calculated.</span></span> <span data-ttu-id="b4238-177">Det här arbetssättet är ofta ett effektivare sätt att ställa in rabatter och avdrag för kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="b4238-177">This approach is often a more efficient way to set up rebates and deductions for customers and vendors.</span></span>

### <a name="set-up-item-groups"></a><span data-ttu-id="b4238-178">Ställ in artikelgrupper</span><span class="sxs-lookup"><span data-stu-id="b4238-178">Set up item groups</span></span>

<span data-ttu-id="b4238-179">Om du vill arbeta med artikelgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Atikelgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-179">To work with Rebate management item groups, go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span> <span data-ttu-id="b4238-180">Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov.</span><span class="sxs-lookup"><span data-stu-id="b4238-180">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="b4238-181">För varje grupp anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="b4238-181">For each group, set the following fields:</span></span>

- <span data-ttu-id="b4238-182">**Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-182">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="b4238-183">**Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.</span><span class="sxs-lookup"><span data-stu-id="b4238-183">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-item-group-assignments"></a><span data-ttu-id="b4238-184">Hantera artikelgruppstilldelningar</span><span class="sxs-lookup"><span data-stu-id="b4238-184">Manage item group assignments</span></span>

<span data-ttu-id="b4238-185">Varje artikel kan tillhöra ett val annat antal rabatthanteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="b4238-185">Each item can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="b4238-186">Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller artikellistan.</span><span class="sxs-lookup"><span data-stu-id="b4238-186">To view and assign group members, you can start from either the group list or the item list.</span></span> <span data-ttu-id="b4238-187">Du kan också lägga till artiklar utifrån kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="b4238-187">You can also add items based on your category hierarchy.</span></span>

<span data-ttu-id="b4238-188">Följ de här stegen om du vill visa, lägga till eller ta bort artiklar för den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-188">To view, add, or remove items for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="b4238-189">Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Artikelgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-189">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="b4238-190">Markera gruppen som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="b4238-190">Select the group to manage.</span></span>
1. <span data-ttu-id="b4238-191">Klicka på **Artiklar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-191">On the Action Pane, select **Items**.</span></span> <span data-ttu-id="b4238-192">Sidan **Rabatthanteringsgrupper** visas och visar en lista med artiklar som redan är medlemmar i den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-192">The **Rebate management groups** page appears and shows a list of items that are already members of the selected group.</span></span>
1. <span data-ttu-id="b4238-193">Välj om du vill lägga till ny en artikel i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b4238-193">To add a new item to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="b4238-194">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="b4238-194">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b4238-195">**Artikelkonto** – Välj artikelkonto-ID.</span><span class="sxs-lookup"><span data-stu-id="b4238-195">**Item account** – Select the item account ID.</span></span>
    - <span data-ttu-id="b4238-196">**Produktnamn** – Ange ett namn och/eller en beskrivning av artikeln.</span><span class="sxs-lookup"><span data-stu-id="b4238-196">**Product name** – Enter a name and/or description of the item.</span></span>

1. <span data-ttu-id="b4238-197">Om du vill ta bort en artikel från gruppen markerar du artikeln och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-197">To remove an item from the group, select the item, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="b4238-198">Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald artikel.</span><span class="sxs-lookup"><span data-stu-id="b4238-198">To view, add, or remove group assignments for a selected item, follow these steps.</span></span>

1. <span data-ttu-id="b4238-199">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="b4238-199">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="b4238-200">Välj den artikel du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="b4238-200">Select the item to work with.</span></span>
1. <span data-ttu-id="b4238-201">I åtgärdsfönstret på fliken **Produkt** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-201">On the Action Pane, on the **Product** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="b4238-202">Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda artikel redan tillhör.</span><span class="sxs-lookup"><span data-stu-id="b4238-202">The **Rebate management groups** page appears and shows a list of groups that the selected item already belongs to.</span></span>
1. <span data-ttu-id="b4238-203">Välj om du vill lägga till artikeln i en ny grupp, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="b4238-203">To add the item to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="b4238-204">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="b4238-204">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b4238-205">**Rabatthanteringsgrupp** – Välj den grupp som artikeln ska läggas till i.</span><span class="sxs-lookup"><span data-stu-id="b4238-205">**Rebate management group** – Select the group to add the item to.</span></span>
    - <span data-ttu-id="b4238-206">**Beskrivning** – Ange en beskrivning av gruppen (till exempel för att förklara varför artikeln är medlem i den).</span><span class="sxs-lookup"><span data-stu-id="b4238-206">**Description** – Enter a description of the group (for example, to explain why the item is a member of it).</span></span>

1. <span data-ttu-id="b4238-207">Om du vill ta bort en artikel från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-207">To remove an item from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="b4238-208">Följ de här stegen om du vill lägga till artiklar i en grupp baserat på kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="b4238-208">To add items to a group based on your category hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="b4238-209">Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Artikelgrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4238-209">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="b4238-210">Markera gruppen som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="b4238-210">Select the group to manage.</span></span>
1. <span data-ttu-id="b4238-211">Klicka på **Lägg till artiklar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-211">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="b4238-212">I dialogrutan **Lägg till artiklar** i fältet **Kategorihierarki**, välj en övre kategorihierarki.</span><span class="sxs-lookup"><span data-stu-id="b4238-212">In the **Add items** dialog box, in the **Category hierarchy** field, select a top-level category.</span></span>
1. <span data-ttu-id="b4238-213">Artikelhierarkin öppnas i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-213">The item hierarchy is opened in the left pane.</span></span> <span data-ttu-id="b4238-214">Välj den hierarkinivå du vill ha.</span><span class="sxs-lookup"><span data-stu-id="b4238-214">Select the hierarchy level that you're looking for.</span></span> 
1. <span data-ttu-id="b4238-215">Artiklar från den valda hierarkin och hierarkinivån visas nu i högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="b4238-215">Items from the selected hierarchy and hierarchy level are now listed in the right pane.</span></span> <span data-ttu-id="b4238-216">Följ dessa steg när du vill arbeta med fönstret:</span><span class="sxs-lookup"><span data-stu-id="b4238-216">Follow these steps to work with the pane:</span></span>

    - <span data-ttu-id="b4238-217">Markera kryssrutan för varje artikel som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="b4238-217">Select the check box for each item that you want to add.</span></span>
    - <span data-ttu-id="b4238-218">Markera kryssrutan i rutnätsrubriken om du vill markera alla artiklar som visas i listan.</span><span class="sxs-lookup"><span data-stu-id="b4238-218">Select the check box on the grid header to select all the items that are listed.</span></span>
    - <span data-ttu-id="b4238-219">Välj knappen **Visa markerad** för att filtrera rutnätet så att det bara visar de objekt du hittills har valt.</span><span class="sxs-lookup"><span data-stu-id="b4238-219">Select the **Show selected** button to filter the grid so that it shows only the items that you've selected so far.</span></span> <span data-ttu-id="b4238-220">Klicka på knappen igen om du vill återgå till den fullständiga listan.</span><span class="sxs-lookup"><span data-stu-id="b4238-220">Select the button again to return to the full list.</span></span>

1. <span data-ttu-id="b4238-221">Välj **OK** för att tillämpa artikelurvalet på den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="b4238-221">Select **OK** to apply your item selection to the selected group.</span></span>
