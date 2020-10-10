---
title: Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos
description: Den här artikeln beskriver hur du utesluter avskilda från historiska data som används för att beräkna en efterfrågeprognos. Genom att exkludera avskilda kan du förbättra prognosexaktheten.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a44be713a1049e90618392d028c81e974841b348
ms.sourcegitcommit: cde71bc7d14ea6cdff2c4e991057d39a6a0473d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2020
ms.locfileid: "3886833"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="2e237-104">Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos</span><span class="sxs-lookup"><span data-stu-id="2e237-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e237-105">Den här artikeln beskriver hur du utesluter avskilda från historiska data som används för att beräkna en efterfrågeprognos.</span><span class="sxs-lookup"><span data-stu-id="2e237-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="2e237-106">Genom att exkludera avskilda kan du förbättra prognosexaktheten.</span><span class="sxs-lookup"><span data-stu-id="2e237-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="2e237-107">Du kan exkludera avvikare för att förbättra prognosexaktheten.</span><span class="sxs-lookup"><span data-stu-id="2e237-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="2e237-108">Den här uppgiften är valfri.</span><span class="sxs-lookup"><span data-stu-id="2e237-108">This is an optional task.</span></span> <span data-ttu-id="2e237-109">Här finns en översikt av processen:</span><span class="sxs-lookup"><span data-stu-id="2e237-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="2e237-110">Klicka på **Huvudplanering** &gt; **Inställningar** &gt; **Efterfrågeprognosticering** &gt; **Borttagning av avskild** för att öppna sidan **Borttagning av avskild** där du kan använda en fråga för att välja transaktionerna som ska undantas.</span><span class="sxs-lookup"><span data-stu-id="2e237-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="2e237-111">Välj vilket företag som frågan gäller och ange sedan ett namn och en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2e237-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="2e237-112">Fältet **Frågedatum** ställs automatiskt in på aktuellt datum.</span><span class="sxs-lookup"><span data-stu-id="2e237-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="2e237-113">Markera kryssrutan **Aktiv** om du vill exkludera transaktionerna som hittas av frågan från historiska data.</span><span class="sxs-lookup"><span data-stu-id="2e237-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="2e237-114">Den här inställningen ska börja gälla när du skapar en baslinjeprognos.</span><span class="sxs-lookup"><span data-stu-id="2e237-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="2e237-115">På sidan **Fråga för borttagning av avskild** kan du lägga till, ta bort och välja kriterier som definierar vilka transaktioner som ska utelämnas när baslinjeprognosen beräknas.</span><span class="sxs-lookup"><span data-stu-id="2e237-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="2e237-116">Välj till exempel en viss artikel eller ordertransaktion som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="2e237-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="2e237-117">Klicka på **Visa transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="2e237-117">Click **Display transactions**.</span></span> <span data-ttu-id="2e237-118">Sidan **Avskilda transaktioner** visar en lista över de transaktioner som uppfyller de kriterier som definierats i frågan och som ska uteslutas ur historiska data när efterfrågeprognosen beräknas.</span><span class="sxs-lookup"><span data-stu-id="2e237-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="2e237-119">**Anm.:** Du kan också skapa en fråga som baseras på en befintlig fråga.</span><span class="sxs-lookup"><span data-stu-id="2e237-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="2e237-120">Välj den frågan som du vill kopiera från och klicka sedan på **Duplicera**.</span><span class="sxs-lookup"><span data-stu-id="2e237-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="2e237-121">Fältet **Frågedatum** identifierar versionen.</span><span class="sxs-lookup"><span data-stu-id="2e237-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="2e237-122">Du kan använda frågan som är den är eller klicka på **Redigera fråga** om du vill ändra kriterierna.</span><span class="sxs-lookup"><span data-stu-id="2e237-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="2e237-123">Du kan även ändra namn och beskrivning för den nya frågan.</span><span class="sxs-lookup"><span data-stu-id="2e237-123">You can optionally modify the name and description of the new query.</span></span>

<a name="additional-resources"></a><span data-ttu-id="2e237-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2e237-124">Additional resources</span></span>
--------

[<span data-ttu-id="2e237-125">Efterfrågeprognosticering – översikt</span><span class="sxs-lookup"><span data-stu-id="2e237-125">Demand forecasting overview</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="2e237-126">Övervaka prognosens exakthet</span><span class="sxs-lookup"><span data-stu-id="2e237-126">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)



