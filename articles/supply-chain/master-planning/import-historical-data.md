---
title: "Importera historikdata för efterfrågeprognoser"
description: "För att få korrekta efterfrågeprognoser behöver du historiska efterfrågedata per artikel eller artikelallokeringsnyckel. Det här avsnittet beskriver hur du använder dataenheter för att importera historiska efterfrågedata från valfritt system, så att du får en längre historik över efterfrågeprognosdatan."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 02daa312d74311432c0c468e3e691637dcf94157
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="293ab-104">Importera historikdata för efterfrågeprognoser</span><span class="sxs-lookup"><span data-stu-id="293ab-104">Import historical data for demand forecasts</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="293ab-105">För att garantera att efterfrågeprognoserna blir korrekt måste du ha lika mycket historiska efterfrågeuppgifter som du kan för varje artikel eller artikelallokeringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="293ab-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="293ab-106">Om den historiska begärandedatan inte redan har importerats, använd då dataenheten **Historisk extern begäran** (ReqDemPlanHistoricalExternalDemandEntity) i Microsoft Dynamics 365 for Finance and Operations för att importera den.</span><span class="sxs-lookup"><span data-stu-id="293ab-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Microsoft Dynamics 365 for Finance and Operations to import it.</span></span>

<span data-ttu-id="293ab-107">I arbetsytan **Datahantering** kan du visa en översikt över alla fält i entiteten.</span><span class="sxs-lookup"><span data-stu-id="293ab-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="293ab-108">Öppna arbetsytan **Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="293ab-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="293ab-109">Klicka på fliken **Dataenheter**.</span><span class="sxs-lookup"><span data-stu-id="293ab-109">Click the **Data entities** tile.</span></span>
3. <span data-ttu-id="293ab-110">Sök enhetslistan för **Historisk extern efterfrågan**.</span><span class="sxs-lookup"><span data-stu-id="293ab-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="293ab-111">Klicka på **Målfält**.</span><span class="sxs-lookup"><span data-stu-id="293ab-111">Click **Target fields**.</span></span> <span data-ttu-id="293ab-112">Följande enhetsfält är obligatoriska: webbplats (**DeliveringSiteId**), datum (**DemandDate**), kvantitet (**DemandQuantity**) samt antingen artikelnummer (**ItemNumber**) eller artikelallokeringsnyckel (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="293ab-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="293ab-113">Du måste ha en Microsoft Excel-fil eller kommaseparerade värden (CSV) som innehåller historiska efterfrågeuppgifter data om du vill använda dataenheten.</span><span class="sxs-lookup"><span data-stu-id="293ab-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="293ab-114">I följande exempel visas hur du importerar data från en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="293ab-114">The following example shows how to import the data from a CSV file.</span></span>

## <a name="example"></a><span data-ttu-id="293ab-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="293ab-115">Example</span></span>

<span data-ttu-id="293ab-116">Du kan använda följande fil som exempel.</span><span class="sxs-lookup"><span data-stu-id="293ab-116">You can use the following file as an example.</span></span> <span data-ttu-id="293ab-117">Hämta [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span><span class="sxs-lookup"><span data-stu-id="293ab-117">Download the [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span></span> <span data-ttu-id="293ab-118">Denna fil innehåller historiska efterfrågedata för artikel D0001.</span><span class="sxs-lookup"><span data-stu-id="293ab-118">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="293ab-119">Den innehåller endast följande obligatoriska fält: webbplats, kvantitet och efterfrågedatum.</span><span class="sxs-lookup"><span data-stu-id="293ab-119">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="293ab-120">Välj det företag som du vill importera de historiska efterfrågeuppgifterna till.</span><span class="sxs-lookup"><span data-stu-id="293ab-120">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="293ab-121">Öppna arbetsytan **Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="293ab-121">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="293ab-122">Klicka på fliken **Importera**.</span><span class="sxs-lookup"><span data-stu-id="293ab-122">Click the **Import** tile.</span></span>
4. <span data-ttu-id="293ab-123">Namnge importprojektet, exempelvis **Importera historisk efterfrågan för artikeln D0001**.</span><span class="sxs-lookup"><span data-stu-id="293ab-123">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="293ab-124">I fältet **Källdataformat** väljer du filformat för den fil som du importerar.</span><span class="sxs-lookup"><span data-stu-id="293ab-124">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="293ab-125">Om du vill importera filen HistoricalDemandData i det här exemplet väljer du **CSV**.</span><span class="sxs-lookup"><span data-stu-id="293ab-125">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="293ab-126">I fältet **Enhetsnamn** väljer du **Historisk extern efterfrågan**.</span><span class="sxs-lookup"><span data-stu-id="293ab-126">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="293ab-127">Spara filen på din dator och överför den sedan.</span><span class="sxs-lookup"><span data-stu-id="293ab-127">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="293ab-128">Klicka på **Importera**.</span><span class="sxs-lookup"><span data-stu-id="293ab-128">Click **Import**.</span></span>
9. <span data-ttu-id="293ab-129">Sidan **Utförandesummering** öppnas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="293ab-129">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="293ab-130">Kontrollera den importerade informationen på sidan.</span><span class="sxs-lookup"><span data-stu-id="293ab-130">Verify the imported data on the page.</span></span>

<span data-ttu-id="293ab-131">När du har importerat efterfrågehistoriken kan du skapa en efterfrågeprognos.</span><span class="sxs-lookup"><span data-stu-id="293ab-131">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="see-also"></a><span data-ttu-id="293ab-132">Se även</span><span class="sxs-lookup"><span data-stu-id="293ab-132">See also</span></span>

[<span data-ttu-id="293ab-133">Generera en statistisk baslinjeprognos</span><span class="sxs-lookup"><span data-stu-id="293ab-133">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)

