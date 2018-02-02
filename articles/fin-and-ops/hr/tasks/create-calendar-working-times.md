--- 
title: Skapa en kalender och generera arbetstider
description: "Kalendrar beskriver kapaciteten och arbetstider för verksamhetsresurser."
author: kherr75
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a9d0d9a3f278a09e89311ee75b6f95fb4f3b04cb
ms.openlocfilehash: 97751310cee3441d80d57860bc90490cf5708de2
ms.contentlocale: sv-se
ms.lasthandoff: 02/02/2018

---
# <a name="create-a-calendar-and-generate-working-times"></a><span data-ttu-id="234f3-103">Skapa en kalender och generera arbetstider</span><span class="sxs-lookup"><span data-stu-id="234f3-103">Create a calendar and generate working times</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="234f3-104">Kalendrar beskriver kapaciteten och arbetstider för verksamhetsresurser.</span><span class="sxs-lookup"><span data-stu-id="234f3-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="234f3-105">Den här proceduren gör att du kan definiera en arbetskalender som baseras på en arbetstidsmall.</span><span class="sxs-lookup"><span data-stu-id="234f3-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="234f3-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="234f3-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="234f3-107">Gå till Alla arbetsytor > Livscykelhantering för resurs.</span><span class="sxs-lookup"><span data-stu-id="234f3-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="234f3-108">Klicka på Kalendrar.</span><span class="sxs-lookup"><span data-stu-id="234f3-108">Click Calendars.</span></span>
3. <span data-ttu-id="234f3-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="234f3-109">Click New.</span></span>
4. <span data-ttu-id="234f3-110">Ange ett värde i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="234f3-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="234f3-111">Detta är id:t för kalendern, som används som referens när du kopplat kalendrar, till exempel till en verksamhetsresurs eller en resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="234f3-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="234f3-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="234f3-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="234f3-113">Ange ett värde i fältet Standardarbetsdag i timmar.</span><span class="sxs-lookup"><span data-stu-id="234f3-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="234f3-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="234f3-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="234f3-115">Klicka på arbetstider.</span><span class="sxs-lookup"><span data-stu-id="234f3-115">Click Working times.</span></span>
9. <span data-ttu-id="234f3-116">Klicka på Sammanställ arbetstider.</span><span class="sxs-lookup"><span data-stu-id="234f3-116">Click Compose working times.</span></span>
    * <span data-ttu-id="234f3-117">Generera arbetstid för varje dag under perioden där du vill kunna planera arbetet.</span><span class="sxs-lookup"><span data-stu-id="234f3-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="234f3-118">Efter hand kan du skapa arbetstider för ytterligare perioder.</span><span class="sxs-lookup"><span data-stu-id="234f3-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="234f3-119">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="234f3-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="234f3-120">Detta är den första dagen som kalendern måste vara öppen.</span><span class="sxs-lookup"><span data-stu-id="234f3-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="234f3-121">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="234f3-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="234f3-122">Detta är den sista dagen som kalendern är öppen.</span><span class="sxs-lookup"><span data-stu-id="234f3-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="234f3-123">Ange eller välj ett värde i fältet Arbetstidsmall.</span><span class="sxs-lookup"><span data-stu-id="234f3-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="234f3-124">Arbetstidmallen definierar arbetstiden för varje veckodag.</span><span class="sxs-lookup"><span data-stu-id="234f3-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="234f3-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="234f3-125">Click OK.</span></span>
14. <span data-ttu-id="234f3-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="234f3-126">Close the page.</span></span>


