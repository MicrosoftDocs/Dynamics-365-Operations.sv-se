---
title: Auktorisera en justerad prognos
description: Inte alla prognosdata måste godkännas omedelbart. Denna artikel beskriver hur du kan ange den period som en prognos är godkända för. Det förklarar också hur du kan attestera prognos för specifika företag och prognosmodeller.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 834ec090bc2bc8486bcb64b756c101a1142a0766
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264804"
---
# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="67472-105">Auktorisera en justerad prognos</span><span class="sxs-lookup"><span data-stu-id="67472-105">Authorize an adjusted forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67472-106">Inte alla prognosdata måste godkännas omedelbart.</span><span class="sxs-lookup"><span data-stu-id="67472-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="67472-107">Denna artikel beskriver hur du kan ange den period som en prognos är godkända för.</span><span class="sxs-lookup"><span data-stu-id="67472-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="67472-108">Det förklarar också hur du kan attestera prognos för specifika företag och prognosmodeller.</span><span class="sxs-lookup"><span data-stu-id="67472-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="67472-109">Inte alla prognosdata måste godkännas omedelbart.</span><span class="sxs-lookup"><span data-stu-id="67472-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="67472-110">Du kan ange start- och slutdatum för den period som prognosen är godkända för.</span><span class="sxs-lookup"><span data-stu-id="67472-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="67472-111">Med denna funktion kan du frysa specifikt kostnadsslag.</span><span class="sxs-lookup"><span data-stu-id="67472-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="67472-112">Start- och slutdatumen som du anger måste överensstämma med start- och slutdatumen på gruppen som prognosen skapas i.</span><span class="sxs-lookup"><span data-stu-id="67472-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="67472-113">Systemet använder denna begränsning och justerar datumen automatiskt om justeringar krävs.</span><span class="sxs-lookup"><span data-stu-id="67472-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="67472-114">På **fliken Detaljer** i fönstret **Attest** kan du visa information om den prognos som var mest nyligen genererade.</span><span class="sxs-lookup"><span data-stu-id="67472-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="67472-115">Du kan välja företag och prognosmodeller för att godkänna prognosen för användning.</span><span class="sxs-lookup"><span data-stu-id="67472-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="67472-116">Som standard är rutnätet omfattar alla företag som prognostiserad efterfrågan har skapats för.</span><span class="sxs-lookup"><span data-stu-id="67472-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="67472-117">För varje företag, den prognosmodell som motsvarar aktuell prognos plan som sätts upp i huvudplanering parametrar är fyllt.</span><span class="sxs-lookup"><span data-stu-id="67472-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="67472-118">Du kan dock ändra den här prognosmodellen till någon prognosmodell som tillhör företaget.</span><span class="sxs-lookup"><span data-stu-id="67472-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="67472-119">Om ingen förväntad efterfrågan data har skapats för ett valt företag, får du ett varningsmeddelande vid importen.</span><span class="sxs-lookup"><span data-stu-id="67472-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="67472-120">Det är mycket viktigt att du förstår hur **spara den manuella justeringar av baslinjen demand forecast** kryssruta fungerar.</span><span class="sxs-lookup"><span data-stu-id="67472-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="67472-121">Om du har gjort manuella justeringar av den statistisk baslinjeprognosen, kommer de justerade värdena att godkännas för användning även om denna kryssruta är avmarkerad.</span><span class="sxs-lookup"><span data-stu-id="67472-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="67472-122">Ändringarna kan emellertid kasseras efter tillstånd.</span><span class="sxs-lookup"><span data-stu-id="67472-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="67472-123">Därför nästa gång en prognos genereras, att prognosen är bara en statistisk prognos och inte har någon handmanöver, även om **överlåtelsen manuella justeringar för att efterfrågan** är markerad.</span><span class="sxs-lookup"><span data-stu-id="67472-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="67472-124">Därför kan du överväga att **spara den manuella justeringar av baslinjen demand forecast** kryssrutan en mekanism som låter dig att förvara eller kasta alla manuella ändringar.</span><span class="sxs-lookup"><span data-stu-id="67472-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

<a name="additional-resources"></a><span data-ttu-id="67472-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="67472-125">Additional resources</span></span>
--------

[<span data-ttu-id="67472-126">Gör manuella justeringar på baslinjeprognosen</span><span class="sxs-lookup"><span data-stu-id="67472-126">Make manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="67472-127">Övervaka prognosens exakthet</span><span class="sxs-lookup"><span data-stu-id="67472-127">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]