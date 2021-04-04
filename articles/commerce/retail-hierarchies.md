---
title: Commerce-hierarkier
description: Den här artikeln beskrivs hierarkier i Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager, EcoResCategoryHierarchyFactbox
audience: Application User
ms.reviewer: josaw
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a2cc766b0fd358d82187a5c0368005896fbb7769
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251387"
---
# <a name="commerce-hierarchies"></a><span data-ttu-id="bd9a3-103">Commerce-hierarkier</span><span class="sxs-lookup"><span data-stu-id="bd9a3-103">Commerce hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bd9a3-104">Den här artikeln beskrivs hierarkier i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-104">This article describes hierarchies in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="bd9a3-105">Du kan skapa en kategorihierarki för att strukturera de produkter som du säljer via kanaler.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-105">You can create a category hierarchy to organize the products that you sell through your channels.</span></span> <span data-ttu-id="bd9a3-106">Du kan använda produkthierarkier för att kategorisera eller gruppera produkter.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-106">You can use product hierarchies to categorize or group products.</span></span> <span data-ttu-id="bd9a3-107">Du kan sedan använda dessa produkter om du vill skapa produktsortiment och kundbonusprogram.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-107">You can then use these products to create product assortments and customer loyalty programs.</span></span> <span data-ttu-id="bd9a3-108">Du kan också tilldela produktattribut och egenskaper, tilldela en prissättningstruktur, inkludera produkter i produkterbjudanden och använda produkterna för rapportering.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-108">You can also assign product attributes and properties, assign a pricing structure, include the products in product promotions, and use the products for reporting.</span></span> <span data-ttu-id="bd9a3-109">Du kan skapa en kategorihierarki som representerar alla produkter och kategorier i organisationen och använder sedan kategorihierarkin för flera syften.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-109">You can create one category hierarchy to represent all the products and categories in your organization, and then use that category hierarchy for multiple purposes.</span></span> <span data-ttu-id="bd9a3-110">Du kan också skapa flera kategorihierarkier för särskilda syften, till exempel produkterbjudanden.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-110">Alternatively, you can create multiple category hierarchies for special purposes, such as product promotions.</span></span> <span data-ttu-id="bd9a3-111">När du skapar en Produkthierarki, måste du tilldela en kategorihierarkityp för att identifiera syftet med kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-111">When you create a product hierarchy, you must assign a category hierarchy type to identify the purpose of the category hierarchy.</span></span> <span data-ttu-id="bd9a3-112">Om du till exempel om endast produkthierarkier som tilldelas typen **Handelsnavigeringshierarki** är refererade när du bläddrar i produkter efter kategori online eller på betalningsplatsen (POS).</span><span class="sxs-lookup"><span data-stu-id="bd9a3-112">For example, only product hierarchies that are assigned the **Commerce navigation hierarchy** type are referenced when you browse products by category online or in point of sale (POS).</span></span>

## <a name="hierarchy-types"></a><span data-ttu-id="bd9a3-113">Hierarkityper</span><span class="sxs-lookup"><span data-stu-id="bd9a3-113">Hierarchy types</span></span>

<span data-ttu-id="bd9a3-114">Följande tabell listar de tillgängliga kategorihierarkityperna och det allmänna syftet med varje typ.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-114">The following table lists the types of category hierarchies that are available and the general purpose of each type.</span></span>

| <span data-ttu-id="bd9a3-115">Kategorihierarkityp</span><span class="sxs-lookup"><span data-stu-id="bd9a3-115">Category hierarchy type</span></span>       | <span data-ttu-id="bd9a3-116">Syfte</span><span class="sxs-lookup"><span data-stu-id="bd9a3-116">Purpose</span></span> |
|-------------------------------|---------|
| <span data-ttu-id="bd9a3-117">Produkthierarki</span><span class="sxs-lookup"><span data-stu-id="bd9a3-117">Product hierarchy</span></span>      | <span data-ttu-id="bd9a3-118">Använd markera den här hierarkityp för att definiera den allmänna odukthierarkin (butik) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-118">Use this hierarchy type to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="bd9a3-119">Du kan använda den här hierarkitypen för marknadsföring, prissättning och kampanjer, rapportering och sortimentplanering.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-119">You can use this hierarchy type for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="bd9a3-120">Endast en produkthierarki kan tilldelas den här hierarkitypen.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-120">Only one product hierarchy can be assigned this hierarchy type.</span></span> |
| <span data-ttu-id="bd9a3-121">Tilläggshierarki</span><span class="sxs-lookup"><span data-stu-id="bd9a3-121">Supplemental hierarchy</span></span> | <span data-ttu-id="bd9a3-122">Använd den här hierarkitypen för eventuella ytterligare kategorihierarkier som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-122">Use this hierarchy type for any additional category hierarchies that you want to create.</span></span> <span data-ttu-id="bd9a3-123">Till exempel på våren har du en kampanj för badkläder.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-123">For example, in the spring, you have a promotion for swimwear.</span></span> <span data-ttu-id="bd9a3-124">Därför kan du använda dina badklädesprodukter i en separat kategorihierarki och tillämpa kampanjprissättningen i de olika produktkategorierna.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-124">Therefore, you include your swimwear products in a separate category hierarchy and apply the promotional pricing to the various product categories.</span></span> |
| <span data-ttu-id="bd9a3-125">Navigeringshierarki</span><span class="sxs-lookup"><span data-stu-id="bd9a3-125">Navigation hierarchy</span></span>   | <span data-ttu-id="bd9a3-126">Använd den här hierarkitypen om du vill gruppera och ordna produkter till kategorier, så att du kan bläddra bland produkterna online eller på betalningsstället.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-126">Use this hierarchy type to group and organize products into categories so that the products can be browsed online or in POS.</span></span> |

<span data-ttu-id="bd9a3-127">Genom att använda en kategorihierarki för strukturering av dina produkter, kan du ställa in och underhålla produktattribut och egenskaper på kategorinivån.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-127">By using a category hierarchy to structure your products, you can set up and maintain product attributes and properties at the category level.</span></span> <span data-ttu-id="bd9a3-128">Dessa attribut och egenskaper omfattar inställningar för produktdimensioner och butiksinställningar.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-128">These attributes and properties include settings for product dimensions and POS settings.</span></span> <span data-ttu-id="bd9a3-129">Vissa produkter som du tilldelar kategorierna automatiskt, ärver de attribut och egenskaper som du definierar.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-129">Any products that you assign to the categories automatically inherit the attributes and properties that you define.</span></span> <span data-ttu-id="bd9a3-130">Du kan också kopiera egenskapsinställningarna för en produkt till flera produkter i en vald kategori samtidigt.</span><span class="sxs-lookup"><span data-stu-id="bd9a3-130">You can also copy the property settings for any product to multiple products in a selected category at the same time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]