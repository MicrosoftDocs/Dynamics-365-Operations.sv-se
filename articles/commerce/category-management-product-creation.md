---
title: Hantera produktkategorier och produkter
description: Det här avsnittet beskriver hur marknadsföringschefer kan använda produktkategorier för att hantera relationer mellan handelsprodukthierarki och information om frisläppt produkt.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResProductCategory, EcoResCategoryAddProduct, EcoResAttributeValue
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cee79d6937afeec1e607abde49d52790c51e98a4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001084"
---
# <a name="manage-product-categories-and-products"></a><span data-ttu-id="68152-103">Hantera produktkategorier och produkter</span><span class="sxs-lookup"><span data-stu-id="68152-103">Manage product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="68152-104">Det här avsnittet beskriver ett bättre sätt att hantera produktkategorier och produkter i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="68152-104">This topic describes an enhanced way to manage product categories and products in Dynamics 365 Commerce.</span></span> <span data-ttu-id="68152-105">Dessa förbättringar gör det möjligt för marknadsföringschefer att visa en struktur som delas mellan produktegenskaper bland produkter och information om frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="68152-105">The enhancements let merchandising managers view a structure of product properties that is shared between the product hierarchy and released product details.</span></span>

<span data-ttu-id="68152-106">För mer information om hur du hanterar produktkategorier på arbetsytan **Kategori- och produkthantering**, välj panelen **Produkthierarki (handel)**.</span><span class="sxs-lookup"><span data-stu-id="68152-106">To learn more about how to manage product categories, in the **Category and product management** workspace, select the **Commerce product hierarchy** tile.</span></span>

<span data-ttu-id="68152-107">Lägg märke till den förbättrade struktur för sidan **Produkthierarki (handel)**.</span><span class="sxs-lookup"><span data-stu-id="68152-107">Notice the enhanced structure of the **Commerce product hierarchy** page that appears.</span></span> <span data-ttu-id="68152-108">I tidigare versioner av appen delades produktegenskaperna upp i *Grundläggande produktegenskaper* och *Produktegenskaper för detaljhandel*, baserat på deras tillämpningsområde.</span><span class="sxs-lookup"><span data-stu-id="68152-108">In previous versions of the app, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="68152-109">Produktegenskaper (butik) är *globala* i sitt tillämpningsområde.</span><span class="sxs-lookup"><span data-stu-id="68152-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="68152-110">Med andra ord delades samma värde för en viss produktegenskap av samtliga juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="68152-110">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="68152-111">Däremot är grundläggande produktegenskaper specifika *juridisk person*.</span><span class="sxs-lookup"><span data-stu-id="68152-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="68152-112">Med andra ord kunde en viss grundläggande produktegenskap variera mellan olika juridiska personer beroende på individuella affärskrav för varje juridisk person.</span><span class="sxs-lookup"><span data-stu-id="68152-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="68152-113">I den förbättrade produktkategoristrukturen separeras produktegenskaper logiskt baserat på deras tillämpbarhet inom en viss grupp i syfte att reflektera strukturen i informationen om den frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="68152-113">In the enhanced product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Fältgruppering baserat på egenskapens tillämpningsområde](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="68152-115">Du kan växla mellan att hantera egenskaper specifika för den juridiska personen över samtliga juridiska personer och att hantera dem för en specifik juridisk person.</span><span class="sxs-lookup"><span data-stu-id="68152-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="68152-116">Om du vill hantera egenskaper i alla juridiska personer, välj **Visa för alla juridiska personer** (eller **Redigera för alla juridiska personer**).</span><span class="sxs-lookup"><span data-stu-id="68152-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Visa/redigera för alla juridiska personer](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="68152-118">Om du vill hantera egenskaper för en viss juridisk person **Visa för en viss juridisk person** (eller **Redigera för en viss juridisk person**).</span><span class="sxs-lookup"><span data-stu-id="68152-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Visa/redigera för en viss juridisk person](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="68152-120">Dessutom, i den förbättrade produktkategoristrukturen kan en marknadsföringschef nu också definiera standardvärden för ytterligare en uppsättning produktegenskaper på en enskild kategorinivå.</span><span class="sxs-lookup"><span data-stu-id="68152-120">Additionally, in the enhanced product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="68152-121">Sedan när produkter skapas ärver de standardvärden för sina produktegenskaper baserat på kopplingen av de här egenskaperna med en enskild kategori från produkthierarkin.</span><span class="sxs-lookup"><span data-stu-id="68152-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in the product hierarchy.</span></span> <span data-ttu-id="68152-122">Dessa ärvda produktegenskaper kan också ändras för respektive produkt så att dessa motsvarar individuella affärskrav.</span><span class="sxs-lookup"><span data-stu-id="68152-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a><span data-ttu-id="68152-123">Välja egenskaper på sidan Produkthierarki (handel) om du vill uppdatera produkter</span><span class="sxs-lookup"><span data-stu-id="68152-123">Selecting properties to update products on the Commerce product hierarchy page</span></span>

<span data-ttu-id="68152-124">Du kan använda den här nya förbättrade strukturen för produktegenskaper för att välja vilka uppdaterade produktegenskaper som måste skickas till associerade produkter.</span><span class="sxs-lookup"><span data-stu-id="68152-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="68152-125">På sidan **Produkthierarki (handel)** på åtgärdsfönstret, välj **Kategori** och välj sedan **Uppdatera produkter** för att öppna dialogrutan **Uppdatera produkter**.</span><span class="sxs-lookup"><span data-stu-id="68152-125">On the **Commerce product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Dialogrutan Uppdatera produkter](media/NewUpdateProductsEnhancedView.PNG)
