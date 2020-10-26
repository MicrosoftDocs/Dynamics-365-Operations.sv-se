---
title: Skapa ett batchjobb
description: Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4903724adc9deaa40b6cd04c215273dd4b0522d4
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982536"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="a29a1-103">Skapa ett batchjobb</span><span class="sxs-lookup"><span data-stu-id="a29a1-103">Create a batch job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a29a1-104">Ett batchjobb är en grupp med uppgifter som skickas till en AOS-instans (Application Object Server) för automatisk bearbetning.</span><span class="sxs-lookup"><span data-stu-id="a29a1-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="a29a1-105">Batchjobb körs med hjälp av säkerhetsreferenserna för användaren som skapade jobbet.</span><span class="sxs-lookup"><span data-stu-id="a29a1-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="a29a1-106">Gör på följande sätt när du skapar ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="a29a1-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="a29a1-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="a29a1-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="a29a1-108">Skapa batchjobbet</span><span class="sxs-lookup"><span data-stu-id="a29a1-108">Create the batch job</span></span>
1. <span data-ttu-id="a29a1-109">Gå till **Navigeringsfönster > Moduler > Systemadministration > Frågor > Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="a29a1-110">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-110">Click **New**.</span></span>
3. <span data-ttu-id="a29a1-111">Skriv ett värde i fältet **Jobbbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="a29a1-112">I fältet **Tidsplanerat startdatum/-tid** anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="a29a1-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="a29a1-113">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="a29a1-114">Skapa en upprepning</span><span class="sxs-lookup"><span data-stu-id="a29a1-114">Create a recurrence</span></span>
1. <span data-ttu-id="a29a1-115">Klicka på **Batchjobb** i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a29a1-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="a29a1-116">Klicka på **Upprepning.**</span><span class="sxs-lookup"><span data-stu-id="a29a1-116">Click **Recurrence**.</span></span> <span data-ttu-id="a29a1-117">Använd dessa alternativ om du vill ange ett intervall och mönster för upprepningen.</span><span class="sxs-lookup"><span data-stu-id="a29a1-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="a29a1-118">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="a29a1-119">Lägg till notifieringar</span><span class="sxs-lookup"><span data-stu-id="a29a1-119">Add alerts</span></span>
1. <span data-ttu-id="a29a1-120">Klicka på **Batchjobb** i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a29a1-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="a29a1-121">Klicka på **Notifieringar**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-121">Click **Alerts**.</span></span> <span data-ttu-id="a29a1-122">Ange om du vill att notifieringar ska skickas när batchjobbet avslutas, innehåller ett fel eller annulleras.</span><span class="sxs-lookup"><span data-stu-id="a29a1-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="a29a1-123">Sedan anger du om du vill att notifieringarna ska visas som popup-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a29a1-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="a29a1-124">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="a29a1-125">Justera batchjobbstatus</span><span class="sxs-lookup"><span data-stu-id="a29a1-125">Adjust batch job status</span></span>
1. <span data-ttu-id="a29a1-126">Gå till **Systemadministration > Förfrågninger > Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="a29a1-127">Välj lämplig batchjobb.</span><span class="sxs-lookup"><span data-stu-id="a29a1-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="a29a1-128">Klicka på **Batchjobb > Funktioner > Ändra status** i Åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a29a1-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="a29a1-129">Välj lämplig status.</span><span class="sxs-lookup"><span data-stu-id="a29a1-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="a29a1-130">**Källskatte**: Ställ in batchjobbet som **källskatt** så att det inte dras från batchjobbets tidsplan.</span><span class="sxs-lookup"><span data-stu-id="a29a1-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="a29a1-131">Motsvarar *stopp*.</span><span class="sxs-lookup"><span data-stu-id="a29a1-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="a29a1-132">**Väntar**: Ställ in batchjobbet som **väntar** så att det väntar på att få hämtas av batchjobbets tidsplan.</span><span class="sxs-lookup"><span data-stu-id="a29a1-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="a29a1-133">Motsvarar *gå*.</span><span class="sxs-lookup"><span data-stu-id="a29a1-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="a29a1-134">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a29a1-134">Click **OK**.</span></span>
