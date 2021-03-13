---
title: Utfall kontra budget Power BI-innehåll
description: Det här avsnittet beskriver Utfall kontra budget Power BI-innehåll. Här förklaras hur du kommer åt rapporterna och ger information om datamodellen.
author: panolte
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 908b96af5b3d67f265953648edd6aa7ec31556a4
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093858"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="29f35-104">Utfall kontra budget Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="29f35-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29f35-105">Det här avsnittet beskriver **Utfall kontra budget** Microsoft Power BI-innehåll.</span><span class="sxs-lookup"><span data-stu-id="29f35-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="29f35-106">Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.</span><span class="sxs-lookup"><span data-stu-id="29f35-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="29f35-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="29f35-107">Overview</span></span>

<span data-ttu-id="29f35-108">**Utfall kontra budget** Power BI-innehållet skapades för personer som ansvarar att övervaka faktiskt kontra budget-prestanda i sina respektive organisationer.</span><span class="sxs-lookup"><span data-stu-id="29f35-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="29f35-109">**Utfall kontra budget** Power BI-innehåll ger insyn i dina budgetavvikelser.</span><span class="sxs-lookup"><span data-stu-id="29f35-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="29f35-110">Du kan analysera budgeten för aktuellt år efter kontokategori, budgetkod, huvudkonto, huvudkontobeskrivningar eller räkenskapsperiod för att få en bättre förståelse för orsaken till eventuella avvikelser.</span><span class="sxs-lookup"><span data-stu-id="29f35-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="29f35-111">Komma åt Power BI-innehåll</span><span class="sxs-lookup"><span data-stu-id="29f35-111">Accessing the Power BI content</span></span>
<span data-ttu-id="29f35-112">Rapporter från **Utfall kontra budget** Power BI-innehåll visas i arbetsytorna **Redovisningsbudget och prognoser** och **Ekonomichef**.</span><span class="sxs-lookup"><span data-stu-id="29f35-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="29f35-113">Rapporter som ingår i Power BI-innehållet</span><span class="sxs-lookup"><span data-stu-id="29f35-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="29f35-114">I följande tabell finns information om mått som finns på varje enskild rapportsida i **Utfall kontra budget** Power BI-innehåll.</span><span class="sxs-lookup"><span data-stu-id="29f35-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="29f35-115">Rapport</span><span class="sxs-lookup"><span data-stu-id="29f35-115">Report</span></span>                      | <span data-ttu-id="29f35-116">Mätvärden</span><span class="sxs-lookup"><span data-stu-id="29f35-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="29f35-117">Utgifter - Utfall kontra budget</span><span class="sxs-lookup"><span data-stu-id="29f35-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="29f35-118">Totala utgifter i år</span><span class="sxs-lookup"><span data-stu-id="29f35-118">Total expenses this year</span></span></li><li><span data-ttu-id="29f35-119">Totala budgetutgifter i år</span><span class="sxs-lookup"><span data-stu-id="29f35-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="29f35-120">Intäkt - utfall kontra budget</span><span class="sxs-lookup"><span data-stu-id="29f35-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="29f35-121">Totala intäkter i år</span><span class="sxs-lookup"><span data-stu-id="29f35-121">Total revenue this year</span></span></li><li><span data-ttu-id="29f35-122">Totala budgetintäkter i år</span><span class="sxs-lookup"><span data-stu-id="29f35-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="29f35-123">Utgift</span><span class="sxs-lookup"><span data-stu-id="29f35-123">Expense</span></span>                     | <ul><li><span data-ttu-id="29f35-124">Totala utgifter i år</span><span class="sxs-lookup"><span data-stu-id="29f35-124">Total expenses this year</span></span></li><li><span data-ttu-id="29f35-125">Målet för utgifter som baseras på budgeten</span><span class="sxs-lookup"><span data-stu-id="29f35-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="29f35-126">Intäkt</span><span class="sxs-lookup"><span data-stu-id="29f35-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="29f35-127">Totala intäkter i år</span><span class="sxs-lookup"><span data-stu-id="29f35-127">Total revenue this year</span></span></li><li><span data-ttu-id="29f35-128">Målet för intäkter som baseras på budgeten</span><span class="sxs-lookup"><span data-stu-id="29f35-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="29f35-129">Nettoinkomst</span><span class="sxs-lookup"><span data-stu-id="29f35-129">Net income</span></span>                  | <ul><li><span data-ttu-id="29f35-130">Nettoinkomst i år</span><span class="sxs-lookup"><span data-stu-id="29f35-130">Net income this year</span></span></li><li><span data-ttu-id="29f35-131">Målet för nettoutgifter som baseras på budgeten</span><span class="sxs-lookup"><span data-stu-id="29f35-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="29f35-132">Förstå datamodellen och enheterna</span><span class="sxs-lookup"><span data-stu-id="29f35-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="29f35-133">Enhet</span><span class="sxs-lookup"><span data-stu-id="29f35-133">Entity</span></span>                    | <span data-ttu-id="29f35-134">Innehåll</span><span class="sxs-lookup"><span data-stu-id="29f35-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="29f35-135">Redovisningsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="29f35-135">General Ledger Activities</span></span> | <span data-ttu-id="29f35-136">Transaktionsbelopp för redovisningen</span><span class="sxs-lookup"><span data-stu-id="29f35-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="29f35-137">Budgetaktiviteter</span><span class="sxs-lookup"><span data-stu-id="29f35-137">Budget Activities</span></span>         | <span data-ttu-id="29f35-138">Transaktionsbelopp för budgetregistret</span><span class="sxs-lookup"><span data-stu-id="29f35-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="29f35-139">Huvudkonton</span><span class="sxs-lookup"><span data-stu-id="29f35-139">Main Accounts</span></span>             | <span data-ttu-id="29f35-140">Huvudkonton att för rapportfiltrering</span><span class="sxs-lookup"><span data-stu-id="29f35-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="29f35-141">Räkenskapskalendrar</span><span class="sxs-lookup"><span data-stu-id="29f35-141">Fiscal Calendars</span></span>          | <span data-ttu-id="29f35-142">Räkenskapskalendrar för rapportfiltrering</span><span class="sxs-lookup"><span data-stu-id="29f35-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="29f35-143">Redovisningar</span><span class="sxs-lookup"><span data-stu-id="29f35-143">Ledgers</span></span>                   | <span data-ttu-id="29f35-144">Redovisningar som kan användas för att filtrera rapporten till den aktuella redovisningen</span><span class="sxs-lookup"><span data-stu-id="29f35-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="29f35-145">Budgetkoder</span><span class="sxs-lookup"><span data-stu-id="29f35-145">Budget Codes</span></span>              | <span data-ttu-id="29f35-146">Budgetkoder att filtrera rapporter efter</span><span class="sxs-lookup"><span data-stu-id="29f35-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="29f35-147">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="29f35-147">Legal Entities</span></span>            | <span data-ttu-id="29f35-148">Juridiska personer som kan användas för att filtrera rapporten till den aktuella juridiska personen</span><span class="sxs-lookup"><span data-stu-id="29f35-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |
