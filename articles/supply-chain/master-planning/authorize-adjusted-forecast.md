---
title: Auktorisera en justerad prognos
description: "Inte alla prognosdata måste godkännas omedelbart. Denna artikel beskriver hur du kan ange den period som en prognos är godkända för. Det förklarar också hur du kan attestera prognos för specifika företag och prognosmodeller."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 64838fd20349c21bf3c0a3b9a3c68d4f19f60745
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="58b39-105">Auktorisera en justerad prognos</span><span class="sxs-lookup"><span data-stu-id="58b39-105">Authorize an adjusted forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58b39-106">Inte alla prognosdata måste godkännas omedelbart.</span><span class="sxs-lookup"><span data-stu-id="58b39-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="58b39-107">Denna artikel beskriver hur du kan ange den period som en prognos är godkända för.</span><span class="sxs-lookup"><span data-stu-id="58b39-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="58b39-108">Det förklarar också hur du kan attestera prognos för specifika företag och prognosmodeller.</span><span class="sxs-lookup"><span data-stu-id="58b39-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="58b39-109">Inte alla prognosdata måste godkännas omedelbart.</span><span class="sxs-lookup"><span data-stu-id="58b39-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="58b39-110">Du kan ange start- och slutdatum för den period som prognosen är godkända för.</span><span class="sxs-lookup"><span data-stu-id="58b39-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="58b39-111">Med denna funktion kan du frysa specifikt kostnadsslag.</span><span class="sxs-lookup"><span data-stu-id="58b39-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="58b39-112">Start- och slutdatumen som du anger måste överensstämma med start- och slutdatumen på gruppen som prognosen skapas i.</span><span class="sxs-lookup"><span data-stu-id="58b39-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="58b39-113">Systemet använder denna begränsning och justerar datumen automatiskt om justeringar krävs.</span><span class="sxs-lookup"><span data-stu-id="58b39-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="58b39-114">På **fliken Detaljer** i fönstret **Attest** kan du visa information om den prognos som var mest nyligen genererade.</span><span class="sxs-lookup"><span data-stu-id="58b39-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="58b39-115">Du kan välja företag och prognosmodeller för att godkänna prognosen för användning.</span><span class="sxs-lookup"><span data-stu-id="58b39-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="58b39-116">Som standard är rutnätet omfattar alla företag som prognostiserad efterfrågan har skapats för.</span><span class="sxs-lookup"><span data-stu-id="58b39-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="58b39-117">För varje företag, den prognosmodell som motsvarar aktuell prognos plan som sätts upp i huvudplanering parametrar är fyllt.</span><span class="sxs-lookup"><span data-stu-id="58b39-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="58b39-118">Du kan dock ändra den här prognosmodellen till någon prognosmodell som tillhör företaget.</span><span class="sxs-lookup"><span data-stu-id="58b39-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="58b39-119">Om ingen förväntad efterfrågan data har skapats för ett valt företag, får du ett varningsmeddelande vid importen.</span><span class="sxs-lookup"><span data-stu-id="58b39-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="58b39-120">Det är mycket viktigt att du förstår hur **spara den manuella justeringar av baslinjen demand forecast** kryssruta fungerar.</span><span class="sxs-lookup"><span data-stu-id="58b39-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="58b39-121">Om du har gjort manuella justeringar av den statistisk baslinjeprognosen, kommer de justerade värdena att godkännas för användning även om denna kryssruta är avmarkerad.</span><span class="sxs-lookup"><span data-stu-id="58b39-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="58b39-122">Ändringarna kan emellertid kasseras efter tillstånd.</span><span class="sxs-lookup"><span data-stu-id="58b39-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="58b39-123">Därför nästa gång en prognos genereras, att prognosen är bara en statistisk prognos och inte har någon handmanöver, även om **överlåtelsen manuella justeringar för att efterfrågan** är markerad.</span><span class="sxs-lookup"><span data-stu-id="58b39-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="58b39-124">Därför kan du överväga att **spara den manuella justeringar av baslinjen demand forecast** kryssrutan en mekanism som låter dig att förvara eller kasta alla manuella ändringar.</span><span class="sxs-lookup"><span data-stu-id="58b39-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

<a name="additional-resources"></a><span data-ttu-id="58b39-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="58b39-125">Additional resources</span></span>
--------

[<span data-ttu-id="58b39-126">Gör manuella justeringar till den ursprungliga prognosen</span><span class="sxs-lookup"><span data-stu-id="58b39-126">Making manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="58b39-127">Övervaka prognosprecision</span><span class="sxs-lookup"><span data-stu-id="58b39-127">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)




