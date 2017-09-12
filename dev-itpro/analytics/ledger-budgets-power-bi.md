---
title: "Faktiskt kontra Power BI-innehåll för budget"
description: "Det här avsnittet beskriver faktiskt Power BI-innehåll kontra Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 6e675ccd610561668dec4f5c7410530edaa122b8
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="0d029-104">Faktiskt kontra Power BI-innehåll för budget</span><span class="sxs-lookup"><span data-stu-id="0d029-104">Actual vs budget Power BI content</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0d029-105">Detta avsnitt beskriver **Faktiskt kontra budget**-Microsoft Power BI-innehåll.</span><span class="sxs-lookup"><span data-stu-id="0d029-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="0d029-106">Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.</span><span class="sxs-lookup"><span data-stu-id="0d029-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span> 

# <a name="overview"></a><span data-ttu-id="0d029-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="0d029-107">Overview</span></span>

<span data-ttu-id="0d029-108">**Faktiskt kontra budget**-Power BI-innehållet skapades för personer som ansvarar att övervaka faktiskt kontra budget-prestanda i sina respektive organisationer.</span><span class="sxs-lookup"><span data-stu-id="0d029-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="0d029-109">**Faktiskt kontra budget**-Power BI-innehåll ger insyn i dina budgetavvikelser.</span><span class="sxs-lookup"><span data-stu-id="0d029-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="0d029-110">Du kan analysera budgeten för aktuellt år efter kontokategori, budgetkod, huvudkonto, huvudkontobeskrivningar eller räkenskapsperiod för att få en bättre förståelse för orsaken till eventuella avvikelser.</span><span class="sxs-lookup"><span data-stu-id="0d029-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span> 

# <a name="accessing-the-power-bi-content"></a><span data-ttu-id="0d029-111">Åtkomst till Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="0d029-111">Accessing the Power BI content</span></span>
<span data-ttu-id="0d029-112">Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (uppdatering juli 2017) visas rapporter från Power BI-innehållet **Faktisk kontra budget** i arbetsytorna **Redovisningsbudget och prognoser** samt **Ekonomichef**.</span><span class="sxs-lookup"><span data-stu-id="0d029-112">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update, reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

# <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="0d029-113">Rapporter som ingår i Power BI-innehållet</span><span class="sxs-lookup"><span data-stu-id="0d029-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="0d029-114">I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **Faktiskt kontra budget**.</span><span class="sxs-lookup"><span data-stu-id="0d029-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="0d029-115">Rapport</span><span class="sxs-lookup"><span data-stu-id="0d029-115">Report</span></span>                      | <span data-ttu-id="0d029-116">Mätvärden</span><span class="sxs-lookup"><span data-stu-id="0d029-116">Metrics</span></span> |
|-----------------------------|---------|
| <span data-ttu-id="0d029-117">Utgifter - Utfall kontra budget</span><span class="sxs-lookup"><span data-stu-id="0d029-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="0d029-118">Totala utgifter i år</span><span class="sxs-lookup"><span data-stu-id="0d029-118">Total expenses this year</span></span></li><li><span data-ttu-id="0d029-119">Totala budgetutgifter i år</span><span class="sxs-lookup"><span data-stu-id="0d029-119">Budget total expenses this year</span></span></li></ul> |
| <span data-ttu-id="0d029-120">Intäkt - utfall kontra budget</span><span class="sxs-lookup"><span data-stu-id="0d029-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="0d029-121">Totala intäkter i år</span><span class="sxs-lookup"><span data-stu-id="0d029-121">Total revenue this year</span></span></li><li><span data-ttu-id="0d029-122">Totala budgetintäkter i år</span><span class="sxs-lookup"><span data-stu-id="0d029-122">Budget total revenue this year</span></span></li><ul> |
| <span data-ttu-id="0d029-123">Utgift</span><span class="sxs-lookup"><span data-stu-id="0d029-123">Expense</span></span>                     | <ul><li><span data-ttu-id="0d029-124">Totala utgifter i år</span><span class="sxs-lookup"><span data-stu-id="0d029-124">Total expenses this year</span></span></li><li><span data-ttu-id="0d029-125">Målet för utgifter som baseras på budgeten</span><span class="sxs-lookup"><span data-stu-id="0d029-125">Goal for expenses based on budget</span></span> </li><ul> |
| <span data-ttu-id="0d029-126">Intäkt</span><span class="sxs-lookup"><span data-stu-id="0d029-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="0d029-127">Totala intäkter i år</span><span class="sxs-lookup"><span data-stu-id="0d029-127">Total revenue this year</span></span></li><li><span data-ttu-id="0d029-128">Målet för intäkter som baseras på budgeten</span><span class="sxs-lookup"><span data-stu-id="0d029-128">Goal for revenue based on budget</span></span> </li><ul> |
| <span data-ttu-id="0d029-129">Nettoinkomst</span><span class="sxs-lookup"><span data-stu-id="0d029-129">Net income</span></span>                  | <ul><li><span data-ttu-id="0d029-130">Nettoinkomst i år</span><span class="sxs-lookup"><span data-stu-id="0d029-130">Net income this year</span></span></li><li><span data-ttu-id="0d029-131">Målet för nettoutgifter som baseras på budgeten</span><span class="sxs-lookup"><span data-stu-id="0d029-131">Goal for net income based on budget</span></span> </li><ul> |

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="0d029-132">Utöka Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="0d029-132">Extending the Power BI content</span></span>
<span data-ttu-id="0d029-133">Genom att använda innehållspaket som är tillgängliga i Microsoft Dynamics Lifecycle Services (LCS) kan du ge bra analyser till människor som inte är inloggade i Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0d029-133">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="0d029-134">Du kan ändra dessa innehållspaket så att de innehåller andra rapporter och modeller och publicera innehållspaket till din Power BI.com-innehavare för analys.</span><span class="sxs-lookup"><span data-stu-id="0d029-134">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="0d029-135">Du hittar Power BI-innehåll för **Faktisk kontra budget** i det delade resursbiblioteket i LCS.</span><span class="sxs-lookup"><span data-stu-id="0d029-135">You can find the **Actual vs budget** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="0d029-136">Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="0d029-136">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="0d029-137">Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.</span><span class="sxs-lookup"><span data-stu-id="0d029-137">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

# <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="0d029-138">Förstå datamodellen och enheterna</span><span class="sxs-lookup"><span data-stu-id="0d029-138">Understanding the data model and entities</span></span>

| <span data-ttu-id="0d029-139">Enhet</span><span class="sxs-lookup"><span data-stu-id="0d029-139">Entity</span></span>                    | <span data-ttu-id="0d029-140">Innehåll</span><span class="sxs-lookup"><span data-stu-id="0d029-140">Contents</span></span> |
|---------------------------|----------|
| <span data-ttu-id="0d029-141">Redovisningsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="0d029-141">General Ledger Activities</span></span> | <span data-ttu-id="0d029-142">Transaktionsbelopp för redovisningen</span><span class="sxs-lookup"><span data-stu-id="0d029-142">Transaction amounts for the general ledger</span></span> |
| <span data-ttu-id="0d029-143">Budgetaktiviteter</span><span class="sxs-lookup"><span data-stu-id="0d029-143">Budget Activities</span></span>         | <span data-ttu-id="0d029-144">Transaktionsbelopp för budgetregistret</span><span class="sxs-lookup"><span data-stu-id="0d029-144">Transaction amounts for the budget register</span></span> |
| <span data-ttu-id="0d029-145">Huvudkonton</span><span class="sxs-lookup"><span data-stu-id="0d029-145">Main Accounts</span></span>             | <span data-ttu-id="0d029-146">Huvudkonton att för rapportfiltrering</span><span class="sxs-lookup"><span data-stu-id="0d029-146">Main accounts to filter reports by</span></span> |
| <span data-ttu-id="0d029-147">Räkenskapskalendrar</span><span class="sxs-lookup"><span data-stu-id="0d029-147">Fiscal Calendars</span></span>          | <span data-ttu-id="0d029-148">Räkenskapskalendrar för rapportfiltrering</span><span class="sxs-lookup"><span data-stu-id="0d029-148">Fiscal calendars to filter reports by</span></span> |
| <span data-ttu-id="0d029-149">Redovisningar</span><span class="sxs-lookup"><span data-stu-id="0d029-149">Ledgers</span></span>                   | <span data-ttu-id="0d029-150">Redovisningar som kan användas för att filtrera rapporten till den aktuella redovisningen</span><span class="sxs-lookup"><span data-stu-id="0d029-150">Ledgers that can be used to filter the report to the current ledger</span></span> |
| <span data-ttu-id="0d029-151">Budgetkoder</span><span class="sxs-lookup"><span data-stu-id="0d029-151">Budget Codes</span></span>              | <span data-ttu-id="0d029-152">Budgetkoder att filtrera rapporter efter</span><span class="sxs-lookup"><span data-stu-id="0d029-152">Budget codes to filter reports by</span></span> |
| <span data-ttu-id="0d029-153">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="0d029-153">Legal Entities</span></span>            | <span data-ttu-id="0d029-154">Juridiska personer som kan användas för att filtrera rapporten till den aktuella juridiska personen</span><span class="sxs-lookup"><span data-stu-id="0d029-154">Legal entities that can be used to filter the report to the current legal entity</span></span> |

