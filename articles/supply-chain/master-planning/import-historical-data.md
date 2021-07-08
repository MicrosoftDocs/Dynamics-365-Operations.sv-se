---
title: Importera historikdata för efterfrågeprognoser
description: För att få korrekta efterfrågeprognoser behöver du historiska efterfrågedata per artikel eller artikelallokeringsnyckel. Det här avsnittet beskriver hur du använder dataenheter för att importera historiska efterfrågedata från valfritt system, så att du får en längre historik över efterfrågeprognosdatan.
author: roxanadiaconu
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b04ee246d4c28e934407ccb92d792692cc4347d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301660"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="c5bd8-104">Importera historikdata för efterfrågeprognoser</span><span class="sxs-lookup"><span data-stu-id="c5bd8-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5bd8-105">För att garantera att efterfrågeprognoserna blir korrekt måste du ha lika mycket historiska efterfrågeuppgifter som du kan för varje artikel eller artikelallokeringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="c5bd8-106">Om den historiska efterfrågedatan inte redan har importerats, använd då dataenheten **Historisk extern efterfrågan** (ReqDemPlanHistoricalExternalDemandEntity) i Dynamics 365 Supply Chain Management för att importera den.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="c5bd8-107">I arbetsytan **Datahantering** kan du visa en översikt över alla fält i entiteten.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="c5bd8-108">Öppna arbetsytan **Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="c5bd8-109">Klicka på fliken **Dataenheter**.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="c5bd8-110">Sök enhetslistan för **Historisk extern efterfrågan**.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="c5bd8-111">Välj **målfält**.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-111">Select **Target fields**.</span></span> <span data-ttu-id="c5bd8-112">Följande enhetsfält är obligatoriska: webbplats (**DeliveringSiteId**), datum (**DemandDate**), kvantitet (**DemandQuantity**) samt antingen artikelnummer (**ItemNumber**) eller artikelallokeringsnyckel (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="c5bd8-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="c5bd8-113">Du måste ha en Microsoft Excel-fil eller kommaseparerade värden (CSV) som innehåller historiska efterfrågeuppgifter data om du vill använda dataenheten.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="c5bd8-114">I följande exempel visas hur du importerar data från en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="c5bd8-115">Mer information om hur du importerar data, bland annat hur du rensar data efter en import, finns i [Översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) samt relaterade ämnen.</span><span class="sxs-lookup"><span data-stu-id="c5bd8-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

<span data-ttu-id="c5bd8-116">Se [Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md).</span><span class="sxs-lookup"><span data-stu-id="c5bd8-116">See also [Generate a statistical baseline forecast](generate-statistical-baseline-forecast.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]