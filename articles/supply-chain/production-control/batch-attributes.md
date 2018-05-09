---
title: Batchattribut
description: "Den här ämnet innehåller information om batchattribut. Batchattribut är egenskaper för råmaterial och färdiga produkter som utgör lagerbatchar. Ämnet innehåller även information om hur du tilldelar batchattribut och hur du kan söka i dem när du reserverar batchar."
author: YuyuScheller
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 255cb8f530b1906409c54dc446872802214482e8
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="batch-attributes"></a><span data-ttu-id="1b8bf-105">Batchattribut</span><span class="sxs-lookup"><span data-stu-id="1b8bf-105">Batch attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b8bf-106">Den här ämnet innehåller information om batchattribut.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-106">This topic provides information about batch attributes.</span></span> <span data-ttu-id="1b8bf-107">Batchattribut är egenskaper för råmaterial och färdiga produkter som utgör lagerbatchar.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-107">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="1b8bf-108">Ämnet innehåller även information om hur du tilldelar batchattribut och hur du kan söka i dem när du reserverar batchar.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-108">The topic also explains how to assign batch attributes, and how you can search on them when you reserve batches.</span></span>

<span data-ttu-id="1b8bf-109">Batchattribut är egenskaper för råmaterial och färdiga produkter som utgör lagerbatchar.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-109">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="1b8bf-110">Batchattribut kan variera, beroende på faktorer som miljöfaktorer, kvaliteten på råmaterial som används för att producera batchen, eller resultatet av den färdiga produkten.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-110">Batch attributes can vary, depending on factors such as environmental conditions, the quality of the raw materials that are used to produce the batch, or the outcome of the finished product.</span></span> <span data-ttu-id="1b8bf-111">Numret och typerna av batchattribut som används, kan variera mycket från en bransch till en annan.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-111">The number and types of batch attributes that are used can vary widely from one industry to another.</span></span> <span data-ttu-id="1b8bf-112">Här följer två exempel som visar hur du använder batchattribut:</span><span class="sxs-lookup"><span data-stu-id="1b8bf-112">Here are two examples that show how to use batch attributes:</span></span>

-   <span data-ttu-id="1b8bf-113">I ostbranschen kan mjölk, som är ett av råmaterialen som används för att tillverka osten, ha attribut som till exempel fetthalt och procentsatsvikt.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-113">In the cheese industry, milk, which is one of the raw materials that are used to produce the cheese, can have attributes such as fat content and percentage weight.</span></span> <span data-ttu-id="1b8bf-114">Osten som tillverkas av mjölken kan i sin tur ha attribut som fukthalt och ålder.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-114">The cheese that is produced from the milk can have other attributes, such as moisture and age.</span></span>
-   <span data-ttu-id="1b8bf-115">I stålbranschen kan järnet som tillverkas ha attribut som procentsatser av magnesiuminnehåll, silverinnehåll och zinkinnehåll.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-115">In the steel industry, the iron that is produced might have attributes such as the percentages of magnesium content, silver content, and zinc content.</span></span>

<span data-ttu-id="1b8bf-116">Fär att bättre kunna hantera numret och typerna av attribut, kan du använda batchattributgrupper.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-116">To better manage the number and types of attributes, you can use batch attribute groups.</span></span> <span data-ttu-id="1b8bf-117">På detta sätt måste du inte lägga till varje enskilt attribut.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-117">In this way, you don't have to add each attribute individually.</span></span>

## <a name="assign-batch-attributes"></a><span data-ttu-id="1b8bf-118">Tilldela batchattribut</span><span class="sxs-lookup"><span data-stu-id="1b8bf-118">Assign batch attributes</span></span>
<span data-ttu-id="1b8bf-119">Du kan tilldela batchattribut till enskilda produkter som hålls i lagerbatchar, eller så kan du tilldela dem till produkter som är associerade med specifika kunder.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-119">You can assign batch attributes to individual products that are held in inventory batches, or you can assign them to products that are associated with specific customers.</span></span> <span data-ttu-id="1b8bf-120">Innan du kan tilldela ett batchattribut på kundnivån, måste du tilldela den till produktnivån.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-120">Before you can assign a batch attribute at the customer level, you must assign it at the product level.</span></span> <span data-ttu-id="1b8bf-121">Produkten måste ha batchdimensionen inställd på **Aktiv** i spårningsdimensiongruppen.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-121">The product must have the batch dimension set to **Active** in the tracking dimension group.</span></span> <span data-ttu-id="1b8bf-122">För att tilldela ett batchattribut till en enskild produkt använder du den produktspecifika sidan.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-122">To assign a batch attribute to an individual product, use the product-specific page.</span></span> <span data-ttu-id="1b8bf-123">Om attributet är specifikt för en produkt för en kund, ska du använda den kundspecifika sidan.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-123">If the attribute is specific to a product for a customer, use the customer-specific page.</span></span> <span data-ttu-id="1b8bf-124">När du lägger till ett attribut till en produkt, definierar du också andra parametrar.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-124">When you add an attribute to a product, you also define other parameters.</span></span> <span data-ttu-id="1b8bf-125">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="1b8bf-125">Here are some examples:</span></span>

-   <span data-ttu-id="1b8bf-126">Det lägsta och högsta intervallen för ett attribut av typerna **Heltal** eller **Del**.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-126">The minimum and maximum ranges for an attribute of the **Integer** or **Fraction** type.</span></span>
-   <span data-ttu-id="1b8bf-127">Toleransåtgärder för ett attribut av typen **Heltal** eller **Del**.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-127">The tolerance actions for an attribute of the **Integer** or **Fraction** type.</span></span> <span data-ttu-id="1b8bf-128">Om värdet för attributet ligger utanför intervallet för minsta och största värde, kan åtgärden vara antingen en varning eller ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-128">If the value of the attribute falls outside the minimum and maximum range, the action can be either a warning message or an error message.</span></span>
-   <span data-ttu-id="1b8bf-129">Målvärdet för attributet.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-129">The target value for the attribute.</span></span> <span data-ttu-id="1b8bf-130">Det här värdet är det optimala värdet för attributet och det gäller för alla attributtyper.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-130">This value is the optimal value of the attribute, and it applies to all attribute types.</span></span>

<span data-ttu-id="1b8bf-131">Du kan öppna sidorna för produkter som du väljer på sidan **Frisläppta produkter** i Produktinformationshantering.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-131">You can access the pages for products that you select on the **Released products** page in Product information management.</span></span> <span data-ttu-id="1b8bf-132">När du har tilldelat batchattribut till en produkt, kan du lägga till specifika värden till attributen på sidan **Batchattribut i lager**.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-132">After you assign batch attributes to a product, you can add specific values to the attributes on the **Inventory batch attributes** page.</span></span>

## <a name="reserve-batches"></a><span data-ttu-id="1b8bf-133">Reservera batchar </span><span class="sxs-lookup"><span data-stu-id="1b8bf-133">Reserve batches</span></span>
<span data-ttu-id="1b8bf-134">Du kan söka i batchattribut när du gör batchreservationer för en försäljningsorder för att fullfölja en kunds order, eller när du plockar och reserverar batchar för en tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-134">You can search on batch attributes when you do batch reservations for a sales order to fulfill a customer's order, or when you pick and reserve batches for a production order.</span></span> <span data-ttu-id="1b8bf-135">Sökninghjälpen hittar en lagerbatch som innehåller produkten som har det batchattribut som du vill ha.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-135">The search helps locate an inventory batch that contains the product that has the batch attribute that you want.</span></span> <span data-ttu-id="1b8bf-136">När du har hittat batchen eller batcharna kan du reservera produkten till den ursprungliga lagertransaktionsraden.</span><span class="sxs-lookup"><span data-stu-id="1b8bf-136">After you locate the batch or batches, you can reserve the product to the originating inventory transaction line.</span></span>




