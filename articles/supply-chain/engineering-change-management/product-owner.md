---
title: Produktägare
description: Det här avsnittet innehåller information om produktägare. En produktägare är en grupp användare som är ansvariga för vissa produkter. Endast gruppens medlemmar kan frisläppa dessa produkter. Produktägaren kan också användas i arbetsflödet för godkännande.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4308020d66995d857e547be47216cb82caacf035
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438117"
---
# <a name="product-owners"></a><span data-ttu-id="12cf2-106">Produktägare</span><span class="sxs-lookup"><span data-stu-id="12cf2-106">Product owners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12cf2-107">En produktägare är en grupp användare som är ansvariga för vissa produkter.</span><span class="sxs-lookup"><span data-stu-id="12cf2-107">The product owner is a group of users who are responsible for specific products.</span></span> <span data-ttu-id="12cf2-108">När en produktägargrupp tilldelas en produkt kan bara medlemmarna i den gruppen frisläppa produkten.</span><span class="sxs-lookup"><span data-stu-id="12cf2-108">When a product owner group is assigned to a product, only the members of that group can release the product.</span></span> <span data-ttu-id="12cf2-109">Produktägaren kan också användas i arbetsflödet för godkännande i konstruktionsändringshantering.</span><span class="sxs-lookup"><span data-stu-id="12cf2-109">The product owner can also be used in the approval workflow in engineering change management.</span></span>

<span data-ttu-id="12cf2-110">Produktägare är globala inställningar.</span><span class="sxs-lookup"><span data-stu-id="12cf2-110">Product owners are global settings.</span></span> <span data-ttu-id="12cf2-111">De är därför tillgängliga för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="12cf2-111">Therefore, they are available to all legal entities.</span></span>

## <a name="create-a-product-owner-group"></a><span data-ttu-id="12cf2-112">Skapa en produktägargrupp</span><span class="sxs-lookup"><span data-stu-id="12cf2-112">Create a product owner group</span></span>

<span data-ttu-id="12cf2-113">Om du vill skapa en produktägargrupp och lägga till medlemmar i den följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="12cf2-113">To create a product owner group and add members to it, follow these steps.</span></span>

1. <span data-ttu-id="12cf2-114">Gå till **konstruktionsändringshantering \> inställningar \> produktägare**.</span><span class="sxs-lookup"><span data-stu-id="12cf2-114">Go to **Engineering change management \> Setup \> Product owners**.</span></span>
2. <span data-ttu-id="12cf2-115">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="12cf2-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="12cf2-116">I fältet **Produktägare** ange ett namn för grupp.</span><span class="sxs-lookup"><span data-stu-id="12cf2-116">In the **Product owner** field, enter a name for the group.</span></span>
4. <span data-ttu-id="12cf2-117">I fältet **Namn** ange en beskrivning för gruppen.</span><span class="sxs-lookup"><span data-stu-id="12cf2-117">In the **Name** field, enter a description of the group.</span></span>
5. <span data-ttu-id="12cf2-118">På snabbfliken **medlemmar** lägg till de arbetare som borde vara medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="12cf2-118">On the **Members** FastTab, add the workers who should be members of the group.</span></span>

## <a name="assign-a-product-owner-to-a-product"></a><span data-ttu-id="12cf2-119">Tilldela en produktägare till en produkt</span><span class="sxs-lookup"><span data-stu-id="12cf2-119">Assign a product owner to a product</span></span>

<span data-ttu-id="12cf2-120">Följ dessa steg för att tilldela en produktägare till en produkt.</span><span class="sxs-lookup"><span data-stu-id="12cf2-120">To assign a product owner to a product, follow these steps.</span></span>

1. <span data-ttu-id="12cf2-121">Öppna sidan **Produktinformation** för relevant produkt eller produktmall.</span><span class="sxs-lookup"><span data-stu-id="12cf2-121">Open the **Product details** page for the relevant product or product master.</span></span>
1. <span data-ttu-id="12cf2-122">På snabbfliken **Allmänt** ställer du in **Produktägare** till namnet på den relevanta produktägargruppen.</span><span class="sxs-lookup"><span data-stu-id="12cf2-122">On the **General** FastTab, set the **Product owner** field to the name of the relevant product owner group.</span></span>

<span data-ttu-id="12cf2-123">När en produktägare tilldelas till en produkt kan bara medlemmar i produktägargruppen inställningen **Produktägare**.</span><span class="sxs-lookup"><span data-stu-id="12cf2-123">While a product owner is assigned to a product, only the members of the product owner group can edit the **Product owner** setting.</span></span>

<span data-ttu-id="12cf2-124">Produktägaren är även synlig på sidan **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="12cf2-124">The product owner is also visible on the **Released products** page.</span></span>

## <a name="product-owners-and-product-releases"></a><span data-ttu-id="12cf2-125">Produktägare och produktlanseringar</span><span class="sxs-lookup"><span data-stu-id="12cf2-125">Product owners and product releases</span></span>

<span data-ttu-id="12cf2-126">Endast användare från en produkts produktägargrupp kan frisläppa produkten.</span><span class="sxs-lookup"><span data-stu-id="12cf2-126">Only users from a product's product owner group can release that product.</span></span> <span data-ttu-id="12cf2-127">Det finns dock ett undantag när produkten är en underordnad artikel och dess överordnade har släppts av den överordnade ägaren.</span><span class="sxs-lookup"><span data-stu-id="12cf2-127">However, there is an exception when the product is a child item, and its parent is released by the parent's owner.</span></span> <span data-ttu-id="12cf2-128">Detta innebär att om produkten ingår i strukturlistan i en annan produkt kontrolleras inte produktägaren för varje artikel i strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="12cf2-128">In other words, if the product is part of the BOM of another product, the system doesn't check the product owner of each item in the BOM.</span></span> <span data-ttu-id="12cf2-129">Endast produktägaren till den överordnade artikeln kontrolleras.</span><span class="sxs-lookup"><span data-stu-id="12cf2-129">It checks only the product owner of the parent item.</span></span>

<span data-ttu-id="12cf2-130">Produktens X tilldelas till exempel produktens ägargruppen *Designa skåp*.</span><span class="sxs-lookup"><span data-stu-id="12cf2-130">For example, product X is assigned to the *Design cabinets* product owner group.</span></span> <span data-ttu-id="12cf2-131">Produkt X ingår även i strukturlistan för produkt Y, som tilldelas produktägargruppen *Designa högtalare*.</span><span class="sxs-lookup"><span data-stu-id="12cf2-131">Product X is also part of the BOM of product Y, which is assigned to the *Design Speakers* product owner group.</span></span> <span data-ttu-id="12cf2-132">Om en användare från en produktägargrupp *Designa högtalare* frisläpper produkt Y och dess strukturlista, frisläpps produkt X tillsammans med produkt Y.</span><span class="sxs-lookup"><span data-stu-id="12cf2-132">If a user from the *Design Speakers* product owner group releases product Y and its BOM, product X will be released together with product Y.</span></span>

## <a name="product-owners-and-approvals"></a><span data-ttu-id="12cf2-133">Produktägare och godkännanden</span><span class="sxs-lookup"><span data-stu-id="12cf2-133">Product owners and approvals</span></span>

<span data-ttu-id="12cf2-134">Eftersom produktägaren vet om vissa tekniska förändringar kommer att gynna sina produkter, är det ofta klokt att ta med dem som en del av godkännande processen i konstruktionsändringshantering.</span><span class="sxs-lookup"><span data-stu-id="12cf2-134">Because product owners know whether specific engineering changes will benefit their products, it often makes sense to include them as part of the approval process in engineering change management.</span></span> <span data-ttu-id="12cf2-135">Du kan implementera den här metoden genom att ställa in produktägarna som deltagarleverantörer i de arbetsflöden som används för konstruktionsändringshantering.</span><span class="sxs-lookup"><span data-stu-id="12cf2-135">You can implement this approach by setting up the product owners as participant providers in the workflows that are used for engineering change management.</span></span> <span data-ttu-id="12cf2-136">Systemet tilldelar sedan godkännandeuppgifter i arbetsflödena, baserat på produkter som finns i konstruktionsändringshantering och teknisk ändringsorder.</span><span class="sxs-lookup"><span data-stu-id="12cf2-136">The system will then assign approval tasks in the workflows, based on the products that are in engineering change requests and engineering change orders.</span></span> <span data-ttu-id="12cf2-137">För mer information, se [Hantera ändringar av konstruktionsprodukter](engineering-change-management.md).</span><span class="sxs-lookup"><span data-stu-id="12cf2-137">For more information, see [Manage changes to engineering products](engineering-change-management.md).</span></span>
