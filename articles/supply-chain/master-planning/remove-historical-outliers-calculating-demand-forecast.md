---
title: "Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos"
description: "Den här artikeln beskriver hur du utesluter avskilda från historiska data som används för att beräkna en efterfrågeprognos. Genom att exkludera avskilda kan du förbättra prognosexaktheten."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ea3f08b20e25af6ebb738c2373b65532d74a0c80
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="62a9a-104">Ta bort avskilda från historiska transaktionsdata när du beräknar en efterfrågeprognos</span><span class="sxs-lookup"><span data-stu-id="62a9a-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="62a9a-105">Den här artikeln beskriver hur du utesluter avskilda från historiska data som används för att beräkna en efterfrågeprognos.</span><span class="sxs-lookup"><span data-stu-id="62a9a-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="62a9a-106">Genom att exkludera avskilda kan du förbättra prognosexaktheten.</span><span class="sxs-lookup"><span data-stu-id="62a9a-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="62a9a-107">Du kan exkludera avvikare för att förbättra prognosexaktheten.</span><span class="sxs-lookup"><span data-stu-id="62a9a-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="62a9a-108">Den här uppgiften är valfri.</span><span class="sxs-lookup"><span data-stu-id="62a9a-108">This is an optional task.</span></span> <span data-ttu-id="62a9a-109">Här finns en översikt av processen:</span><span class="sxs-lookup"><span data-stu-id="62a9a-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="62a9a-110">Klicka på **Huvudplanering** &gt; **Inställningar** &gt; **Efterfrågeprognosticering** &gt; **Borttagning av avskild** för att öppna sidan **Borttagning av avskild** där du kan använda en fråga för att välja transaktionerna som ska undantas.</span><span class="sxs-lookup"><span data-stu-id="62a9a-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="62a9a-111">Välj vilket företag som frågan gäller och ange sedan ett namn och en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="62a9a-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="62a9a-112">Fältet **Frågedatum** ställs automatiskt in på aktuellt datum.</span><span class="sxs-lookup"><span data-stu-id="62a9a-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="62a9a-113">Markera kryssrutan **Aktiv** om du vill exkludera transaktionerna som hittas av frågan från historiska data.</span><span class="sxs-lookup"><span data-stu-id="62a9a-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="62a9a-114">Den här inställningen ska börja gälla när du skapar en baslinjeprognos.</span><span class="sxs-lookup"><span data-stu-id="62a9a-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="62a9a-115">På sidan **Fråga för borttagning av avskild** kan du lägga till, ta bort och välja kriterier som definierar vilka transaktioner som ska utelämnas när baslinjeprognosen beräknas.</span><span class="sxs-lookup"><span data-stu-id="62a9a-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="62a9a-116">Välj till exempel en viss artikel eller ordertransaktion som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="62a9a-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="62a9a-117">Klicka på **Visa transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="62a9a-117">Click **Display transactions**.</span></span> <span data-ttu-id="62a9a-118">Sidan **Avskilda transaktioner** visar en lista över de transaktioner som uppfyller de kriterier som definierats i frågan och som ska uteslutas ur historiska data när efterfrågeprognosen beräknas.</span><span class="sxs-lookup"><span data-stu-id="62a9a-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="62a9a-119">**Anm.:** Du kan också skapa en fråga som baseras på en befintlig fråga.</span><span class="sxs-lookup"><span data-stu-id="62a9a-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="62a9a-120">Välj den frågan som du vill kopiera från och klicka sedan på **Duplicera**.</span><span class="sxs-lookup"><span data-stu-id="62a9a-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="62a9a-121">Fältet **Frågedatum** identifierar versionen.</span><span class="sxs-lookup"><span data-stu-id="62a9a-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="62a9a-122">Du kan använda frågan som är den är eller klicka på **Redigera fråga** om du vill ändra kriterierna.</span><span class="sxs-lookup"><span data-stu-id="62a9a-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="62a9a-123">Du kan även ändra namn och beskrivning för den nya frågan.</span><span class="sxs-lookup"><span data-stu-id="62a9a-123">You can optionally modify the name and description of the new query.</span></span>

<a name="see-also"></a><span data-ttu-id="62a9a-124">Se även</span><span class="sxs-lookup"><span data-stu-id="62a9a-124">See also</span></span>
--------

[<span data-ttu-id="62a9a-125">Introduktion till efterfrågeprognosticering</span><span class="sxs-lookup"><span data-stu-id="62a9a-125">Introduction to demand forecasting</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="62a9a-126">Övervaka prognosprecision</span><span class="sxs-lookup"><span data-stu-id="62a9a-126">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)




