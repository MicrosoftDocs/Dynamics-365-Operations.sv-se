---
title: Produktkategorihantering
description: "Det här avsnittet beskriver hur marknadsföringschefer kan använda produktkategorier (butik) för att hantera relationer mellan butiksprodukthierarki och information om frisläppt produkt."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: sv-se
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a><span data-ttu-id="7e76b-103">Förbättrad produkt- och kategorihantering</span><span class="sxs-lookup"><span data-stu-id="7e76b-103">Enhanced product and category management</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="7e76b-104">Det här avsnittet beskriver ett bättre sätt att hantera produktkategorier (butik) och produkter i Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="7e76b-104">This topic describes an enhanced way to manage Retail product categories and products in Dynamics 365 for Retail.</span></span> <span data-ttu-id="7e76b-105">Dessa förbättringar gör det möjligt för marknadsföringschefer att visa en gemensam struktur för produktegenskaper bland detaljhandelsprodukter och information om frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="7e76b-105">These enhancements let merchandising managers view a common structure of product properties between Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="7e76b-106">Om du vill ha mer information om hur du hanterar produktkategorier (butik), gå till **Produkthierarki (butik)** från arbetsytan **Kategori- och produkthantering** och notera förbättrad struktur för sidan **Produkthierarki (butik)**.</span><span class="sxs-lookup"><span data-stu-id="7e76b-106">To learn more about managing Retail product categories, go to **Retail product hierarchy** from the **Category and product management** workspace, and note the enhanced structure of the **Retail product category** page.</span></span>

![Arbetsytan Kategori- och produkthantering](media/LaunchRetailProductHierarchy.png)

<span data-ttu-id="7e76b-108">I tidigare versioner delades produktegenskaperna upp i **Grundläggande produktegenskaper** och **Produktegenskaper för detaljhandel**, baserat på deras tillämpningsområde.</span><span class="sxs-lookup"><span data-stu-id="7e76b-108">In previous versions, product properties were divided into **Basic product properties** and **Retail product properties**, based on the scope of their applicability.</span></span> <span data-ttu-id="7e76b-109">**Produktegenskaper för detaljhandel** var *global* efter tillämpningsområde vilket innebär att en given **Produktegenskap för detaljhandel**, delas lika mellan alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="7e76b-109">**Retail product properties** were *global* by scope of applicability, which means that for a given **Retail product property**, the same value is shared across all legal entities.</span></span> <span data-ttu-id="7e76b-110">**Grundläggande produktegenskaper** är *specifika för juridisk person*.</span><span class="sxs-lookup"><span data-stu-id="7e76b-110">**Basic product properties** are *legal entity specific*.</span></span> <span data-ttu-id="7e76b-111">Med andra ord kunde en viss **Grundläggande produktegenskap** variera mellan olika juridiska personer baserat på individuella affärskrav.</span><span class="sxs-lookup"><span data-stu-id="7e76b-111">In other words, for a given **Basic product property** the value can differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="7e76b-112">I den förbättrade produktkategoristrukturen separeras produktegenskaper logiskt baserat på deras tillämpbarhet inom en viss grupp i syfte att reflektera formstrukturen i informationen om den frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="7e76b-112">In the enhanced Retail product category structure, product properties are logically separated based on their applicability within a group, to reflect the released product details form structure.</span></span>

![Gruppering av fält baserat på deras tillämpningsområde](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="7e76b-114">Du kan växla mellan att hantera egenskaper specifika för den juridiska personen över samtliga juridiska personer och att hantera dem för en specifik juridisk person.</span><span class="sxs-lookup"><span data-stu-id="7e76b-114">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="7e76b-115">För att göra detta, välj antingen **Visa/redigera för samtliga juridiska personer** eller **Visa/redigera för en specifik juridisk person**.</span><span class="sxs-lookup"><span data-stu-id="7e76b-115">To do this, select either **View/Edit for all legal entities** or **View/Edit for a specific legal entity**.</span></span>

![Växla vy mellan en person och alla juridiska personer](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Växla vy mellan en person och alla juridiska personer](media/ToggleToEditForAllLegalEntities.PNG)  

<span data-ttu-id="7e76b-118">Jämfört med tidigare versioner i den nya produktkategoristrukturen (butik) kan en marknadsföringschef också definiera standardvärden för ytterligare en uppsättning produktegenskaper på en enskild kategorinivå.</span><span class="sxs-lookup"><span data-stu-id="7e76b-118">Compared to previous versions, in the new Retail product category structure a merchandising manager can also define default values for an additional set of product properties at an individual category level.</span></span> <span data-ttu-id="7e76b-119">När produkten skapas kommer dessa standardinställda produktegenskapvärden att ärvas av en produkt baserat på deras koppling till en enskild kategori från produkthierarkin (butik).</span><span class="sxs-lookup"><span data-stu-id="7e76b-119">At the time of product creation, these default product property values are inherited by a product, based on their association with an individual category from Retail product hierarchy.</span></span> <span data-ttu-id="7e76b-120">Dessa ärvda produktegenskaper kan också ändras för respektive produkt så att dessa motsvarar individuella affärskrav.</span><span class="sxs-lookup"><span data-stu-id="7e76b-120">These inherited product properties can also be modified for each product, to meet individual business requirements.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="7e76b-121">Välj egenskaper i kategoriformuläret för detaljhandelsprodukt om du vill uppdatera produkter</span><span class="sxs-lookup"><span data-stu-id="7e76b-121">Select properties to update products from the Retail product category form</span></span> 
 
<span data-ttu-id="7e76b-122">Du kan använda den här nya förbättrade strukturen för produktegenskaper för att välja vilka uppdaterade produktegenskaper som måste skickas till associerade produkter.</span><span class="sxs-lookup"><span data-stu-id="7e76b-122">You can use this new enhanced structure for product properties to select which updated product properties must be pushed to associated products.</span></span> 

![Ny utökad vy över Uppdatera produkter](media/NewUpdateProductsEnhancedView.PNG) 

<span data-ttu-id="7e76b-124">Marknadsföringschefer kan modifiera dessa ärvda produktegenskaper för respektive produkt så att dessa motsvarar individuella affärskrav.</span><span class="sxs-lookup"><span data-stu-id="7e76b-124">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>


