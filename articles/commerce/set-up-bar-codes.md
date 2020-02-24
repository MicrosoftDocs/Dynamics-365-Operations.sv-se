---
title: Ställa in streckkoder
description: Det här avsnittet beskriver hur du använder streckkoder i Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 74a08fc168dd3c41fa501ca8110af899a181e333
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024086"
---
# <a name="set-up-bar-codes"></a><span data-ttu-id="dc45e-103">Ställa in streckkoder</span><span class="sxs-lookup"><span data-stu-id="dc45e-103">Set up bar codes</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dc45e-104">Det här avsnittet beskriver hur du använder streckkoder i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dc45e-104">This article describes how to use bar codes in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="dc45e-105">Du kan använda streckkoder för att köpa eller sälja produkter, spåra produktvarianter och ställa in kunder och medarbetare.</span><span class="sxs-lookup"><span data-stu-id="dc45e-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="dc45e-106">Du kan också använda streckkoder till att utfärda och signera kuponger, presentkort och kreditnotor.</span><span class="sxs-lookup"><span data-stu-id="dc45e-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="dc45e-107">Du kan lägga upp butiksprodukter så att de har standardstreckkoder eller anpassade interna streckkoder.</span><span class="sxs-lookup"><span data-stu-id="dc45e-107">You can set up retail products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="dc45e-108">Produkter kan ha fler än en streckkod.</span><span class="sxs-lookup"><span data-stu-id="dc45e-108">Products can have more than one bar code.</span></span> <span data-ttu-id="dc45e-109">Till exempel kan en produkt ha flera streckkoder om den kommer från olika tillverkare, eller om den har varianter baserat på storlek, utförande eller färg.</span><span class="sxs-lookup"><span data-stu-id="dc45e-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="dc45e-110">Streckkoder kan innehålla produktens vikt eller pris.</span><span class="sxs-lookup"><span data-stu-id="dc45e-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="dc45e-111">Streckkodsmasker är mallar som används för att skapa streckkoder.</span><span class="sxs-lookup"><span data-stu-id="dc45e-111">Bar code masks are templates that are used to create bar codes.</span></span>

> [!NOTE]
> <span data-ttu-id="dc45e-112">Om du tilldelar varje variantkombination en unik streckkod kan du skanna artikelstreckkoden i kassan och sedan låta programmet bestämma vilken variant av produkten som säljs.</span><span class="sxs-lookup"><span data-stu-id="dc45e-112">If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="dc45e-113">Du kan också samla in och visa statistik om försäljningen per variant.</span><span class="sxs-lookup"><span data-stu-id="dc45e-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="dc45e-114">Varje storlek-, färg- och utförandegrupp kan tilldelas ett unikt nummer som identifierar den gruppen i streckkoden.</span><span class="sxs-lookup"><span data-stu-id="dc45e-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="dc45e-115">Retail använder streckkodsmasken för att generera streckkoder automatiskt för varje variantkombination.</span><span class="sxs-lookup"><span data-stu-id="dc45e-115">Retail uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="dc45e-116">Denna funktion kan vara praktisk om det förekommer flera storlekar, färger och utföranden eftersom antalet kombinationer ökar markant med varje variantkod som läggs till.</span><span class="sxs-lookup"><span data-stu-id="dc45e-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="dc45e-117">Om denna funktion inte används måste streckkoder manuellt tilldelas varje kombination som representerar en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="dc45e-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span>

<span data-ttu-id="dc45e-118">Du kan skapa streckkoder manuellt eller automatiskt.</span><span class="sxs-lookup"><span data-stu-id="dc45e-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="dc45e-119">Slutför följande uppgifter i den ordning som de visas i för att skapa streckkoder.</span><span class="sxs-lookup"><span data-stu-id="dc45e-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1. <span data-ttu-id="dc45e-120">[Ställ in streckkodsmasktecken](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="dc45e-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2. <span data-ttu-id="dc45e-121">[Ställ in streckkodsmasker](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="dc45e-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3. <span data-ttu-id="dc45e-122">Konfigurera streckkodsinställningar.</span><span class="sxs-lookup"><span data-stu-id="dc45e-122">Configure bar code setups.</span></span>
4. <span data-ttu-id="dc45e-123">Skapa streckkoder för specifika produkter.</span><span class="sxs-lookup"><span data-stu-id="dc45e-123">Create bar codes for products.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dc45e-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dc45e-124">Additional resources</span></span>

[<span data-ttu-id="dc45e-125">Ställa in streckkodsmasker</span><span class="sxs-lookup"><span data-stu-id="dc45e-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)
