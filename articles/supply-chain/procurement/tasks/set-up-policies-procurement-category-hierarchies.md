---
title: Ställ in policyer för hierarkier för anskaffningskategorier
description: Använd den här proceduren för att ställa in regler för att beställa produkter i en kategori.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1fdf357466de12bd0188fc43cd266c67af762c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "323167"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a><span data-ttu-id="9a01d-103">Ställ in policyer för hierarkier för anskaffningskategorier</span><span class="sxs-lookup"><span data-stu-id="9a01d-103">Set up policies for procurement category hierarchies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9a01d-104">Använd den här proceduren för att ställa in regler för att beställa produkter i en kategori.</span><span class="sxs-lookup"><span data-stu-id="9a01d-104">Use this procedure to set up rules for ordering products in a category.</span></span> <span data-ttu-id="9a01d-105">Policyreglerna definieras för en specifik inköpspolicy.</span><span class="sxs-lookup"><span data-stu-id="9a01d-105">The rules are defined for a specific purchasing policy.</span></span> <span data-ttu-id="9a01d-106">Åtkomstregeldata kontrollerar vilka anskaffningskategorier som anställda har åtkomst till när de skapar en rekvisition.</span><span class="sxs-lookup"><span data-stu-id="9a01d-106">The category access rule controls which procurement categories employees have access to when they create a requisition.</span></span> <span data-ttu-id="9a01d-107">När en rekvisition skapas fastställs den inköpspolicy och den kategoriåtkomstregel som ska användas av den juridiska person och den driftenhet som medarbetaren tillhör.</span><span class="sxs-lookup"><span data-stu-id="9a01d-107">When a requisition is being created, the purchasing policy and category access rule that should be applied are determined by the legal entity and the operational unit that the employee belongs to.</span></span> <span data-ttu-id="9a01d-108">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="9a01d-108">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="9a01d-109">Denna uppgift utförs vanligtvis av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="9a01d-109">This task would typically be carried out by a purchasing manager.</span></span>


## <a name="find-the-procurement-policy"></a><span data-ttu-id="9a01d-110">Hitta anskaffningpolicyn</span><span class="sxs-lookup"><span data-stu-id="9a01d-110">Find the procurement policy</span></span>
1. <span data-ttu-id="9a01d-111">Gå till anskaffning och källa > Inställningar > Policyer > Inköpspolicyer.</span><span class="sxs-lookup"><span data-stu-id="9a01d-111">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="9a01d-112">Klicka på länken för anskaffningspolicy USMF.</span><span class="sxs-lookup"><span data-stu-id="9a01d-112">Click the link on the Procurement Policy USMF policy.</span></span>
    * <span data-ttu-id="9a01d-113">Detta är policyn som du vill lägga till en regel till.</span><span class="sxs-lookup"><span data-stu-id="9a01d-113">This is the policy that you’ll add a rule to.</span></span> <span data-ttu-id="9a01d-114">Den måste vara en aktiv policy.</span><span class="sxs-lookup"><span data-stu-id="9a01d-114">It must be an Active policy.</span></span>  

## <a name="create-a-category-access-rule"></a><span data-ttu-id="9a01d-115">Skapa en kategoriåtkomstregel</span><span class="sxs-lookup"><span data-stu-id="9a01d-115">Create a category access rule</span></span>
1. <span data-ttu-id="9a01d-116">Välj Policyregel för kategoriåtkomst.</span><span class="sxs-lookup"><span data-stu-id="9a01d-116">Select the Category access policy rule.</span></span>
    * <span data-ttu-id="9a01d-117">Om knappen Skapa policyregel tonasned är det på grund av att det redan finns en aktiv policyregel för Kategoriåtkomst.</span><span class="sxs-lookup"><span data-stu-id="9a01d-117">If the Create policy rule button is dimmed, it’s because there’s already an active policy rule for Category access.</span></span> <span data-ttu-id="9a01d-118">Kontrollera fälten Giltighet och Utgångsdatum för att bestämma vilket den är, sedan väljer du den och klickar på Dra tillbaka policyregel.</span><span class="sxs-lookup"><span data-stu-id="9a01d-118">Check the Effective and Expiration date fields to determine which it is, then select it, and click Retire policy rule.</span></span> <span data-ttu-id="9a01d-119">Om knappen Skapa policyregel är tillgänglig behöver du inte att göra någonting.</span><span class="sxs-lookup"><span data-stu-id="9a01d-119">If the Create policy rule button is available, you don’t need to do anything.</span></span>  
2. <span data-ttu-id="9a01d-120">Klicka på Skapa policyregel.</span><span class="sxs-lookup"><span data-stu-id="9a01d-120">Click Create policy rule.</span></span>
3. <span data-ttu-id="9a01d-121">Ange datum och tid i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="9a01d-121">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="9a01d-122">Tiden får inte överlappa med en annan regel som redan är aktiv.</span><span class="sxs-lookup"><span data-stu-id="9a01d-122">The time must not overlap with another rule that’s already active.</span></span>  
    * <span data-ttu-id="9a01d-123">Välj en kategori som regeln ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="9a01d-123">Select a category that the rule will apply to.</span></span> <span data-ttu-id="9a01d-124">Gör en notering av vilken kategori detta är – du behöver den senare.</span><span class="sxs-lookup"><span data-stu-id="9a01d-124">Make a note of which category this is – you’ll need it later.</span></span> <span data-ttu-id="9a01d-125">När du väljer en kategori kommer alla dess överordnade kategorier också att läggas till i listan för Valda kategorier.</span><span class="sxs-lookup"><span data-stu-id="9a01d-125">When you select a category, its parent category or categories will also be added to the Selected categories list.</span></span>  
    * <span data-ttu-id="9a01d-126">Om du vill att regeln ska gälla alla underkategorier för den valda kategorin, markerar du kryssrutan Inkludera underkategorier.</span><span class="sxs-lookup"><span data-stu-id="9a01d-126">If you want the rule to apply to all subcategories of the selected category, select the Include subcategories check box.</span></span>  
4. <span data-ttu-id="9a01d-127">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9a01d-127">Click Add.</span></span>
    * <span data-ttu-id="9a01d-128">Om du ställer in alternativet Inkludera överordnad regel kommer policyregeln som du definierar för en överordnad kategori också att tilldelas till dess underordnade kategorier, om ingen policyregel har definierats för de underordnade kategorierna.</span><span class="sxs-lookup"><span data-stu-id="9a01d-128">If you set the Include parent rule option to Yes, the policy rule that you define for a parent category is also assigned to its child categories, if no policy rule has been defined for the child categories.</span></span>  
5. <span data-ttu-id="9a01d-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9a01d-129">Click OK.</span></span>

## <a name="create-a-category-policy-rule"></a><span data-ttu-id="9a01d-130">Skapa en kategoripolicyregel</span><span class="sxs-lookup"><span data-stu-id="9a01d-130">Create a category policy rule</span></span>
1. <span data-ttu-id="9a01d-131">Välj Policyregel för kategoriåtkomst</span><span class="sxs-lookup"><span data-stu-id="9a01d-131">Select the Category policy rule</span></span>
    * <span data-ttu-id="9a01d-132">Om knappen Skapa policyregel är nedtonad väljer du den aktiva policyregeln och klickar sedan på Dra tillbaka policyregel.</span><span class="sxs-lookup"><span data-stu-id="9a01d-132">If the Create policy rule button is dimmed, select the active policy rule, and then click Retire policy rule.</span></span>  
2. <span data-ttu-id="9a01d-133">Klicka på Skapa policyregel.</span><span class="sxs-lookup"><span data-stu-id="9a01d-133">Click Create policy rule.</span></span>
3. <span data-ttu-id="9a01d-134">Ange datum och tid i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="9a01d-134">In the Effective date field, enter a date and time.</span></span>
4. <span data-ttu-id="9a01d-135">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9a01d-135">Click Add.</span></span>
5. <span data-ttu-id="9a01d-136">Markera samma kategori som du använde för kategoriåtkomstregeln.</span><span class="sxs-lookup"><span data-stu-id="9a01d-136">Select the same category that you used for the Category access rule.</span></span>
6. <span data-ttu-id="9a01d-137">Välj ett alternativ i fältet Leverantörsurval.</span><span class="sxs-lookup"><span data-stu-id="9a01d-137">In the Vendor selection field, select an option.</span></span>
    * <span data-ttu-id="9a01d-138">Välj en regel för att kontrollera vilken typ av leverantörer som kan väljas för kategorin, när rekvisitioner skapas.</span><span class="sxs-lookup"><span data-stu-id="9a01d-138">Select a rule to control which kind of vendors can be selected for the category when requisitions are created.</span></span>  
7. <span data-ttu-id="9a01d-139">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="9a01d-139">Click Close.</span></span>
    * <span data-ttu-id="9a01d-140">De policyregler som du har definierat har varit för rekvisitioner av typen Förbrukning.</span><span class="sxs-lookup"><span data-stu-id="9a01d-140">The policy rules that you have defined have been for requisitions of type Consumption.</span></span> <span data-ttu-id="9a01d-141">Om du vill definiera policyer för rekvisitioner av typen Återanskaffning, ska du skapa en regel för Policyregeltypen som kallas "Åtkomstpolicyregel för återanskaffningskategori".</span><span class="sxs-lookup"><span data-stu-id="9a01d-141">If you wanted to define policies for requisitions of type Replenishment, you would create a rule for the Policy rule type called “Replenishment category access policy rule”.</span></span>  

