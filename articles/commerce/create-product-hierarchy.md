---
title: Skapa en ny produkthierarki
description: I det här avsnittet beskrivs hur du skapar en ny produkthierarki i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 724ec2e5af7837d574298d662911cd9c6ee9e9f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415757"
---
# <a name="create-a-new-product-hierarchy"></a><span data-ttu-id="1f878-103">Skapa en ny produkthierarki</span><span class="sxs-lookup"><span data-stu-id="1f878-103">Create a new product hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="1f878-104">I det här avsnittet beskrivs hur du skapar en ny produkthierarki i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1f878-104">This topic describes how to create a new product hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1f878-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="1f878-105">Overview</span></span>

<span data-ttu-id="1f878-106">Dynamics 365 Commerce stöder flera butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="1f878-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="1f878-107">Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker).</span><span class="sxs-lookup"><span data-stu-id="1f878-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="1f878-108">Varje butikskanal kan ha egna betalningsmetoder, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal.</span><span class="sxs-lookup"><span data-stu-id="1f878-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="1f878-109">Du måste ställa in alla dessa element innan du kan skapa en butikskanel.</span><span class="sxs-lookup"><span data-stu-id="1f878-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="1f878-110">En produkthierarki för Handel används för att definiera den allmänna produkthierarkin för din organisation.</span><span class="sxs-lookup"><span data-stu-id="1f878-110">A Commerce product hierarchy is used to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="1f878-111">Du kan använda en produkthierarki för Handel för marknadsföring, prissättning och kampanjer, rapportering och sortimentplanering.</span><span class="sxs-lookup"><span data-stu-id="1f878-111">You can use a Commerce product hierarchy for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="1f878-112">Endast en produkthierarki för Handel tilldelas per organisation.</span><span class="sxs-lookup"><span data-stu-id="1f878-112">Only one Commerce product hierarchy can be assigned per organization.</span></span>

## <a name="create-and-configure-a-product-hierarchy"></a><span data-ttu-id="1f878-113">Skapa och konfigurera en produkthierarki</span><span class="sxs-lookup"><span data-stu-id="1f878-113">Create and configure a product hierarchy</span></span>

<span data-ttu-id="1f878-114">Följ stegen nedan om du vill skapa och konfigurera en produkthierarki för Handel.</span><span class="sxs-lookup"><span data-stu-id="1f878-114">To create and configure a Commerce product hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="1f878-115">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> produkthierarki för Handel**.</span><span class="sxs-lookup"><span data-stu-id="1f878-115">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
1. <span data-ttu-id="1f878-116">Om det inte finns någon hierarki ännu, i **åtgärdsfönstret**, välj **ny** för att skapa roten för hierarkin.</span><span class="sxs-lookup"><span data-stu-id="1f878-116">If no hierachy exists yet, on the **Action pane**, select **New** to create the root of the hierarchy.</span></span>
1. <span data-ttu-id="1f878-117">Under **allmänt**:</span><span class="sxs-lookup"><span data-stu-id="1f878-117">Under **General**:</span></span>
    1. <span data-ttu-id="1f878-118">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="1f878-118">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="1f878-119">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="1f878-119">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="1f878-120">I rutan **Eget namn** anger du ett eget namn.</span><span class="sxs-lookup"><span data-stu-id="1f878-120">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="1f878-121">Ange **Aktiv** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="1f878-121">Set **Active** to **Yes**.</span></span>

## <a name="add-hierarchy-nodes"></a><span data-ttu-id="1f878-122">Lägg till hierarkinoder</span><span class="sxs-lookup"><span data-stu-id="1f878-122">Add hierarchy nodes</span></span>

<span data-ttu-id="1f878-123">Gör så här för att lägga till hierarkinoder.</span><span class="sxs-lookup"><span data-stu-id="1f878-123">To add hierarchy nodes, follow these steps.</span></span>

1. <span data-ttu-id="1f878-124">I åtgärdsfönstret klickar du på **Redigera kategorihierarki**.</span><span class="sxs-lookup"><span data-stu-id="1f878-124">On the action pane, select **Edit category hierarchy**.</span></span>
1. <span data-ttu-id="1f878-125">Markera den överordnade nod som du vill lägga till en ny nod i och välj sedan **Ny kategorinod**.</span><span class="sxs-lookup"><span data-stu-id="1f878-125">Select the parent node you want to add a new node to, and then select **New category node**.</span></span>
1. <span data-ttu-id="1f878-126">I avsnittet **allmänt** finns **namn**, **beskrivning**, **eget namn** och **nyckelord**.</span><span class="sxs-lookup"><span data-stu-id="1f878-126">In the **General** section provide a **Name**, **Description**, **Friendly name** and **Keywords**.</span></span>
1. <span data-ttu-id="1f878-127">Under **allmänt**:</span><span class="sxs-lookup"><span data-stu-id="1f878-127">Under **General**:</span></span>
    1. <span data-ttu-id="1f878-128">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="1f878-128">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="1f878-129">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="1f878-129">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="1f878-130">I rutan **Eget namn** anger du ett eget namn.</span><span class="sxs-lookup"><span data-stu-id="1f878-130">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="1f878-131">I rutan **nyckelord**, ange relevanta nyckelord.</span><span class="sxs-lookup"><span data-stu-id="1f878-131">In the **Keywords** box, enter relevant keywords.</span></span>
    1. <span data-ttu-id="1f878-132">I rutan **Visningsordning**, ange ett nummer för visningsordningen (valfritt).</span><span class="sxs-lookup"><span data-stu-id="1f878-132">In the **Display order** box, enter a number for the display order (optional).</span></span>
1. <span data-ttu-id="1f878-133">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1f878-133">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="1f878-134">Upprepa stegen ovan om du vill lägga till fler noder.</span><span class="sxs-lookup"><span data-stu-id="1f878-134">Repeat the steps above to add additional nodes.</span></span>

<span data-ttu-id="1f878-135">Följande bild visar skapandet av en ny produkthierarkinod.</span><span class="sxs-lookup"><span data-stu-id="1f878-135">The following image shows the creation of a new product hierarchy node.</span></span>

![Skapa en produkthierarki](media/create-product-hierarchy.png)

## <a name="other-settings"></a><span data-ttu-id="1f878-137">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="1f878-137">Other settings</span></span>

<span data-ttu-id="1f878-138">Grupper av kategoriattribut kan också tilldelas till varje grupp efter behov.</span><span class="sxs-lookup"><span data-stu-id="1f878-138">Category attribute groups can also be assigned to each group as required.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="1f878-139">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1f878-139">Additional resources</span></span>

[<span data-ttu-id="1f878-140">Commerce-hierarkier</span><span class="sxs-lookup"><span data-stu-id="1f878-140">commerce hierarchies</span></span>](retail-hierarchies.md)

[<span data-ttu-id="1f878-141">Hantera produktkategorier och produkter</span><span class="sxs-lookup"><span data-stu-id="1f878-141">Manage product categories and products </span></span>](category-management-product-creation.md)

[<span data-ttu-id="1f878-142">Ändra sorteringsordning för marknadsföringsentiteter</span><span class="sxs-lookup"><span data-stu-id="1f878-142">Change the sort order for merchandizing entities</span></span>](custom-order-categories-nav-retail-prod-hierarchy.md)
