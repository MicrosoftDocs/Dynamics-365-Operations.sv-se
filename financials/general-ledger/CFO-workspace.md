---
title: "Lägg till ekonomiska dimensioner i arbetsyta för ekonomichef"
description: "Det här avsnittet beskriver hur du lägger till ekonomiska dimensioner till arbetsytan ekonomichef så att den kan användas för redovisnings- och budgettransaktionerna."
author: aolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.2.0
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 05fd7ce5293b3a300aabc073a6e492c5804d1897
ms.contentlocale: sv-se
ms.lasthandoff: 08/03/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="60585-103">Lägg till ekonomiska dimensioner i arbetsyta för ekonomichef</span><span class="sxs-lookup"><span data-stu-id="60585-103">Add financial dimensions to the CFO workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="60585-104">Det här avsnittet beskriver hur du lägger till ekonomiska dimensioner till arbetsytan för ekonomichef så att den kan användas för redovisnings- och budgettransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="60585-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="60585-105">Arbetsytan för ekonomichef har fliken **översikt** och fliken **ekonomi**.</span><span class="sxs-lookup"><span data-stu-id="60585-105">The CFO workspace has an **Overview** tab and a **Financial** tab.</span></span> <span data-ttu-id="60585-106">Rapporterna om dessa två flikar stöds av två mått: LedgerActivityMeasure och BudgetActivityMeasure.</span><span class="sxs-lookup"><span data-stu-id="60585-106">The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="60585-107">I Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, uppdatering juli 2017 finns en relation mellan dessa två mått och entiteten DimensionCombinationEntity.</span><span class="sxs-lookup"><span data-stu-id="60585-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update, there is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="60585-108">Därför kan du välja dimensioner.</span><span class="sxs-lookup"><span data-stu-id="60585-108">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="60585-109">I Finance and Operations på sidan **Entitetsbutiken** kan du uppdatera måtten **LedgerActivityMeasure** och **BudgetActivityMeasure**.</span><span class="sxs-lookup"><span data-stu-id="60585-109">In Finance and Operations, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="60585-110">Öppna Programutforskaren i Microsoft Visual Studio och sök efter **LedgerCFO**.</span><span class="sxs-lookup"><span data-stu-id="60585-110">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="60585-111">Under **resurser** öppnar du **LedgerCFOWorkspacePBIX**.</span><span class="sxs-lookup"><span data-stu-id="60585-111">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="60585-112">När resursen öppnas i desktop Microsoft Power BI Desktop väljer du **hämta data**, väljer **SQL Server-databas** och väljer sedan **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="60585-112">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="60585-113">Ange servernamn och ange **AxDW** som databasen.</span><span class="sxs-lookup"><span data-stu-id="60585-113">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="60585-114">Välj **DirectQuery** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="60585-114">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="60585-115">Leta upp och markera **LedgerActivityMeasure\_DimensionCombination**, och välj sedan **lasta**.</span><span class="sxs-lookup"><span data-stu-id="60585-115">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="60585-116">I listan **fält** byter du namn på tabellen **ekonomiska dimensioner**, så att den blir lätt att identifiera.</span><span class="sxs-lookup"><span data-stu-id="60585-116">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="60585-117">Välj **hantera relationer**, och välj sedan **ny**.</span><span class="sxs-lookup"><span data-stu-id="60585-117">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="60585-118">I första fältet väljer du **redovisningsaktiviteter**, och väljer sedan **LedgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="60585-118">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="60585-119">I det andra fältet väljer du **LedgerActivityMeasure\_DimensionCombination** (eller **ekonomiska dimensioner** om du byter namn på tabellen).</span><span class="sxs-lookup"><span data-stu-id="60585-119">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="60585-120">Välj rubriken **DimensionCombinationRECID**.</span><span class="sxs-lookup"><span data-stu-id="60585-120">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="60585-121">I fältet **kardinalitet** väljer du **många till en**.</span><span class="sxs-lookup"><span data-stu-id="60585-121">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="60585-122">Ändra värdet **Korsfilterriktning** till **enkel**.</span><span class="sxs-lookup"><span data-stu-id="60585-122">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="60585-123">Markera både **aktivera den här relationen** och **anta referensintegritet**, markera **OK**, och välj sedan **nära**.</span><span class="sxs-lookup"><span data-stu-id="60585-123">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="60585-124">[![Skapa en relation](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="60585-124">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="60585-125">I listan **fält** bör du se tabellen och de ekonomiska dimensionerna som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="60585-125">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="60585-126">Dra de ekonomiska dimensioner som du vill använda till rapportnivåfilter.</span><span class="sxs-lookup"><span data-stu-id="60585-126">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="60585-127">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="60585-127">Save your changes.</span></span>
15. <span data-ttu-id="60585-128">Högerklicka på projektet i programobjektträdet (AOT) och välj sedan **synkronisera**.</span><span class="sxs-lookup"><span data-stu-id="60585-128">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="60585-129">Bygg ditt projekt och öppna sedan programmet för att visa resultaten.</span><span class="sxs-lookup"><span data-stu-id="60585-129">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="60585-130">[![Slutförd arbetsyta](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="60585-130">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>

