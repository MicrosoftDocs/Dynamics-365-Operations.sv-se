---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 4 - Kör rapporten)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 917eae141bbb8792f02d3323054e2a4096dae551
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544666"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4-run-the-report"></a><span data-ttu-id="d24fc-103">ER Använd ekonomiska dimensioner som en datakälla (Del 4: Kör rapporten)</span><span class="sxs-lookup"><span data-stu-id="d24fc-103">ER Use financial dimensions as a data source (Part 4: Run the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d24fc-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="d24fc-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="d24fc-105">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="d24fc-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="d24fc-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 3: Design the report)”.</span><span class="sxs-lookup"><span data-stu-id="d24fc-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="d24fc-107">Du måste även konfigurera förvalda dokumenttyper på sidan för elektroniska rapporteringsparametrar.</span><span class="sxs-lookup"><span data-stu-id="d24fc-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="d24fc-108">Förvalda dokumenttyper anges också när du hämtar och importerar en ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d24fc-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="d24fc-109">Kör rapport</span><span class="sxs-lookup"><span data-stu-id="d24fc-109">Run report</span></span>
1. <span data-ttu-id="d24fc-110">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="d24fc-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="d24fc-111">Expandera "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="d24fc-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="d24fc-112">Välj "Financial dimensions sample model\Ledger journal report" i trädet.</span><span class="sxs-lookup"><span data-stu-id="d24fc-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="d24fc-113">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="d24fc-113">Click Run.</span></span>
5. <span data-ttu-id="d24fc-114">Ange eller välj ett värde i fältet Dimension name.</span><span class="sxs-lookup"><span data-stu-id="d24fc-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="d24fc-115">Ange följande om du vill välja alla dimensioner i det aktuella företaget: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="d24fc-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="d24fc-116">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="d24fc-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="d24fc-117">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="d24fc-117">Click Filter.</span></span>
8. <span data-ttu-id="d24fc-118">Markera raden för redovisningsjournalregistret (Ledger journal table) och fältet för journalens batchnummer (Journal batch number).</span><span class="sxs-lookup"><span data-stu-id="d24fc-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="d24fc-119">Ange "00057" i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="d24fc-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="d24fc-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d24fc-120">Click OK.</span></span>
11. <span data-ttu-id="d24fc-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d24fc-121">Click OK.</span></span>
    * <span data-ttu-id="d24fc-122">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="d24fc-122">Review the generated output.</span></span> <span data-ttu-id="d24fc-123">Notera att ekonomiska dimensioner från den motsvarande dimensioner visas för varje transaktion i den valda batchen.</span><span class="sxs-lookup"><span data-stu-id="d24fc-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="d24fc-124">Kör denna rapport och välj olika dimensioner för att se att rapporten inte är beroende av antalet valda dimensioner eller antalet dimensioner som konfigureras för denna Dynamics 365 for Finance and Operations, Enterprise Edition-instans.</span><span class="sxs-lookup"><span data-stu-id="d24fc-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  

