--- 
title: Skapa ett batchjobb
description: "Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-batch-job"></a><span data-ttu-id="8e2ac-103">Skapa ett batchjobb</span><span class="sxs-lookup"><span data-stu-id="8e2ac-103">Create a batch job</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8e2ac-104">Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="8e2ac-105">Batchjobb körs med hjälp av säkerhetsreferenserna för användaren som skapade jobbet.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="8e2ac-106">Gör på följande sätt när du skapar ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="8e2ac-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="8e2ac-108">Skapa batchjobbet</span><span class="sxs-lookup"><span data-stu-id="8e2ac-108">Create the batch job</span></span>
1. <span data-ttu-id="8e2ac-109">Gå till Systemadministration > Förfrågninger > Batchjobb.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="8e2ac-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-110">Click New.</span></span>
3. <span data-ttu-id="8e2ac-111">Skriv ett värde i fältet Jobbbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="8e2ac-112">I fältet Tidsplanerat startdatum/-tid anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="8e2ac-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="8e2ac-114">Skapa en upprepning</span><span class="sxs-lookup"><span data-stu-id="8e2ac-114">Create a recurrence</span></span>
1. <span data-ttu-id="8e2ac-115">Klicka på Batchjobb i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="8e2ac-116">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-116">Click Recurrence.</span></span>
    * <span data-ttu-id="8e2ac-117">Använd dessa alternativ om du vill ange ett intervall och mönster för upprepningen.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="8e2ac-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="8e2ac-119">Lägg till notifieringar</span><span class="sxs-lookup"><span data-stu-id="8e2ac-119">Add alerts</span></span>
1. <span data-ttu-id="8e2ac-120">Klicka på Batchjobb i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="8e2ac-121">Klicka på Notifieringar.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-121">Click Alerts.</span></span>
    * <span data-ttu-id="8e2ac-122">Ange om du vill att notifieringar ska skickas när batchjobbet avslutas, innehåller ett fel eller annulleras.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="8e2ac-123">Sedan anger du om du vill att notifieringarna ska visas som popup-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="8e2ac-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8e2ac-124">Click OK.</span></span>


