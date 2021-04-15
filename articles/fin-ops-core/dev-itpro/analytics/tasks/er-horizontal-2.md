---
title: ER Använd horisontellt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter (Del 2 - Kör format)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel). (Del 2)
author: NickSelin
ms.date: 08/29/2018
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
ms.openlocfilehash: a62bad6ca241a2372a72e312ec5a707008a5fc09
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744997"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a><span data-ttu-id="7f1d1-104">ER Använd horisontellt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter (Del 2 - Kör format)</span><span class="sxs-lookup"><span data-stu-id="7f1d1-104">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 2 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7f1d1-105">Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att skapa rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="7f1d1-106">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="7f1d1-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren "ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)".</span><span class="sxs-lookup"><span data-stu-id="7f1d1-107">To complete these steps, you must first complete the steps in the "ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)" procedure.</span></span>

<span data-ttu-id="7f1d1-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="7f1d1-109">Sök skapat format</span><span class="sxs-lookup"><span data-stu-id="7f1d1-109">Find created format</span></span>
1. <span data-ttu-id="7f1d1-110">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="7f1d1-111">Expandera "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="7f1d1-112">Välj "Financial dimensions sample model\Sample report with horizontally expandable ranges" i trädet.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-112">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="7f1d1-113">Kör formatet för att skapa Excel-utleverans</span><span class="sxs-lookup"><span data-stu-id="7f1d1-113">Execute format to create Excel output</span></span>
1. <span data-ttu-id="7f1d1-114">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-114">Click Run.</span></span>
2. <span data-ttu-id="7f1d1-115">Ange "BusinessUnit;CostCenter;Department" i fältet Dimensions name.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-115">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="7f1d1-116">Ange eller välj ett värde i namnfältet Dimensions.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-116">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="7f1d1-117">För att välja samtliga dimensioner för aktuellt företag, ange: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="7f1d1-117">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="7f1d1-118">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-118">Expand the Records to include section.</span></span>
4. <span data-ttu-id="7f1d1-119">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-119">Click Filter.</span></span>
5. <span data-ttu-id="7f1d1-120">Markera raden för redovisningsjournalregistret (Ledger journal table) och fältet för journalens batchnummer (Journal batch number).</span><span class="sxs-lookup"><span data-stu-id="7f1d1-120">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="7f1d1-121">Ange "00057..00058" i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-121">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="7f1d1-122">00057..00058</span><span class="sxs-lookup"><span data-stu-id="7f1d1-122">00057..00058</span></span>  
7. <span data-ttu-id="7f1d1-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-123">Click OK.</span></span>
8. <span data-ttu-id="7f1d1-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-124">Click OK.</span></span>
    * <span data-ttu-id="7f1d1-125">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-125">Review the generated output.</span></span> <span data-ttu-id="7f1d1-126">Observera att den nyss skapade Excel-filen innehåller samma antal kolumner som valdes för ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-126">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="7f1d1-127">Rapporthuvudet i dessa kolumner representerar namnen på de ekonomiska dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-127">The report header in those columns represents financial dimensions' names.</span></span> <span data-ttu-id="7f1d1-128">Transaktionsraderna i dessa kolumner representerar ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-128">The transactions' lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="7f1d1-129">Kör denna rapport och välj olika dimensioner för att se att rapporten inte är beroende av antalet valda dimensioner eller antalet dimensioner som konfigureras för denna instans.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-129">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]