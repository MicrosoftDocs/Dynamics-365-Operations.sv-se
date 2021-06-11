---
title: Skapa kalendrar och generera arbetstider
description: Kalendrar beskriver kapaciteten och arbetstider för verksamhetsresurser. Det här avsnittet förklarar för att definiera en arbetskalender som baseras på en arbetstidsmall.
author: andreabichsel
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate, HcmPersonnelManagementWorkspace, WrkCtrGroupDateCalendar, WrkCtrDateCalendar
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16decd94f72e6aefe4e1d058f4cfd6215d14f569
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058906"
---
# <a name="create-calendars-and-generate-working-times"></a><span data-ttu-id="55fa0-104">Skapa kalendrar och generera arbetstider</span><span class="sxs-lookup"><span data-stu-id="55fa0-104">Create calendars and generate working times</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="55fa0-105">Kalendrar beskriver kapaciteten och arbetstider för verksamhetsresurser.</span><span class="sxs-lookup"><span data-stu-id="55fa0-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="55fa0-106">Det här avsnittet förklarar för att definiera en arbetskalender som baseras på en arbetstidsmall.</span><span class="sxs-lookup"><span data-stu-id="55fa0-106">This article explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="55fa0-107">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="55fa0-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="55fa0-108">På startsidan väljer du **Livscykelhantering för resurs**.</span><span class="sxs-lookup"><span data-stu-id="55fa0-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="55fa0-109">Välj **kalendrar**.</span><span class="sxs-lookup"><span data-stu-id="55fa0-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="55fa0-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="55fa0-110">Select **New**.</span></span>
4. <span data-ttu-id="55fa0-111">I fältet **kalender** klassificerar du kalender.</span><span class="sxs-lookup"><span data-stu-id="55fa0-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="55fa0-112">Detta är id:t för kalendern, som används som referens när du kopplat kalendrar, till exempel till en verksamhetsresurs eller en resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="55fa0-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="55fa0-113">Ange sedan ett namn i fältet **Namn** för din kalender.</span><span class="sxs-lookup"><span data-stu-id="55fa0-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="55fa0-114">Ange ett värde i fältet **Standardarbetsdag i timmar**.</span><span class="sxs-lookup"><span data-stu-id="55fa0-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="55fa0-115">Kontrollera att raden är markerad och välj **arbetstider** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="55fa0-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="55fa0-116">Välj **Sammanställ arbetstider**.</span><span class="sxs-lookup"><span data-stu-id="55fa0-116">Select **Compose working times**.</span></span> <span data-ttu-id="55fa0-117">Skapa arbetstid för varje dag under perioden där du vill kunna planera arbetet.</span><span class="sxs-lookup"><span data-stu-id="55fa0-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="55fa0-118">Efter hand kan du skapa arbetstider för ytterligare perioder.</span><span class="sxs-lookup"><span data-stu-id="55fa0-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="55fa0-119">I fältet **Från datum** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="55fa0-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="55fa0-120">Detta är den första dagen som kalendern måste vara öppen.</span><span class="sxs-lookup"><span data-stu-id="55fa0-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="55fa0-121">I fältet **Till datum**, anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="55fa0-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="55fa0-122">Detta är den sista dagen som kalendern är öppen.</span><span class="sxs-lookup"><span data-stu-id="55fa0-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="55fa0-123">Ange eller välj ett värde i fältet **Arbetstidsmall**.</span><span class="sxs-lookup"><span data-stu-id="55fa0-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="55fa0-124">Arbetstidmallen definierar arbetstiden för varje veckodag.</span><span class="sxs-lookup"><span data-stu-id="55fa0-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="55fa0-125">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="55fa0-125">Select **OK**.</span></span>
13. <span data-ttu-id="55fa0-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="55fa0-126">Close the page.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]