---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 4 - Kör rapporten)
description: I det här avsnittet beskrivs hur du konfigurerar en elektronisk rapporteringsmodell (ER) för användning av ekonomiska dimensioner som datakälla för ER-rapporter. (Del 4)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1fe332de84339d3369ba495ca13f50c4901f366
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092285"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="90346-104">ER Använd ekonomiska dimensioner som en datakälla (Del 4 - Kör rapporten)</span><span class="sxs-lookup"><span data-stu-id="90346-104">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="90346-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="90346-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="90346-106">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="90346-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="90346-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 3: Design the report)”.</span><span class="sxs-lookup"><span data-stu-id="90346-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="90346-108">Du måste även konfigurera förvalda dokumenttyper på sidan för elektroniska rapporteringsparametrar.</span><span class="sxs-lookup"><span data-stu-id="90346-108">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="90346-109">Förvalda dokumenttyper anges också när du hämtar och importerar en ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="90346-109">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="90346-110">Kör rapport</span><span class="sxs-lookup"><span data-stu-id="90346-110">Run report</span></span>
1. <span data-ttu-id="90346-111">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="90346-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="90346-112">Expandera "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="90346-112">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="90346-113">Välj "Financial dimensions sample model\Ledger journal report" i trädet.</span><span class="sxs-lookup"><span data-stu-id="90346-113">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="90346-114">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="90346-114">Click Run.</span></span>
<span data-ttu-id="90346-115">![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="90346-115">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="90346-116">Ange eller välj ett värde i namnfältet Dimensions.</span><span class="sxs-lookup"><span data-stu-id="90346-116">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="90346-117">Ange följande information om du vill välja alla dimensioner i det aktuella företaget: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="90346-117">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="90346-119">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="90346-119">Expand the Records to include section.</span></span>
7. <span data-ttu-id="90346-120">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="90346-120">Click Filter.</span></span>
8. <span data-ttu-id="90346-121">Markera raden för redovisningsjournalregistret (Ledger journal table) och fältet för journalens batchnummer (Journal batch number).</span><span class="sxs-lookup"><span data-stu-id="90346-121">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="90346-122">Ange "00057" i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="90346-122">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="90346-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="90346-123">Click OK.</span></span>
11. <span data-ttu-id="90346-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="90346-124">Click OK.</span></span>
<span data-ttu-id="90346-125">![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="90346-125">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="90346-126">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="90346-126">Review the generated output.</span></span> <span data-ttu-id="90346-127">Ekonomiska dimensioner från den motsvarande dimensioner visas för varje transaktion i den valda batchen.</span><span class="sxs-lookup"><span data-stu-id="90346-127">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="90346-128">Kör denna rapport och välj olika dimensioner för att se att rapporten inte är beroende av antalet valda dimensioner eller antalet dimensioner som konfigureras för denna instans.</span><span class="sxs-lookup"><span data-stu-id="90346-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run4.png)
