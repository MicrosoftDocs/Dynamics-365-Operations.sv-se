---
title: Skapa och köra färdiga rapporter
description: Använd den här uppgiftsguiden för att köra färdiga rapporter på huvudkontoret från olika arbetsytor och förfrågningar och försäljningsrapporter som finns under Handel.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailCategoryAndProductWorkspace, RetailOrgHierarchyTreeLookup, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f9931a39e4ca2141ed5b43086226c7fcc7cbd7c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024043"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="7190c-103">Skapa och köra färdiga rapporter</span><span class="sxs-lookup"><span data-stu-id="7190c-103">Generate and run out of box reports</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="7190c-104">Använd den här uppgiftsguiden för att köra färdiga rapporter på huvudkontoret från olika arbetsytor och förfrågningar och försäljningsrapporter som finns under Handel.</span><span class="sxs-lookup"><span data-stu-id="7190c-104">Use this task guide to run out of box reports in Headquarters from different workspaces and Inquiries & Sales reports located in Commerce.</span></span>

<span data-ttu-id="7190c-105">Det demonstrationsdataföretag som används för att skapa den här registreringen är USRT.</span><span class="sxs-lookup"><span data-stu-id="7190c-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="7190c-106">Den här registreringen är avsedd för systemadministratörsrollen.</span><span class="sxs-lookup"><span data-stu-id="7190c-106">This recording is intended for the System administrator role.</span></span>

## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="7190c-107">Starta rapporter från arbetsytor</span><span class="sxs-lookup"><span data-stu-id="7190c-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="7190c-108">Gå till Butik och handel > Produkter och kategorier > Kategori- och produkthantering.</span><span class="sxs-lookup"><span data-stu-id="7190c-108">Go to Retail and Commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="7190c-109">Klicka på pilen för att utöka eller komprimera avsnittet Rapporter.</span><span class="sxs-lookup"><span data-stu-id="7190c-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="7190c-110">Klicka på Rapport över topprodukter.</span><span class="sxs-lookup"><span data-stu-id="7190c-110">Click Top products report.</span></span>
4. <span data-ttu-id="7190c-111">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="7190c-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="7190c-112">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="7190c-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="7190c-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kanal.</span><span class="sxs-lookup"><span data-stu-id="7190c-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7190c-114">I trädet, välj Contoso Retail\Contoso Retail USA\Central\Houston.</span><span class="sxs-lookup"><span data-stu-id="7190c-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="7190c-115">Här visas standardorganisationshierarkin för handelrapporteringsyfte.</span><span class="sxs-lookup"><span data-stu-id="7190c-115">This shows the default organization hierarchy for Commerce reporting purpose.</span></span>   <span data-ttu-id="7190c-116">Gå till Organisationsadministration > Organisationer > Syften för organisationshierarki, välj handelsrapportering och under Tilldelade hierarkier, kontrollera det hierarkinamn för vilket standardkolumnen är markerad.</span><span class="sxs-lookup"><span data-stu-id="7190c-116">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="7190c-117">Som en del av demodata (som används för registreringen av den här uppgiften) bör du märka att Butiker efter region är standardorganisationshierarki för syftet med rapportering.</span><span class="sxs-lookup"><span data-stu-id="7190c-117">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
8. <span data-ttu-id="7190c-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7190c-118">Click OK.</span></span>
9. <span data-ttu-id="7190c-119">Markera ett alternativ i fältet Visa.</span><span class="sxs-lookup"><span data-stu-id="7190c-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="7190c-120">Markera ett alternativ i fältet Efter.</span><span class="sxs-lookup"><span data-stu-id="7190c-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="7190c-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7190c-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports"></a><span data-ttu-id="7190c-122">Starta rapporter från förfrågningar och försäljningsrapporter</span><span class="sxs-lookup"><span data-stu-id="7190c-122">Launch reports from the inquiries and sales reports</span></span>
1. <span data-ttu-id="7190c-123">Gå till Butik och handel > Förfrågningar och rapporter > Försäljningsrapporter > Kategoriförsäljning – rapport.</span><span class="sxs-lookup"><span data-stu-id="7190c-123">Go to Retail and Commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="7190c-124">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="7190c-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="7190c-125">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="7190c-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="7190c-126">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kanal.</span><span class="sxs-lookup"><span data-stu-id="7190c-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7190c-127">I trädet, välj Contoso Retail\Contoso Retail USA\West\Seattle.</span><span class="sxs-lookup"><span data-stu-id="7190c-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="7190c-128">Här visas standardorganisationshierarkin för handelrapporteringsyfte.</span><span class="sxs-lookup"><span data-stu-id="7190c-128">This shows the default organization hierarchy for Commerce reporting purpose.</span></span> <span data-ttu-id="7190c-129">Gå till Organisationsadministration > Organisationer > Syften för organisationshierarki, välj handelsrapportering och under Tilldelade hierarkier, kontrollera det hierarkinamn för vilket standardkolumnen är markerad.</span><span class="sxs-lookup"><span data-stu-id="7190c-129">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="7190c-130">Som en del av demodata (som används för registreringen av den här uppgiften) bör du märka att Butiker efter region är standardorganisationshierarki för syftet med rapportering.</span><span class="sxs-lookup"><span data-stu-id="7190c-130">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
6. <span data-ttu-id="7190c-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7190c-131">Click OK.</span></span>
7. <span data-ttu-id="7190c-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7190c-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="7190c-133">Exportera en HQ-rapport</span><span class="sxs-lookup"><span data-stu-id="7190c-133">Export an HQ reports</span></span>
1. <span data-ttu-id="7190c-134">Gå till Butik och handel > Förfrågningar och rapporter > Försäljningsrapporter > Organisationsförsäljning – rapport.</span><span class="sxs-lookup"><span data-stu-id="7190c-134">Go to Retail and Commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="7190c-135">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="7190c-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="7190c-136">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="7190c-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="7190c-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7190c-137">Click OK.</span></span>
5. <span data-ttu-id="7190c-138">Klicka på Exportera.</span><span class="sxs-lookup"><span data-stu-id="7190c-138">Click Export.</span></span>
6. <span data-ttu-id="7190c-139">Klicka på PDF.</span><span class="sxs-lookup"><span data-stu-id="7190c-139">Click PDF.</span></span>

