---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 4 - Kör rapporten)
description: I det här avsnittet beskrivs hur du konfigurerar en elektronisk rapporteringsmodell (ER) för användning av ekonomiska dimensioner som datakälla för ER-rapporter. (Del 4)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a06936da71d7b05f312a99c8c11d148403d29c3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752398"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="69ee5-104">ER Använd ekonomiska dimensioner som en datakälla (Del 4 - Kör rapporten)</span><span class="sxs-lookup"><span data-stu-id="69ee5-104">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69ee5-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="69ee5-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="69ee5-106">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="69ee5-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="69ee5-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 3: Design the report)”.</span><span class="sxs-lookup"><span data-stu-id="69ee5-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="69ee5-108">Du måste även konfigurera förvalda dokumenttyper på sidan för elektroniska rapporteringsparametrar.</span><span class="sxs-lookup"><span data-stu-id="69ee5-108">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="69ee5-109">Förvalda dokumenttyper anges också när du hämtar och importerar en ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="69ee5-109">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="69ee5-110">Kör rapport</span><span class="sxs-lookup"><span data-stu-id="69ee5-110">Run report</span></span>
1. <span data-ttu-id="69ee5-111">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="69ee5-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="69ee5-112">Expandera "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="69ee5-112">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="69ee5-113">Välj "Financial dimensions sample model\Ledger journal report" i trädet.</span><span class="sxs-lookup"><span data-stu-id="69ee5-113">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="69ee5-114">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="69ee5-114">Click Run.</span></span>
<span data-ttu-id="69ee5-115">![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="69ee5-115">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="69ee5-116">Ange eller välj ett värde i namnfältet Dimensions.</span><span class="sxs-lookup"><span data-stu-id="69ee5-116">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="69ee5-117">Ange följande information om du vill välja alla dimensioner i det aktuella företaget: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="69ee5-117">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="69ee5-119">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="69ee5-119">Expand the Records to include section.</span></span>
7. <span data-ttu-id="69ee5-120">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="69ee5-120">Click Filter.</span></span>
8. <span data-ttu-id="69ee5-121">Markera raden för redovisningsjournalregistret (Ledger journal table) och fältet för journalens batchnummer (Journal batch number).</span><span class="sxs-lookup"><span data-stu-id="69ee5-121">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="69ee5-122">Ange "00057" i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="69ee5-122">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="69ee5-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="69ee5-123">Click OK.</span></span>
11. <span data-ttu-id="69ee5-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="69ee5-124">Click OK.</span></span>
<span data-ttu-id="69ee5-125">![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="69ee5-125">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="69ee5-126">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="69ee5-126">Review the generated output.</span></span> <span data-ttu-id="69ee5-127">Ekonomiska dimensioner från den motsvarande dimensioner visas för varje transaktion i den valda batchen.</span><span class="sxs-lookup"><span data-stu-id="69ee5-127">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="69ee5-128">Kör denna rapport och välj olika dimensioner för att se att rapporten inte är beroende av antalet valda dimensioner eller antalet dimensioner som konfigureras för denna instans.</span><span class="sxs-lookup"><span data-stu-id="69ee5-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]