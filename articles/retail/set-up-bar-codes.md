---
title: "Ställ in streckkoder"
description: "Denna artikel beskriver hur du använder streckkoder i Microsoft Dynamics 365 for Retail."
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
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fdc56bf468babd4b0b0652d9791114af676c8470
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-bar-codes"></a><span data-ttu-id="d7042-103">Ställ in streckkoder</span><span class="sxs-lookup"><span data-stu-id="d7042-103">Set up bar codes</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="d7042-104">Denna artikel beskriver hur du använder streckkoder i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="d7042-104">This article describes how to use bar codes in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="d7042-105">Du kan använda streckkoder för att köpa eller sälja produkter, spåra produktvarianter och ställa in kunder och medarbetare.</span><span class="sxs-lookup"><span data-stu-id="d7042-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="d7042-106">Du kan också använda streckkoder till att utfärda och signera kuponger, presentkort och kreditnotor.</span><span class="sxs-lookup"><span data-stu-id="d7042-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="d7042-107">Du kan lägga upp butiksprodukter så att de har standardstreckkoder eller anpassade interna streckkoder.</span><span class="sxs-lookup"><span data-stu-id="d7042-107">You can set up retail products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="d7042-108">Produkter kan ha fler än en streckkod.</span><span class="sxs-lookup"><span data-stu-id="d7042-108">Products can have more than one bar code.</span></span> <span data-ttu-id="d7042-109">Till exempel kan en produkt ha flera streckkoder om den kommer från olika tillverkare, eller om den har varianter baserat på storlek, utförande eller färg.</span><span class="sxs-lookup"><span data-stu-id="d7042-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="d7042-110">Streckkoder kan innehålla produktens vikt eller pris.</span><span class="sxs-lookup"><span data-stu-id="d7042-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="d7042-111">Streckkodsmasker är mallar som används för att skapa streckkoder.</span><span class="sxs-lookup"><span data-stu-id="d7042-111">Bar code masks are templates that are used to create bar codes.</span></span> <span data-ttu-id="d7042-112">**Obs!** Om du tilldelar varje variantkombination en unik streckkod kan du skanna artikelstreckkoden i kassan och sedan låta programmet bestämma vilken variant av produkten som säljs.</span><span class="sxs-lookup"><span data-stu-id="d7042-112">**Note:** If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="d7042-113">Du kan också samla in och visa statistik om försäljningen per variant.</span><span class="sxs-lookup"><span data-stu-id="d7042-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="d7042-114">Varje storlek-, färg- och utförandegrupp kan tilldelas ett unikt nummer som identifierar den gruppen i streckkoden.</span><span class="sxs-lookup"><span data-stu-id="d7042-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="d7042-115">I Dynamics 365 for Retail används streckkodsmasken för att generera streckkoder automatiskt för varje variantkombination.</span><span class="sxs-lookup"><span data-stu-id="d7042-115">Dynamics 365 for Retail uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="d7042-116">Denna funktion kan vara praktisk om det förekommer flera storlekar, färger och utföranden eftersom antalet kombinationer ökar markant med varje variantkod som läggs till.</span><span class="sxs-lookup"><span data-stu-id="d7042-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="d7042-117">Om denna funktion inte används måste streckkoder manuellt tilldelas varje kombination som representerar en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="d7042-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span> <span data-ttu-id="d7042-118">Du kan skapa streckkoder manuellt eller automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d7042-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="d7042-119">Slutför följande uppgifter i den ordning som de visas i för att skapa streckkoder.</span><span class="sxs-lookup"><span data-stu-id="d7042-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1.  <span data-ttu-id="d7042-120">[Ställ in streckkodsmasktecken](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="d7042-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2.  <span data-ttu-id="d7042-121">[Ställ in streckkodsmasker](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="d7042-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3.  <span data-ttu-id="d7042-122">Konfigurera streckkodsinställningar.</span><span class="sxs-lookup"><span data-stu-id="d7042-122">Configure bar code setups.</span></span>
4.  <span data-ttu-id="d7042-123">Skapa streckkoder för specifika produkter.</span><span class="sxs-lookup"><span data-stu-id="d7042-123">Create bar codes for products.</span></span>


<a name="see-also"></a><span data-ttu-id="d7042-124">Se även</span><span class="sxs-lookup"><span data-stu-id="d7042-124">See also</span></span>
--------

[<span data-ttu-id="d7042-125">Ställ in streckkodsmasker</span><span class="sxs-lookup"><span data-stu-id="d7042-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)




