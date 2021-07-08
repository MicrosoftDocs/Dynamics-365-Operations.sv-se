---
title: Rabatthanteringsgrupper
description: I det här avsnittet beskrivs hur du ställer in Rabatthanteringsgrupper. Rabatthanteringsgrupper kan användas under rabattberäkningar och kan kopplas till en huvudpost.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee5a195b3d2881ff70fb1f0d4063ed681e874648
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271087"
---
# <a name="rebate-management-groups"></a><span data-ttu-id="358b3-104">Rabatthanteringsgrupper</span><span class="sxs-lookup"><span data-stu-id="358b3-104">Rebate management groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="358b3-105">Rabatthanteringsberäkningar kan baseras på grupper.</span><span class="sxs-lookup"><span data-stu-id="358b3-105">Rebate management calculations can be driven by groups.</span></span> <span data-ttu-id="358b3-106">Rabatthanteringsgrupper kan skapas för kunder, leverantörer och artiklar.</span><span class="sxs-lookup"><span data-stu-id="358b3-106">Rebate management groups can be created for customers, vendors, and items.</span></span> <span data-ttu-id="358b3-107">De kan kopplas till en huvudpost.</span><span class="sxs-lookup"><span data-stu-id="358b3-107">They can be attached to a master record.</span></span>

## <a name="rebate-management-customer-groups"></a><span data-ttu-id="358b3-108">Rabatthanteringsgrupper för kunder</span><span class="sxs-lookup"><span data-stu-id="358b3-108">Rebate management customer groups</span></span>

<span data-ttu-id="358b3-109">Beräkningen för en grupp av kunder skapas ofta för en företagskedja, till exempel en kedja eller ett franchiseföretag.</span><span class="sxs-lookup"><span data-stu-id="358b3-109">The calculation for a group of customers is often created for a chain of companies, such as a supermarket chain or a franchise company.</span></span> <span data-ttu-id="358b3-110">Den här typen av beräkning hör vanligtvis till en rabatt.</span><span class="sxs-lookup"><span data-stu-id="358b3-110">This type of calculation is usually related to a rebate.</span></span>

<span data-ttu-id="358b3-111">Ett avdrag beräknas ofta utan hänsyn till vem den godkända ordern såldes till.</span><span class="sxs-lookup"><span data-stu-id="358b3-111">A deduction is often calculated without considering who the qualifying order was sold to.</span></span> <span data-ttu-id="358b3-112">Det finns dock några undantag.</span><span class="sxs-lookup"><span data-stu-id="358b3-112">However, there are exceptions.</span></span> <span data-ttu-id="358b3-113">En licenstagare kan exempelvis skapa ett avdragsschema där kundgrupp A får 4 procent, men kundgrupp B får bara tre procent.</span><span class="sxs-lookup"><span data-stu-id="358b3-113">For example, a licensee might create a deduction scheme where customer group A will receive 4 percent, but customer group B will receive only 3 percent.</span></span>

### <a name="set-up-customer-groups"></a><span data-ttu-id="358b3-114">Ställ in kundgrupper</span><span class="sxs-lookup"><span data-stu-id="358b3-114">Set up customer groups</span></span>

<span data-ttu-id="358b3-115">Om du vill arbeta med kundgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Kundgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-115">To work with Rebate management customer groups, go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span> <span data-ttu-id="358b3-116">Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov.</span><span class="sxs-lookup"><span data-stu-id="358b3-116">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="358b3-117">För varje grupp anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="358b3-117">For each group, set the following fields:</span></span>

- <span data-ttu-id="358b3-118">**Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-118">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="358b3-119">**Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.</span><span class="sxs-lookup"><span data-stu-id="358b3-119">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-customer-group-assignments"></a><span data-ttu-id="358b3-120">Hantera kundgruppstilldelningar</span><span class="sxs-lookup"><span data-stu-id="358b3-120">Manage customer group assignments</span></span>

<span data-ttu-id="358b3-121">Varje kund kan tillhöra ett val annat antal rabatthanteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="358b3-121">Each customer can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="358b3-122">Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller kundlistan.</span><span class="sxs-lookup"><span data-stu-id="358b3-122">To view and assign group members, you can start from either the group list or the customer list.</span></span>

<span data-ttu-id="358b3-123">Följ de här stegen om du vill visa, lägga till eller ta bort kunder för den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-123">To view, add, or remove customers for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="358b3-124">Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Kundgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-124">Go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span>
1. <span data-ttu-id="358b3-125">Markera gruppen som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="358b3-125">Select the group to manage.</span></span>
1. <span data-ttu-id="358b3-126">I åtgärdsfönstret, välj **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="358b3-126">On the Action Pane, select **Customers**.</span></span> <span data-ttu-id="358b3-127">Sidan **Rabatthanteringsgrupper** visas och visar en lista med kunder som redan är medlemmar i den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-127">The **Rebate management groups** page appears and shows a list of customers that are already members of the selected group.</span></span>
1. <span data-ttu-id="358b3-128">Välj om du vill lägga till en ny kund i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="358b3-128">To add a new customer to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="358b3-129">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="358b3-129">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="358b3-130">**Kundkonto** – Välj kundkonto-ID.</span><span class="sxs-lookup"><span data-stu-id="358b3-130">**Customer account** – Select the customer account ID.</span></span>

1. <span data-ttu-id="358b3-131">Om du vill ta bort en kund från gruppen markerar du kunden och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-131">To remove a customer from the group, select the customer, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="358b3-132">Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald kund.</span><span class="sxs-lookup"><span data-stu-id="358b3-132">To view, add, or remove group assignments for a selected customer, follow these steps.</span></span>

1. <span data-ttu-id="358b3-133">Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="358b3-133">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="358b3-134">Välj den kund du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="358b3-134">Select the customer to work with.</span></span>
1. <span data-ttu-id="358b3-135">I åtgärdsfönstret på fliken **Kund** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-135">On the Action Pane, on the **Customer** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="358b3-136">Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda kunden redan tillhör.</span><span class="sxs-lookup"><span data-stu-id="358b3-136">The **Rebate management groups** page appears and shows a list of groups that the selected customer already belongs to.</span></span>
1. <span data-ttu-id="358b3-137">Välj om du vill lägga till en ny kund i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="358b3-137">To add the customer to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="358b3-138">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="358b3-138">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="358b3-139">**Rabatthanteringsgrupp** – Välj den grupp som kunden ska läggas till i.</span><span class="sxs-lookup"><span data-stu-id="358b3-139">**Rebate management group** – Select the group to add the customer to.</span></span>

1. <span data-ttu-id="358b3-140">Om du vill ta bort en kund från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-140">To remove a customer from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="rebate-management-vendor-groups"></a><span data-ttu-id="358b3-141">Rabatthantering för leverantörsgrupper</span><span class="sxs-lookup"><span data-stu-id="358b3-141">Rebate management vendor groups</span></span>

<span data-ttu-id="358b3-142">Beräkningen för en grupp av leverantörer skapas ofta för en grupp med leveranspunkter.</span><span class="sxs-lookup"><span data-stu-id="358b3-142">The calculation for a group of vendors is often created for a group of delivery points.</span></span> <span data-ttu-id="358b3-143">Den här typen av beräkning hör vanligtvis till en rabatt.</span><span class="sxs-lookup"><span data-stu-id="358b3-143">This type of calculation is usually related to a rebate.</span></span>

### <a name="set-up-vendor-groups"></a><span data-ttu-id="358b3-144">Ställ in leverantörsgrupper</span><span class="sxs-lookup"><span data-stu-id="358b3-144">Set up vendor groups</span></span>

<span data-ttu-id="358b3-145">Om du vill arbeta med leverantörsgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Leverantörsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-145">To work with Rebate management vendor groups, go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span> <span data-ttu-id="358b3-146">Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov.</span><span class="sxs-lookup"><span data-stu-id="358b3-146">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="358b3-147">För varje grupp anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="358b3-147">For each group, set the following fields:</span></span>

- <span data-ttu-id="358b3-148">**Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-148">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="358b3-149">**Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.</span><span class="sxs-lookup"><span data-stu-id="358b3-149">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-vendor-group-assignments"></a><span data-ttu-id="358b3-150">Hantera leverantörsgruppstilldelningar</span><span class="sxs-lookup"><span data-stu-id="358b3-150">Manage vendor group assignments</span></span>

<span data-ttu-id="358b3-151">Varje leverantör kan tillhöra ett val annat antal rabatthanteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="358b3-151">Each vendor can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="358b3-152">Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller leverantörlistan.</span><span class="sxs-lookup"><span data-stu-id="358b3-152">To view and assign group members, you can start from either the group list or the vendor list.</span></span>

<span data-ttu-id="358b3-153">Följ de här stegen om du vill visa, lägga till eller ta bort leverantör för den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-153">To view, add, or remove vendors for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="358b3-154">Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Leverantörsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-154">Go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span>
1. <span data-ttu-id="358b3-155">Markera gruppen som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="358b3-155">Select the group to manage.</span></span>
1. <span data-ttu-id="358b3-156">Klicka på **Leverantörer** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-156">On the Action Pane, select **Vendors**.</span></span> <span data-ttu-id="358b3-157">Sidan **Rabatthanteringsgrupper** visas och visar en lista med leverantör som redan är medlemmar i den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-157">The **Rebate management groups** page appears and shows a list of vendors that are already members of the selected group.</span></span>
1. <span data-ttu-id="358b3-158">Välj om du vill lägga till en ny leverantör i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="358b3-158">To add a new vendor to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="358b3-159">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="358b3-159">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="358b3-160">**Leverantörskonto** – Välj leverantörskonto-ID.</span><span class="sxs-lookup"><span data-stu-id="358b3-160">**Vendor account** – Select the vendor account ID.</span></span>

1. <span data-ttu-id="358b3-161">Om du vill ta bort en leverantör från gruppen markerar du leverantören och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-161">To remove a vendor from the group, select the vendor, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="358b3-162">Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald leverantör.</span><span class="sxs-lookup"><span data-stu-id="358b3-162">To view, add, or remove group assignments for a selected vendor, follow these steps.</span></span>

1. <span data-ttu-id="358b3-163">Gå till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="358b3-163">Go to **Accounts payable \> Vendors \> All vendors**.</span></span>
1. <span data-ttu-id="358b3-164">Välj den leverantör du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="358b3-164">Select the vendor to work with.</span></span>
1. <span data-ttu-id="358b3-165">I åtgärdsfönstret på fliken **Leverantör** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-165">On the Action Pane, on the **Vendor** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="358b3-166">Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda leverantör redan tillhör.</span><span class="sxs-lookup"><span data-stu-id="358b3-166">The **Rebate management groups** page appears and shows a list of groups that the selected vendor already belongs to.</span></span>
1. <span data-ttu-id="358b3-167">Välj om du vill lägga till en leverantör i en ny grupp, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="358b3-167">To add the vendor to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="358b3-168">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="358b3-168">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="358b3-169">**Rabatthanteringsgrupp** – Välj den grupp som leverantören ska läggas till i.</span><span class="sxs-lookup"><span data-stu-id="358b3-169">**Rebate management group** – Select the group to add the vendor to.</span></span>

1. <span data-ttu-id="358b3-170">Om du vill ta bort en leverantör från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-170">To remove a vendor from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="item-rebate-groups"></a><span data-ttu-id="358b3-171">Artikelrabattgrupper</span><span class="sxs-lookup"><span data-stu-id="358b3-171">Item rebate groups</span></span>

<span data-ttu-id="358b3-172">Genom att gruppera artiklar blir du mer flexibel när rabatter och avdrag beräknas.</span><span class="sxs-lookup"><span data-stu-id="358b3-172">By grouping items, you have more flexibility when rebates and deductions are calculated.</span></span> <span data-ttu-id="358b3-173">Det här arbetssättet är ofta ett effektivare sätt att ställa in rabatter och avdrag för kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="358b3-173">This approach is often a more efficient way to set up rebates and deductions for customers and vendors.</span></span>

### <a name="set-up-item-groups"></a><span data-ttu-id="358b3-174">Ställ in artikelgrupper</span><span class="sxs-lookup"><span data-stu-id="358b3-174">Set up item groups</span></span>

<span data-ttu-id="358b3-175">Om du vill arbeta med artikelgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Atikelgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-175">To work with Rebate management item groups, go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span> <span data-ttu-id="358b3-176">Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov.</span><span class="sxs-lookup"><span data-stu-id="358b3-176">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="358b3-177">För varje grupp anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="358b3-177">For each group, set the following fields:</span></span>

- <span data-ttu-id="358b3-178">**Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-178">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="358b3-179">**Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.</span><span class="sxs-lookup"><span data-stu-id="358b3-179">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-item-group-assignments"></a><span data-ttu-id="358b3-180">Hantera artikelgruppstilldelningar</span><span class="sxs-lookup"><span data-stu-id="358b3-180">Manage item group assignments</span></span>

<span data-ttu-id="358b3-181">Varje artikel kan tillhöra ett val annat antal rabatthanteringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="358b3-181">Each item can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="358b3-182">Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller artikellistan.</span><span class="sxs-lookup"><span data-stu-id="358b3-182">To view and assign group members, you can start from either the group list or the item list.</span></span> <span data-ttu-id="358b3-183">Du kan också lägga till artiklar utifrån kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="358b3-183">You can also add items based on your category hierarchy.</span></span>

<span data-ttu-id="358b3-184">Följ de här stegen om du vill visa, lägga till eller ta bort artiklar för den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-184">To view, add, or remove items for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="358b3-185">Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Artikelgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-185">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="358b3-186">Markera gruppen som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="358b3-186">Select the group to manage.</span></span>
1. <span data-ttu-id="358b3-187">Klicka på **Artiklar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-187">On the Action Pane, select **Items**.</span></span> <span data-ttu-id="358b3-188">Sidan **Rabatthanteringsgrupper** visas och visar en lista med artiklar som redan är medlemmar i den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-188">The **Rebate management groups** page appears and shows a list of items that are already members of the selected group.</span></span>
1. <span data-ttu-id="358b3-189">Välj om du vill lägga till ny en artikel i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="358b3-189">To add a new item to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="358b3-190">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="358b3-190">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="358b3-191">**Artikelkonto** – Välj artikelkonto-ID.</span><span class="sxs-lookup"><span data-stu-id="358b3-191">**Item account** – Select the item account ID.</span></span>

1. <span data-ttu-id="358b3-192">Om du vill ta bort en artikel från gruppen markerar du artikeln och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-192">To remove an item from the group, select the item, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="358b3-193">Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald artikel.</span><span class="sxs-lookup"><span data-stu-id="358b3-193">To view, add, or remove group assignments for a selected item, follow these steps.</span></span>

1. <span data-ttu-id="358b3-194">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="358b3-194">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="358b3-195">Välj den artikel du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="358b3-195">Select the item to work with.</span></span>
1. <span data-ttu-id="358b3-196">I åtgärdsfönstret på fliken **Produkt** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-196">On the Action Pane, on the **Product** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="358b3-197">Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda artikel redan tillhör.</span><span class="sxs-lookup"><span data-stu-id="358b3-197">The **Rebate management groups** page appears and shows a list of groups that the selected item already belongs to.</span></span>
1. <span data-ttu-id="358b3-198">Välj om du vill lägga till artikeln i en ny grupp, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="358b3-198">To add the item to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="358b3-199">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="358b3-199">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="358b3-200">**Rabatthanteringsgrupp** – Välj den grupp som artikeln ska läggas till i.</span><span class="sxs-lookup"><span data-stu-id="358b3-200">**Rebate management group** – Select the group to add the item to.</span></span>

1. <span data-ttu-id="358b3-201">Om du vill ta bort en artikel från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-201">To remove an item from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="358b3-202">Följ de här stegen om du vill lägga till artiklar i en grupp baserat på kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="358b3-202">To add items to a group based on your category hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="358b3-203">Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Artikelgrupper**.</span><span class="sxs-lookup"><span data-stu-id="358b3-203">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="358b3-204">Markera gruppen som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="358b3-204">Select the group to manage.</span></span>
1. <span data-ttu-id="358b3-205">Klicka på **Lägg till artiklar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-205">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="358b3-206">I dialogrutan **Lägg till artiklar** i fältet **Kategorihierarki**, välj en övre kategorihierarki.</span><span class="sxs-lookup"><span data-stu-id="358b3-206">In the **Add items** dialog box, in the **Category hierarchy** field, select a top-level category.</span></span>
1. <span data-ttu-id="358b3-207">Artikelhierarkin öppnas i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-207">The item hierarchy is opened in the left pane.</span></span> <span data-ttu-id="358b3-208">Välj den hierarkinivå du vill ha.</span><span class="sxs-lookup"><span data-stu-id="358b3-208">Select the hierarchy level that you're looking for.</span></span> 
1. <span data-ttu-id="358b3-209">Artiklar från den valda hierarkin och hierarkinivån visas nu i högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="358b3-209">Items from the selected hierarchy and hierarchy level are now listed in the right pane.</span></span> <span data-ttu-id="358b3-210">Följ dessa steg när du vill arbeta med fönstret:</span><span class="sxs-lookup"><span data-stu-id="358b3-210">Follow these steps to work with the pane:</span></span>

    - <span data-ttu-id="358b3-211">Markera kryssrutan för varje artikel som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="358b3-211">Select the check box for each item that you want to add.</span></span>
    - <span data-ttu-id="358b3-212">Markera kryssrutan i rutnätsrubriken om du vill markera alla artiklar som visas i listan.</span><span class="sxs-lookup"><span data-stu-id="358b3-212">Select the check box on the grid header to select all the items that are listed.</span></span>
    - <span data-ttu-id="358b3-213">Välj knappen **Visa markerad** för att filtrera rutnätet så att det bara visar de objekt du hittills har valt.</span><span class="sxs-lookup"><span data-stu-id="358b3-213">Select the **Show selected** button to filter the grid so that it shows only the items that you've selected so far.</span></span> <span data-ttu-id="358b3-214">Klicka på knappen igen om du vill återgå till den fullständiga listan.</span><span class="sxs-lookup"><span data-stu-id="358b3-214">Select the button again to return to the full list.</span></span>

1. <span data-ttu-id="358b3-215">Välj **OK** för att tillämpa artikelurvalet på den valda gruppen.</span><span class="sxs-lookup"><span data-stu-id="358b3-215">Select **OK** to apply your item selection to the selected group.</span></span>
