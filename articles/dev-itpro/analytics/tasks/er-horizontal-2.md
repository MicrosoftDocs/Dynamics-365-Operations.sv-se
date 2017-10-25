--- 
title: "Kör ett format som använder horisontellt expanderbara intervall för att lägga till kolumner dynamiskt i Excel-rapporter för elektronisk rapportering (ER)"
description: "Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8e5c53905b903bc5242625283f3b093144243cf9
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="run-a-format-that-uses-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a><span data-ttu-id="4baa5-103">Kör ett format som använder horisontellt expanderbara intervall för att lägga till kolumner dynamiskt i Excel-rapporter för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="4baa5-103">Run a format that uses horizontally-expandable ranges to dynamically add columns in Excel reports for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4baa5-104">Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall.</span><span class="sxs-lookup"><span data-stu-id="4baa5-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="4baa5-105">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="4baa5-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="4baa5-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren "ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)".</span><span class="sxs-lookup"><span data-stu-id="4baa5-106">To complete these steps, you must first complete the steps in the “ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)” procedure.</span></span>

<span data-ttu-id="4baa5-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="4baa5-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="4baa5-108">Sök skapat format</span><span class="sxs-lookup"><span data-stu-id="4baa5-108">Find created format</span></span>
1. <span data-ttu-id="4baa5-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="4baa5-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="4baa5-110">Expandera "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="4baa5-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="4baa5-111">Välj "Financial dimensions sample model\Sample report with horizontally expandable ranges" i trädet.</span><span class="sxs-lookup"><span data-stu-id="4baa5-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="4baa5-112">Kör formatet för att skapa Excel-utleverans</span><span class="sxs-lookup"><span data-stu-id="4baa5-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="4baa5-113">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="4baa5-113">Click Run.</span></span>
2. <span data-ttu-id="4baa5-114">Ange "BusinessUnit;CostCenter;Department" i fältet Dimensions name.</span><span class="sxs-lookup"><span data-stu-id="4baa5-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="4baa5-115">Ange eller välj ett värde i namnfältet Dimensions.</span><span class="sxs-lookup"><span data-stu-id="4baa5-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="4baa5-116">För att välja samtliga dimensioner för aktuellt företag, ange: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="4baa5-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="4baa5-117">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="4baa5-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="4baa5-118">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="4baa5-118">Click Filter.</span></span>
5. <span data-ttu-id="4baa5-119">Markera raden för redovisningsjournalregistret (Ledger journal table) och fältet för journalens batchnummer (Journal batch number).</span><span class="sxs-lookup"><span data-stu-id="4baa5-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="4baa5-120">Ange "00057..00058" i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="4baa5-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="4baa5-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="4baa5-121">00057..00058</span></span>  
7. <span data-ttu-id="4baa5-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4baa5-122">Click OK.</span></span>
8. <span data-ttu-id="4baa5-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4baa5-123">Click OK.</span></span>
    * <span data-ttu-id="4baa5-124">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="4baa5-124">Review the generated output.</span></span> <span data-ttu-id="4baa5-125">Observera att den nyss skapade Excel-filen innehåller samma antal kolumner som valdes för ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="4baa5-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="4baa5-126">Rapporthuvudet i dessa kolumner representerar namnen på de ekonomiska dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="4baa5-126">The report header in those columns represents financial dimensions’ names.</span></span> <span data-ttu-id="4baa5-127">Transaktionsraderna i dessa kolumner representerar ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="4baa5-127">The transactions’ lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="4baa5-128">Kör denna rapport och välj olika dimensioner för att se att rapporten inte är beroende av antalet valda dimensioner eller antalet dimensioner som konfigureras för denna Dynamics 365 for Finance and Operations, Enterprise edition-instans.</span><span class="sxs-lookup"><span data-stu-id="4baa5-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  

