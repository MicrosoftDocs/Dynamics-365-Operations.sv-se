---
title: Butikshierarkier
description: "Den här artikeln beskriver butikshierarkierna i Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 817696566473bc5f31a7ff11c04291351dfd4764
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="retail-hierarchies"></a><span data-ttu-id="8307d-103">Butikshierarkier</span><span class="sxs-lookup"><span data-stu-id="8307d-103">Retail hierarchies</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="8307d-104">Den här artikeln beskriver butikshierarkierna i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="8307d-104">This article describes retail hierarchies in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="8307d-105">Du kan skapa en butikskategorihierarki för att strukturera de produkter som du säljer via butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="8307d-105">You can create a retail category hierarchy to organize the products that you sell through your retail channels.</span></span> <span data-ttu-id="8307d-106">Du kan använda butiksprodukthierarkier för att kategorisera eller gruppera produkter.</span><span class="sxs-lookup"><span data-stu-id="8307d-106">You can use retail product hierarchies to categorize or group products.</span></span> <span data-ttu-id="8307d-107">Du kan sedan använda dessa produkter om du vill skapa produktsortiment och kundbonusprogram.</span><span class="sxs-lookup"><span data-stu-id="8307d-107">You can then use these products to create product assortments and customer loyalty programs.</span></span> <span data-ttu-id="8307d-108">Du kan också tilldela produktattribut och egenskaper, tilldela en prissättningstruktur, inkludera produkter i produkterbjudanden och använda produkterna för rapportering.</span><span class="sxs-lookup"><span data-stu-id="8307d-108">You can also assign product attributes and properties, assign a pricing structure, include the products in product promotions, and use the products for reporting.</span></span> <span data-ttu-id="8307d-109">Du kan skapa en butikskategorihierarki som representerar alla produkter och kategorier i organisationen och använder sedan kategorihierarkin för flera syften.</span><span class="sxs-lookup"><span data-stu-id="8307d-109">You can create one retail category hierarchy to represent all the products and categories in your organization, and then use that category hierarchy for multiple purposes.</span></span> <span data-ttu-id="8307d-110">Du kan också skapa flera butikskategorihierarkier för särskilda syften, till exempel produkterbjudanden.</span><span class="sxs-lookup"><span data-stu-id="8307d-110">Alternatively, you can create multiple retail category hierarchies for special purposes, such as product promotions.</span></span> <span data-ttu-id="8307d-111">När du skapar en Produkthierarki (butik), måste du tilldela en kategorihierarkityp för att identifiera syftet med kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="8307d-111">When you create a retail product hierarchy, you must assign a category hierarchy type to identify the purpose of the category hierarchy.</span></span> <span data-ttu-id="8307d-112">Om du till exempel om endast produkthierarkier som tilldelas typen **Butiksnavigeringshierarki** är refererade när du bläddrar i produkter efter kategori online eller på betalningsplatsen (POS).</span><span class="sxs-lookup"><span data-stu-id="8307d-112">For example, only product hierarchies that are assigned the **Retail navigation hierarchy** type are referenced when you browse products by category online or in point of sale (POS).</span></span>

## <a name="retail-hierarchy-types"></a><span data-ttu-id="8307d-113">Typ av butikshierarki</span><span class="sxs-lookup"><span data-stu-id="8307d-113">Retail hierarchy types</span></span>
<span data-ttu-id="8307d-114">Följande tabell listar de tillgängliga kategorihierarkityperna och det allmänna syftet med varje typ.</span><span class="sxs-lookup"><span data-stu-id="8307d-114">The following table lists the types of retail category hierarchies that are available and the general purpose of each type.</span></span>

| <span data-ttu-id="8307d-115">Kategorihierarkityp</span><span class="sxs-lookup"><span data-stu-id="8307d-115">Category hierarchy type</span></span>       | <span data-ttu-id="8307d-116">Syfte</span><span class="sxs-lookup"><span data-stu-id="8307d-116">Purpose</span></span>                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8307d-117">Produkthierarki (butik)</span><span class="sxs-lookup"><span data-stu-id="8307d-117">Retail product hierarchy</span></span>      | <span data-ttu-id="8307d-118">Använd markera den här hierarkityp för att definiera den allmänna odukthierarkin (butik) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="8307d-118">Use this hierarchy type to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="8307d-119">Du kan använda den här hierarkitypen för marknadsföring, prissättning och kampanjer, rapportering och sortimentplanering.</span><span class="sxs-lookup"><span data-stu-id="8307d-119">You can use this hierarchy type for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="8307d-120">Endast en butiksprodukthierarki kan tilldelas den här hierarkitypen.</span><span class="sxs-lookup"><span data-stu-id="8307d-120">Only one retail product hierarchy can be assigned this hierarchy type.</span></span>                                       |
| <span data-ttu-id="8307d-121">Tilläggshierarki</span><span class="sxs-lookup"><span data-stu-id="8307d-121">Supplemental retail hierarchy</span></span> | <span data-ttu-id="8307d-122">Använd den här hierarkitypen för eventuella ytterligare butikskategorihierarkier som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="8307d-122">Use this hierarchy type for any additional retail category hierarchies that you want to create.</span></span> <span data-ttu-id="8307d-123">Till exempel på våren har du en kampanj för badkläder.</span><span class="sxs-lookup"><span data-stu-id="8307d-123">For example, in the spring, you have a promotion for swimwear.</span></span> <span data-ttu-id="8307d-124">Därför kan du använda dina badklädesprodukter i en separat kategorihierarki och tillämpa kampanjprissättningen i de olika produktkategorierna.</span><span class="sxs-lookup"><span data-stu-id="8307d-124">Therefore, you include your swimwear products in a separate category hierarchy and apply the promotional pricing to the various product categories.</span></span> |
| <span data-ttu-id="8307d-125">Butiksnavigeringshierarki</span><span class="sxs-lookup"><span data-stu-id="8307d-125">Retail navigation hierarchy</span></span>   | <span data-ttu-id="8307d-126">Använd den här hierarkitypen om du vill gruppera och ordna produkter till kategorier, så att du kan bläddra bland produkterna online eller på betalningsstället.</span><span class="sxs-lookup"><span data-stu-id="8307d-126">Use this hierarchy type to group and organize products into categories so that the products can be browsed online or in POS.</span></span>                                                                                                                                                                                       |

<span data-ttu-id="8307d-127">Genom att använda en butikskategorihierarki för strukturering av dina produkter, kan du ställa in och underhålla produktattribut och egenskaper på kategorinivån.</span><span class="sxs-lookup"><span data-stu-id="8307d-127">By using a retail category hierarchy to structure your products, you can set up and maintain product attributes and properties at the category level.</span></span> <span data-ttu-id="8307d-128">Dessa attribut och egenskaper omfattar inställningar för produktdimensioner och butiksinställningar.</span><span class="sxs-lookup"><span data-stu-id="8307d-128">These attributes and properties include settings for product dimensions and POS settings.</span></span> <span data-ttu-id="8307d-129">Vissa produkter som du tilldelar kategorierna automatiskt, ärver de attribut och egenskaper som du definierar.</span><span class="sxs-lookup"><span data-stu-id="8307d-129">Any products that you assign to the categories automatically inherit the attributes and properties that you define.</span></span> <span data-ttu-id="8307d-130">Du kan också kopiera egenskapsinställningarna för en produkt till flera produkter i en vald kategori samtidigt.</span><span class="sxs-lookup"><span data-stu-id="8307d-130">You can also copy the property settings for any product to multiple products in a selected category at the same time.</span></span>




