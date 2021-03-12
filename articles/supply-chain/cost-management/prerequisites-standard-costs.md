---
title: Krav för översikt över standardkostnader
description: I detta avsnitt beskrivs hur du använder standardkostnader.
author: AndersGirke
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9333bda96ceae378ab74892534db13761038a06c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967368"
---
# <a name="prerequisites-for-standard-costs-overview"></a><span data-ttu-id="8b9f3-103">Krav för översikt över standardkostnader</span><span class="sxs-lookup"><span data-stu-id="8b9f3-103">Prerequisites for standard costs overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8b9f3-104">I detta avsnitt beskrivs hur du använder standardkostnader.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-104">This topic describes the basic steps for using standard costs.</span></span> <span data-ttu-id="8b9f3-105">Efterföljande steg beror på företagets verksamhet.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-105">Subsequent steps depend on the company's operations.</span></span> <span data-ttu-id="8b9f3-106">Vilka steg som ska användas skiljer sig beroende på företagets verksamhet, till exempel om det är en miljö utan tillverkning, en tillverkningsmiljö utan flöden eller en tillverkningsmiljö med flöden.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-106">For example, the steps differ for a nonmanufacturing environment, a manufacturing environment that doesn't use routings, and a manufacturing environment that uses routings.</span></span> 

<span data-ttu-id="8b9f3-107">Så här ställer du in standardkostnader.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-107">To set up standard costs, follow these steps.</span></span>

<span data-ttu-id="8b9f3-108">**1. Skapa en artikelmodellgrupp för standardkostnader.**</span><span class="sxs-lookup"><span data-stu-id="8b9f3-108">**1. Create an item model group for standard costs.**</span></span>

<span data-ttu-id="8b9f3-109">Använd **artikelmodellgruppen** om du vill skapa en ny grupp för standardkostnader och tilldela lagermodellen **standardkostnad**.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-109">Use the **Item model groups** page to create a new group for standard costs, and assign an inventory model of **Standard cost**.</span></span> <span data-ttu-id="8b9f3-110">Artikelmodellgruppens ID ska ha en innebörd, till exempel **Stdkost**.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-110">The identifier for the item model group should be meaningful, such as **Std Cost**.</span></span> <span data-ttu-id="8b9f3-111">Markera kryssrutorna om du vill ange att gruppen ska tillåta ekonomiskt negativt lager och att den ska bokföra fysiskt lager och ekonomiskt lager.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-111">Select the check boxes to indicate that the group should allow financial negative inventory, and that it should post physical inventory and financial inventory.</span></span> <span data-ttu-id="8b9f3-112">Denna standardkostnadsgrupp tilldelas artiklar.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-112">This standard cost group will be assigned to items.</span></span>

<span data-ttu-id="8b9f3-113">**2. Definiera redovisningskonton som hör till standardkostnadsavvikelser.**</span><span class="sxs-lookup"><span data-stu-id="8b9f3-113">**2. Define ledger accounts that are related to standard cost variances.**</span></span> 

<span data-ttu-id="8b9f3-114">Använd sidan **Kontoplan** om du vill definiera huvudbokskonton som hör till standardkostnadsavvikelser.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-114">Use the **Chart of accounts** page to define ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="8b9f3-115">Dessa huvudbokskonton måste definieras innan de kan tilldelas på sidan **Posting**.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-115">These ledger accounts must be defined before they can be assigned on the **Posting** page.</span></span> <span data-ttu-id="8b9f3-116">Redovisningskontona kan återspegla artikelgrupper och kostnadsgrupper.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-116">The ledger accounts can reflect item groups and cost groups.</span></span>

<span data-ttu-id="8b9f3-117">**3. Tilldela huvudbokskonton till artikelbokföringar som hör till standardkostnadsavvikelser.**</span><span class="sxs-lookup"><span data-stu-id="8b9f3-117">**3. Assign ledger accounts to item postings that are related to standard cost variances.**</span></span> 

<span data-ttu-id="8b9f3-118">Använd sidan **Posting** om du vill tilldela huvudbokskonton som hör till standardkostnadsavvikelser.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-118">Use the **Posting** page to assign the ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="8b9f3-119">Du kan välja om du vill ange en avvikelses redovisningskonto per artikel (eller artikelgrupp) och per kostnadsgrupp (eller kostnadsgruppstyp), eller specificera att redovisningskontot gäller för alla artiklar och alla kostnadsgrupper.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-119">You can specify a variance's ledger account by item (or item group) and by cost group (or cost group type), or you can specify that the ledger account applies to all items and all cost groups.</span></span> <span data-ttu-id="8b9f3-120">Dessa val motsvarar kostnadsrelationer för tabeller, grupper och allt.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-120">These options correspond to cost relations for tables, groups, and all.</span></span> 

<span data-ttu-id="8b9f3-121">Använd sidan **Transaktionskombinationer** om vill du göra det möjligt att använda kostnadsrelationer (för tabeller, grupper och allt) innan du definierar artikelbokföringsregler.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-121">Before you define the item posting rules, use the **Transaction combinations** page to enable cost relations (for tables, groups, and all).</span></span>

<span data-ttu-id="8b9f3-122">**4. Definiera lagerparametrar som hör till standardkostnader.**</span><span class="sxs-lookup"><span data-stu-id="8b9f3-122">**4. Define inventory parameters that are related to standard costs.**</span></span> 

-  <span data-ttu-id="8b9f3-123">Använd fliken **Lagerredovisning** på sidan **Lagerredovisningsparametrar** om du vill definiera två kontrollparametrar som hör till standardkostnader.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-123">Use the **Inventory accounting** tab on the **Inventory accounting policies setup > Parameters** page to define two cost control parameters that are related to standard costs.</span></span>

    -  <span data-ttu-id="8b9f3-124">I fältet **Kostnadsuppdelning** välj **Inga** eller **Delredovisning**.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-124">In the **Cost breakdown** field, select **None** or **Sub ledger**.</span></span> <span data-ttu-id="8b9f3-125">Om du väljer **Delredovisning** är kostnadsuppdelningen *aktiv*.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-125">If you select **Sub ledger**, the cost breakdown is an *active* cost breakdown.</span></span> <span data-ttu-id="8b9f3-126">En aktiv kostnadsuppdelning har stor betydelse när du beräknar, behåller och visar kostnadsgruppssegmentering över en produktstruktur i flera nivåer för standardkostnadsartiklar.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-126">An active cost breakdown is critical for calculating, retaining, and viewing cost group segmentation across a multilevel product structure for standard cost items.</span></span> <span data-ttu-id="8b9f3-127">När kostnadsuppdelningen är aktiv kan du rapportera och analysera lager, produkter i arbete (PIA) och kostnader för sålda varor (COGS) per kostnadsgrupp på en enda nivå, flera nivåer eller i totalformat.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-127">When the cost breakdown is active, you can report and analyze inventory, work in process (WIP), and cost of goods sold (COGS) per cost group in a single-level, multilevel, or total format.</span></span> <span data-ttu-id="8b9f3-128">Om kostnadsuppdelningen är aktiv och du också aktiverar en tillverkad artikels kostnad kommer kostnadsgruppssegmenteringen att lagras i artikelns kostnadspost.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-128">When the cost breakdown is active, if you activate a manufactured item's cost, the cost group segmentation will be stored in the item's cost record.</span></span> 

    -  <span data-ttu-id="8b9f3-129">Om du väljer **ingen** underhålls inte kostnadsgruppssegmenteringen för standardkostnadsartiklar.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-129">If you select **None**, cost group segmentation won't be maintained for standard cost items.</span></span> <span data-ttu-id="8b9f3-130">Med andra ord beräknas och underhålls en tillverkad artikels standardkostnad som ett enskilt belopp, utan kostnadsgruppssegmentering.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-130">In other words, a manufactured item's standard cost will be calculated and maintained as a single amount, without cost group segmentation.</span></span> <span data-ttu-id="8b9f3-131">Kostnadsbidragen från tillverkade komponenter aggregeras till ett enda belopp.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-131">The cost contributions of manufactured components will be aggregated into the single amount.</span></span>

-  <span data-ttu-id="8b9f3-132">Använd fältet **Avvikelser från standard** välj **Summerat** eller **Per kostnadsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-132">In the **Variances to standard** field, select **Summarized** or **Per cost group**.</span></span> <span data-ttu-id="8b9f3-133">Om du väljer **Per kostnadsgrupp** kan du identifiera inköpsprisavvikelser och produktionsavvikelser per kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-133">If you select **Per cost group**, you can identify purchase price variances and production variances by cost group.</span></span> <span data-ttu-id="8b9f3-134">Du kan även identifiera fyra typer av produktionsavvikelser: partistorlek, kvantitet, pris och ersättning.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-134">You can also identify the four types of production variances: the lot size, quantity, price, and substitution variances.</span></span> <span data-ttu-id="8b9f3-135">Om du väljer **summerad** kan du inte identifiera avvikelser per kostnadsgrupp, och du kan inte identifiera de fyra typerna av produktionsavvikelse.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-135">If you select **Summarized**, you can't identify variances by cost group, and you can't identify the four types of production variances.</span></span> <span data-ttu-id="8b9f3-136">Du kan endast visa en summerad produktionsavvikelse.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-136">You can just view a summarized production variance.</span></span>

-  <span data-ttu-id="8b9f3-137">Principen om avvikelse från standarden fungerar oberoende av kostnadsuppdelningsprincipen.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-137">The policy about variance to standard works independently of the cost breakdown policy.</span></span> <span data-ttu-id="8b9f3-138">Med andra ord innebär det att du kan välja en kostnadsuppdelningsprincip som är **ingen**, och välja avvikelser per kostnadsgrupp, så att produktionsavvikelser per kostnadsgrupp ändå kan fångas in.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-138">In other words, you can select a cost breakdown policy of **None** and select variances per cost group, so that production variances by cost group will still be captured.</span></span>

<span data-ttu-id="8b9f3-139">**5. Skapa kostnadsversioner för standardkostnader.**</span><span class="sxs-lookup"><span data-stu-id="8b9f3-139">**5. Create costing versions for standard costs.**</span></span> 

<span data-ttu-id="8b9f3-140">Använd sidan **Inställningar för kostnadsredovisningsversion** om du vill skapa en eller flera kostnadsversioner för standardkostnader.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-140">Use the **Costing version setup** page to create one or more costing versions for standard costs.</span></span> <span data-ttu-id="8b9f3-141">Varje kostnadsversion måste betecknas med en kostnadstyp för **standardkostnader** och måste tillåta att innehåll omfattar kostnadsdata.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-141">Each costing version must be designated by a costing type of **Standard cost** and must allow content to include cost data.</span></span>

<span data-ttu-id="8b9f3-142">**6. Förbered en befintlig -kund på att använda standardkostnader.**</span><span class="sxs-lookup"><span data-stu-id="8b9f3-142">**6. Prepare an existing customer to use standard costs.**</span></span> 

<span data-ttu-id="8b9f3-143">Kunder som vill ändra sina befintliga artiklar till lagermodellen Standardkostnad måste använda sidan **Konverteringar av standardkostnad**.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-143">Customers who want to change their existing items to a standard cost inventory model must use the **Standard cost conversions** page.</span></span>


<a name="related-topics"></a><span data-ttu-id="8b9f3-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8b9f3-144">Related topics</span></span>
--------

[<span data-ttu-id="8b9f3-145">Standardkostnadskonvertering – översikt</span><span class="sxs-lookup"><span data-stu-id="8b9f3-145">Standard cost conversion overview</span></span>](standard-cost-conversion-overview.md)

### <a name="blogs"></a><span data-ttu-id="8b9f3-146">Bloggar</span><span class="sxs-lookup"><span data-stu-id="8b9f3-146">Blogs</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="8b9f3-147">Bloggar</span><span class="sxs-lookup"><span data-stu-id="8b9f3-147">Community blogs</span></span>

- [<span data-ttu-id="8b9f3-148">Så här ställer du in standardkostnader för direkt material i Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8b9f3-148">How to set up standard costs for direct materials in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [<span data-ttu-id="8b9f3-149">Direkta standardarbetskostnader i Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8b9f3-149">Standard direct labor costs in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)
