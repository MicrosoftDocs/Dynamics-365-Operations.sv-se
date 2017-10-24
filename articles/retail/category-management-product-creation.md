---
title: Hantering och skapande av produktkategorier
description: "Detta avsnitt beskriver de förbättringar som gjorts inom hanteringsupplevelsen för produktkategorier inom detaljhandel. Dessa förbättringar gör det möjligt för marknadsföringschefer att skapa en korrelation mellan hierarkin bland detaljhandelsprodukter och frisläppt produktinformation."
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: 
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 6b9afb40b68b672514c083d99efbc9bd098dd561
ms.openlocfilehash: b158ff5b277c125e0aa158c071007ed8a0f25482
ms.contentlocale: sv-se
ms.lasthandoff: 10/03/2017

---

# <a name="product-category-management-and-creation"></a><span data-ttu-id="cd005-104">Hantering och skapande av produktkategorier</span><span class="sxs-lookup"><span data-stu-id="cd005-104">Product category management and creation</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="cd005-105">De förbättringar som har gjorts inom hanteringsupplevelsen för produktkategorier inom detaljhandeln gör det möjligt för marknadsföringschefer att skapa en korrelation mellan hierarkin bland detaljhandelsprodukter och frisläppt produktinformation.</span><span class="sxs-lookup"><span data-stu-id="cd005-105">Enhancements that have been made to the management experience for Retail product categories let merchandising managers have a correlation between Retail product hierarchy and released product details.</span></span> <span data-ttu-id="cd005-106">I arbetsytan **Kategori- och produkthantering** väljer du **Hierarki för detaljhandelsprodukt** för att öppna sidan **Ny struktur för produktkategori inom detaljhandel** om du vill visa dessa förbättringar.</span><span class="sxs-lookup"><span data-stu-id="cd005-106">To view these enhancements, in the **Category & product management**  workspace, select **Retail product hierarchy** to open the **New structure of Retail product category** page.</span></span> 

<span data-ttu-id="cd005-107">I tidigare versioner delades produktegenskaperna upp i grundläggande produktegenskaper och produktegenskaper för detaljhandel, baserat på omfattningen av deras tillämpbarhet.</span><span class="sxs-lookup"><span data-stu-id="cd005-107">In previous releases, product properties were divided into Basic product properties and Retail product properties, based on the scope of their applicability.</span></span> <span data-ttu-id="cd005-108">Produktegenskaperna inom detaljhandel var *globala*.</span><span class="sxs-lookup"><span data-stu-id="cd005-108">Retail product properties were *global*.</span></span> <span data-ttu-id="cd005-109">Med andra ord delades samma värde för en viss produktegenskap av samtliga juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="cd005-109">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="cd005-110">Grundläggande produktegenskaper var *specifika för juridisk person*.</span><span class="sxs-lookup"><span data-stu-id="cd005-110">Basic product properties were *legal entity–specific*.</span></span> <span data-ttu-id="cd005-111">Med andra ord kunde en viss produktegenskap variera mellan olika juridiska personer baserat på individuella affärskrav.</span><span class="sxs-lookup"><span data-stu-id="cd005-111">In other words, a given product property might differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="cd005-112">I och med dessa förbättringar för produktkategorier i kategorin Detaljhandelsprodukter fortsätter vi att separera olika fält. Detta sker baserat på dessas tillämpbarhet inom en viss grupp i syfte att reflektera formstrukturen i den frisläppta produktinformationen.</span><span class="sxs-lookup"><span data-stu-id="cd005-112">With these enhancements, for product properties in the Retail product category, we continue to separate the fields, based on their applicability within a group, to reflect the released product details form structure.</span></span>

<span data-ttu-id="cd005-113">Du kan växla mellan att hantera egenskaper specifika för den juridiska personen över samtliga juridiska personer och att hantera dem för en specifik juridisk person.</span><span class="sxs-lookup"><span data-stu-id="cd005-113">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="cd005-114">Välj helt enkelt **Visa/redigera för samtliga juridiska personer** eller **Visa/redigera för en specifik juridisk person** efter behov.</span><span class="sxs-lookup"><span data-stu-id="cd005-114">Just select **View/Edit for all legal entities** or **View/Edit for a specific legal entity** as you require.</span></span>

<span data-ttu-id="cd005-115">Marknadsföringschefer kan även definiera standardvärden för en ytterligare uppsättning produktegenskaper på individuell kategorinivå.</span><span class="sxs-lookup"><span data-stu-id="cd005-115">Merchandising managers can also define default values for an additional set of product properties at the level of an individual category.</span></span> <span data-ttu-id="cd005-116">Dessa egenskapsvärden går i arv till en produkt baserat på produktens koppling till en kategori när produkten skapas.</span><span class="sxs-lookup"><span data-stu-id="cd005-116">These property values are inherited by a product, based on their association with a category at the time of product creation.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="cd005-117">Välj egenskaper i kategoriformuläret för detaljhandelsprodukt om du vill uppdatera produkter</span><span class="sxs-lookup"><span data-stu-id="cd005-117">Select properties to update products from the Retail product category form</span></span>

<span data-ttu-id="cd005-118">Du kan använda logiska gruppegenskaper för att välja vilka uppdaterade produktegenskaper som ska appliceras på associerade produkter.</span><span class="sxs-lookup"><span data-stu-id="cd005-118">You can use logical grouping properties to select which updated product properties should be pushed to associated products.</span></span>

<span data-ttu-id="cd005-119">Marknadsföringschefer kan modifiera dessa ärvda produktegenskaper för respektive produkt så att dessa motsvarar individuella affärskrav.</span><span class="sxs-lookup"><span data-stu-id="cd005-119">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>

