---
title: Skapa en arbetstidskalender
description: Definiera en arbetstidskalender, semestrar och ej arbetstider i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ea55ad7f86e0c7d5ccc6e6de0af475299b05639
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052443"
---
# <a name="create-a-working-time-calendar"></a><span data-ttu-id="3fc1e-103">Skapa en arbetstidskalender</span><span class="sxs-lookup"><span data-stu-id="3fc1e-103">Create a working time calendar</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3fc1e-104">En arbetstidskalender i Dynamics 365 Human Resources visar de dagar och timmar som medarbetarna arbetar i din organisation.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-104">A working time calendar in Dynamics 365 Human Resources shows the days and hours that employees work in your organization.</span></span> <span data-ttu-id="3fc1e-105">När en medarbetare skickar en ledighetsansökan behöver han inte bekymra dig om helgdagar och stängningar.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-105">When an employee submits a time-off request, they don't have to worry about holidays and closures.</span></span>

<span data-ttu-id="3fc1e-106">Om du vill effektivisera begäranden om ledighet konfigurerar du de här artiklarna för din organisation:</span><span class="sxs-lookup"><span data-stu-id="3fc1e-106">To streamline time-off requests, configure these items for your organization:</span></span>

- <span data-ttu-id="3fc1e-107">Arbetstidskalender</span><span class="sxs-lookup"><span data-stu-id="3fc1e-107">Working time calendar</span></span>
- <span data-ttu-id="3fc1e-108">Helgdagar och stängningar</span><span class="sxs-lookup"><span data-stu-id="3fc1e-108">Holidays and closures</span></span>
- <span data-ttu-id="3fc1e-109">Ej arbetstid</span><span class="sxs-lookup"><span data-stu-id="3fc1e-109">Non-work time</span></span>

<span data-ttu-id="3fc1e-110">Du kan lägga till de sista två objekten medan du ställer in en arbetstidskalender.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-110">You can add the last two items while you're setting up a working time calendar.</span></span> <span data-ttu-id="3fc1e-111">Du kan även konfigurera eller uppdatera dem separat.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-111">You can also configure or update them separately.</span></span>

## <a name="set-up-a-working-time-calendar"></a><span data-ttu-id="3fc1e-112">Ställa in en arbetstidskalender</span><span class="sxs-lookup"><span data-stu-id="3fc1e-112">Set up a working time calendar</span></span>

<span data-ttu-id="3fc1e-113">Skapa minst en arbetstidskalender som visar dina dagar och arbetstider.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-113">Set up at least one working time calendar that shows your days and hours of operation.</span></span> <span data-ttu-id="3fc1e-114">Om du har platser i flera länder och regioner kanske du vill skapa en arbetstidskalender för varje område.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-114">If you have locations in multiple countries and regions, you might want to set up a working time calendar for each area.</span></span>

1. <span data-ttu-id="3fc1e-115">På sidan **Organisationsadministration** klickar du på **kalendrar**.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-115">On the **Organization administration** page, select **Calendars**.</span></span>

2. <span data-ttu-id="3fc1e-116">Välj **Ny** och ange ett nytt namn på och en beskrivning för din kalender.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-116">Select **New** and enter a name and description for your calendar.</span></span>

3. <span data-ttu-id="3fc1e-117">Under **Genereringsalternativ** väljer du arbetsdagar för organisationen och anger arbetstider.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-117">Under **Generation options**, select the work days for your organization and enter work times.</span></span> 
   - <span data-ttu-id="3fc1e-118">Om du vill lägga till en helgdag eller avslutning väljer du knappen **Lägg till** bredvid **helgdagar och stängningar**.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-118">To add a holiday or closure, select the **Add** button next to **Holidays and closures**.</span></span>
   - <span data-ttu-id="3fc1e-119">Om du vill lägga till ledig tid, som lunch eller raster, väljer du **Lägg till** under **EJ ARBETSTID** och anger namn och tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-119">To add non-work time, like lunches or breaks, select **Add** under **NON-WORK TIME** and enter the name and time range.</span></span>

4. <span data-ttu-id="3fc1e-120">Under **dagar**, välj **generera** för att generera dagar i kalendern.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-120">Under **Days**, select **Generate** to generate the days in your calendar.</span></span> <span data-ttu-id="3fc1e-121">Ange datumintervallet för kalendern och välj sedan **generera dagar**.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-121">Enter the date range for your calendar and then select **Generate days**.</span></span>

5. <span data-ttu-id="3fc1e-122">Lägg till arbetsscheman genom att under **Arbetsschema** välja **Lägg till** och sedan ange tiderna för varje arbetsschema.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-122">To add work schedules, under **Work schedule**, select **Add** and then enter the times for each work schedule.</span></span>

## <a name="configure-holidays-and-closures"></a><span data-ttu-id="3fc1e-123">Konfigurera helgdagar och stängningar</span><span class="sxs-lookup"><span data-stu-id="3fc1e-123">Configure holidays and closures</span></span>

<span data-ttu-id="3fc1e-124">Du kan lägga till eller ändra helgdagar och stängningar separat från en arbetstidskalender.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-124">You can add or change holidays and closures separately from a working time calendar.</span></span>

1. <span data-ttu-id="3fc1e-125">På sidan **Organisationsadministration** klickar du på **Helgdagar och stängningar**.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-125">On the **Organization administration** page, select **Holidays and closures**.</span></span>

2. <span data-ttu-id="3fc1e-126">Välj **Ny** och ange ett nytt namn och datum för helgdag och stängning.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-126">Select **New** and enter a name and date for the holiday or closure.</span></span>

## <a name="configure-non-work-time"></a><span data-ttu-id="3fc1e-127">Konfigurera ej arbetstid</span><span class="sxs-lookup"><span data-stu-id="3fc1e-127">Configure non-work time</span></span>

<span data-ttu-id="3fc1e-128">Du kan lägga till eller ändra ej arbetstider separat från en arbetstidskalender.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-128">You can add or change non-work times separately from a working time calendar.</span></span>

1. <span data-ttu-id="3fc1e-129">På sidan **Organisationsadministration** klickar du på **ej arbetstid**.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-129">On the **Organization administration** page, select **Non-work time**.</span></span>

2. <span data-ttu-id="3fc1e-130">Välj **Ny** och ange namnet och tidsintervallet för ej arbetstid.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-130">Select **New** and enter a name and time range for the non-work time.</span></span>

<span data-ttu-id="3fc1e-131">Om du har aktiverat förhandsgranskningsfunktionen för ledighet och frånvaro i helgdagar använder Personal helgdagar och stängningsdatum för att bestämma antalet dagar som ska anpassas för anställda som är registrerade i kalendern.</span><span class="sxs-lookup"><span data-stu-id="3fc1e-131">If you've enabled the Leave and absence bank holiday corrections preview feature, Human Resources uses holidays and closure dates to determine the number of days to adjust for employees enrolled in the calendar.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fc1e-132">Se även</span><span class="sxs-lookup"><span data-stu-id="3fc1e-132">See also</span></span>

- [<span data-ttu-id="3fc1e-133">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="3fc1e-133">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="3fc1e-134">Konfigurera typer av tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="3fc1e-134">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]