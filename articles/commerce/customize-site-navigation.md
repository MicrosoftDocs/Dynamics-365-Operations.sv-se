---
title: Anpassa webbplatsnavigeringen
description: I det här avsnittet beskrivs hur du skapar en anpassad onlinemapp för navigering för att ordna dina produkter för bläddring på din Microsoft Dynamics 365 Commerce-webbplats.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 642cb5c145dec68631eb9ab27d926ba8ab75c59b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914920"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="e22b8-103">Anpassa webbplatsnavigeringen</span><span class="sxs-lookup"><span data-stu-id="e22b8-103">Customize site navigation</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e22b8-104">I det här avsnittet beskrivs hur du skapar en anpassad onlinemapp för navigering för att ordna dina produkter för bläddring på din Microsoft Dynamics 365 Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="e22b8-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="e22b8-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="e22b8-105">Overview</span></span>

<span data-ttu-id="e22b8-106">Nätbutiker gör vanligtvis att kunderna hittar och bläddrar igenom produkter genom att navigera genom produktkategorier.</span><span class="sxs-lookup"><span data-stu-id="e22b8-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="e22b8-107">Den här funktionen tillhandahålls vanligtvis med flikar högst upp på sidan eller genom ett navigeringsfält till vänster.</span><span class="sxs-lookup"><span data-stu-id="e22b8-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="e22b8-108">I Dynamics 365 Commerce kan du skapa och hantera den hierarkiska strukturen för kategorinavigeringen och de produkter som ingår i de olika kategorierna.</span><span class="sxs-lookup"><span data-stu-id="e22b8-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-retail-channel-navigation-hierarchy"></a><span data-ttu-id="e22b8-109">Skapa en navigeringshierarki för butikskanal</span><span class="sxs-lookup"><span data-stu-id="e22b8-109">Create a retail channel navigation hierarchy</span></span>

<span data-ttu-id="e22b8-110">Följ stegen nedan om du vill skapa en navigeringshierarki för butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="e22b8-110">To create a retail channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="e22b8-111">Gå till **Butik \> Produkter och kategorier \> Kategori- och produkthantering**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-111">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="e22b8-112">Markera **kategorihierarkier** och välj sedan **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="e22b8-113">Namn på hierarkin.</span><span class="sxs-lookup"><span data-stu-id="e22b8-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e22b8-114">Den översta kategorin som du skapar är rotkategorinoden.</span><span class="sxs-lookup"><span data-stu-id="e22b8-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="e22b8-115">Den visas inte på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="e22b8-115">It won't be shown on your site.</span></span> <span data-ttu-id="e22b8-116">Om du vill skapa en kategorihierarki där en enskild nod på den översta nivån visas på din webbplats, skapar du och namnger kategorin som underordnad till rotkategorin.</span><span class="sxs-lookup"><span data-stu-id="e22b8-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="e22b8-117">Välj **ny kategorinod** och ge kategorin ett namn.</span><span class="sxs-lookup"><span data-stu-id="e22b8-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="e22b8-118">Fortsätt att skapa kategorier på samma nivå och underordnade kategorier som du behöver.</span><span class="sxs-lookup"><span data-stu-id="e22b8-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="e22b8-119">Nu kan du tilldela produkter till varje kategori som du har skapat under kategorin på den högsta nivån.</span><span class="sxs-lookup"><span data-stu-id="e22b8-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="e22b8-120">Anpassa ordningen på kategorier</span><span class="sxs-lookup"><span data-stu-id="e22b8-120">Customize the order of categories</span></span>

<span data-ttu-id="e22b8-121">De kategorier som du definierar visas som standard i alfabetisk ordning på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e22b8-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="e22b8-122">Du kan dock även anpassa visningsordningen för kategorier.</span><span class="sxs-lookup"><span data-stu-id="e22b8-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="e22b8-123">Tilldela en kategorihierarkityp</span><span class="sxs-lookup"><span data-stu-id="e22b8-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="e22b8-124">Gå till **Butik \> Produkter och kategorier \> Kategori- och produkthantering**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-124">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="e22b8-125">Välj **kategorihierarkier**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="e22b8-126">I åtgärdsfönstret, på fliken **kategorihierarki** i gruppen **Inställning** markerar du **Associera hierarki**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="e22b8-127">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-127">Select **New**.</span></span>
1. <span data-ttu-id="e22b8-128">I fältet **Kategorihierarkityp**, välj **Navigeringshierarki för butikskanal**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-128">In the **Category hierarchy type** field, select **Retail channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="e22b8-129">I fältet **kategorihierarki** väljer du den hierarki för kanalnavigering som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="e22b8-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="e22b8-130">Publicera nya eller uppdaterade navigeringsnoder</span><span class="sxs-lookup"><span data-stu-id="e22b8-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="e22b8-131">Gör så här om du vill att din navigeringsnoden ska vara tillgänglig för din nätbutik:</span><span class="sxs-lookup"><span data-stu-id="e22b8-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="e22b8-132">Gå till **Butik \> Kanalinställningar \> Kanalkategorier och produktattribut**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-132">Go to **Retail \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="e22b8-133">I trädet till vänster väljer du onlinebutiken.</span><span class="sxs-lookup"><span data-stu-id="e22b8-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="e22b8-134">Välj **Publicera kanaluppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="e22b8-135">Gå till **Butik \> Butik-IT \> Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-135">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="e22b8-136">I listan söker du och väljer **Jobb 1040**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="e22b8-137">Välj **kör nu**.</span><span class="sxs-lookup"><span data-stu-id="e22b8-137">Select **Run now**.</span></span>
1. <span data-ttu-id="e22b8-138">Upprepa steg 5 och 6 för jobben 1070 och 1150.</span><span class="sxs-lookup"><span data-stu-id="e22b8-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="e22b8-139">Visa kategorier på din webbplats</span><span class="sxs-lookup"><span data-stu-id="e22b8-139">Show categories on your site</span></span>

<span data-ttu-id="e22b8-140">Om du vill visa kategorihierarkin i din nätbutik måste du lägga till modulen för navigeringsmenyn på lämplig plats i en mall eller i ett fragment.</span><span class="sxs-lookup"><span data-stu-id="e22b8-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="e22b8-141">Modulen navigeringsmeny visar sedan webbhierarkin, förutsatt att du har publicerat din butikshierarki på den kanal som webbplatsen är bunden till.</span><span class="sxs-lookup"><span data-stu-id="e22b8-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your retail navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="e22b8-142">Med modulen navigeringsmeny som ingår i butikens startpaket kan användarna bara navigera till kategorier som inte har underkategorier.</span><span class="sxs-lookup"><span data-stu-id="e22b8-142">The navigation menu module that is included in the store starter kit lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="e22b8-143">Om dina kunder ska kunna navigera till kategorier som har underkategorier måste du anpassa modulen för navigeringsmenyn.</span><span class="sxs-lookup"><span data-stu-id="e22b8-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="e22b8-144">Lägga till anpassade navigeringsalternativ</span><span class="sxs-lookup"><span data-stu-id="e22b8-144">Add custom navigation options</span></span>

<span data-ttu-id="e22b8-145">På navigeringsmenyn kan du lägga till navigeringsalternativ som inte ingår i din produktkategorihierarki.</span><span class="sxs-lookup"><span data-stu-id="e22b8-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="e22b8-146">I slutet av listan med produktkategorier kan du till exempel lägga till artikeln **kontakta oss** som pekar på en kontaktsida som du har skapat för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e22b8-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="e22b8-147">Om du vill lägga till anpassade navigeringsalternativ på navigeringsmenyn följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e22b8-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="e22b8-148">I mallen eller fragmentet som du vill anpassa väljer du modulen navigeringsmeny.</span><span class="sxs-lookup"><span data-stu-id="e22b8-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="e22b8-149">I fönstret egenskaper, på fliken **Data** väljer du **Lägg till objekt** för att skapa ett nytt navigeringsobjekt i innehållshanteringssystem (CMS).</span><span class="sxs-lookup"><span data-stu-id="e22b8-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="e22b8-150">Ange länktext och en URL.</span><span class="sxs-lookup"><span data-stu-id="e22b8-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="e22b8-151">Upprepa steg 2 och 3 om du vill lägga till fler anpassade navigeringsalternativ.</span><span class="sxs-lookup"><span data-stu-id="e22b8-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="e22b8-152">När du är klar sparar du mallen eller fragmentmallen och checkar in den.</span><span class="sxs-lookup"><span data-stu-id="e22b8-152">When you've finished, save the template or fragment, and check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e22b8-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e22b8-153">Additional resources</span></span>

[<span data-ttu-id="e22b8-154">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="e22b8-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="e22b8-155">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="e22b8-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="e22b8-156">Arbeta med förinställda layouter</span><span class="sxs-lookup"><span data-stu-id="e22b8-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="e22b8-157">Arbeta med fragment</span><span class="sxs-lookup"><span data-stu-id="e22b8-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="e22b8-158">Arbeta med moduler</span><span class="sxs-lookup"><span data-stu-id="e22b8-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="e22b8-159">Skapa URL för webbsida</span><span class="sxs-lookup"><span data-stu-id="e22b8-159">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="e22b8-160">Arbeta med publiceringsgrupper</span><span class="sxs-lookup"><span data-stu-id="e22b8-160">Work with publish groups</span></span>](publish-groups.md)
