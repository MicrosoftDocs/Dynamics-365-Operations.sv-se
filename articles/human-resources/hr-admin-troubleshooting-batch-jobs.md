---
title: Optimera prestanda genom att tidsplanera batchjobb efter timmar
description: I det här avsnittet beskrivs hur du löser prestandaproblem med Microsoft Dynamics 365 Human Resources genom att schemalägga långvariga batchjobb efter timmar.
author: andreabichsel
manager: AnnBe
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 452a87cf5ba6c1ac73636584d75b2ec2ac555e02
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527775"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a><span data-ttu-id="e9038-103">Optimera prestanda genom att tidsplanera batchjobb efter timmar</span><span class="sxs-lookup"><span data-stu-id="e9038-103">Optimize performance by scheduling batch jobs after hours</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="e9038-104">Utfärda</span><span class="sxs-lookup"><span data-stu-id="e9038-104">Issue</span></span>

<span data-ttu-id="e9038-105">Microsoft Dynamics 365 Human Resources kan uppleva prestandaproblem om långvariga batchjobb körs under normal arbetstid.</span><span class="sxs-lookup"><span data-stu-id="e9038-105">Microsoft Dynamics 365 Human Resources can experience performance issues if long-running batch jobs run during typical business hours.</span></span>

## <a name="resolution"></a><span data-ttu-id="e9038-106">Upplösning</span><span class="sxs-lookup"><span data-stu-id="e9038-106">Resolution</span></span>

<span data-ttu-id="e9038-107">Tidsplanera följande batchjobb vid ledighet.</span><span class="sxs-lookup"><span data-stu-id="e9038-107">Schedule the following batch jobs during off hours.</span></span> <span data-ttu-id="e9038-108">Vi rekommenderar också att du granskar frekvensen av batchjobb som körs ofta.</span><span class="sxs-lookup"><span data-stu-id="e9038-108">We also recommend reviewing the frequency of batch jobs that run frequently.</span></span> <span data-ttu-id="e9038-109">Minska om möjligt upprepningen av batchjobbet.</span><span class="sxs-lookup"><span data-stu-id="e9038-109">If possible, reduce the recurrence of the batch job.</span></span> <span data-ttu-id="e9038-110">I många fall är standardfrekvensen tillräcklig.</span><span class="sxs-lookup"><span data-stu-id="e9038-110">In many cases, the default frequency is sufficient.</span></span>

<span data-ttu-id="e9038-111">Följande batchjobb ska köras under nätter eller efter timmar.</span><span class="sxs-lookup"><span data-stu-id="e9038-111">The following batch jobs should run at night or after hours.</span></span> <span data-ttu-id="e9038-112">Kontrollera tids zonen för dessa återkommande batchjobb.</span><span class="sxs-lookup"><span data-stu-id="e9038-112">Be sure to check the time zone for these recurring batch jobs.</span></span> <span data-ttu-id="e9038-113">Vissa batchjobb kan använda Pacific Standard Time (PST).</span><span class="sxs-lookup"><span data-stu-id="e9038-113">Some batch jobs might use Pacific Standard Time (PST).</span></span>

| <span data-ttu-id="e9038-114">Batchjobb</span><span class="sxs-lookup"><span data-stu-id="e9038-114">Batch job</span></span> | <span data-ttu-id="e9038-115">Standardförekomst</span><span class="sxs-lookup"><span data-stu-id="e9038-115">Default occurrence</span></span> |
| --- | --- |
| <span data-ttu-id="e9038-116">Rensa historik över batchjobb</span><span class="sxs-lookup"><span data-stu-id="e9038-116">Batch job history cleanup</span></span> | <span data-ttu-id="e9038-117">1 gång per månad</span><span class="sxs-lookup"><span data-stu-id="e9038-117">1 time per month</span></span> |
| <span data-ttu-id="e9038-118">Exportera rensning av mellanlagring</span><span class="sxs-lookup"><span data-stu-id="e9038-118">Export staging cleanup</span></span> | <span data-ttu-id="e9038-119">1 gång per dag</span><span class="sxs-lookup"><span data-stu-id="e9038-119">1 time per day</span></span> |
| <span data-ttu-id="e9038-120">Common Data Service-integration, synkronisering av missad begäran</span><span class="sxs-lookup"><span data-stu-id="e9038-120">Common Data Service integration missed request sync</span></span> | <span data-ttu-id="e9038-121">1 gång per dag</span><span class="sxs-lookup"><span data-stu-id="e9038-121">1 time per day</span></span> |
| <span data-ttu-id="e9038-122">Systemjobb för databaskomprimering som regelbundet måste köras på ledig tid</span><span class="sxs-lookup"><span data-stu-id="e9038-122">Database compression system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="e9038-123">1 gång per dag</span><span class="sxs-lookup"><span data-stu-id="e9038-123">1 time per day</span></span> |
| <span data-ttu-id="e9038-124">Systemjobb för återskapa databasindex som regelbundet måste köras på ledig tid</span><span class="sxs-lookup"><span data-stu-id="e9038-124">Database index rebuild system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="e9038-125">1 gång per dag</span><span class="sxs-lookup"><span data-stu-id="e9038-125">1 time per day</span></span> |

1. <span data-ttu-id="e9038-126">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="e9038-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="e9038-127">I fältet **Sök** söker du efter ett av batchjobben ovan.</span><span class="sxs-lookup"><span data-stu-id="e9038-127">In the **Search** bar, search for one of the above batch jobs.</span></span>

3. <span data-ttu-id="e9038-128">Välj **kör i bakgrunden** och välj sedan **återkommande**.</span><span class="sxs-lookup"><span data-stu-id="e9038-128">Select **Run in the background**, and then select **Recurrence**.</span></span>

   ![Ange upprepning](media/talent-batch-history-cleanup-recurrence.png)

4. <span data-ttu-id="e9038-130">Under **Definiera återkommande**, ange **Startdatum** och **Starttid** vid ledighet eller helg.</span><span class="sxs-lookup"><span data-stu-id="e9038-130">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off hours or the weekend.</span></span> <span data-ttu-id="e9038-131">Välj **Inget slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="e9038-131">Select **No end date**.</span></span> 

   ![Definiera återkommande startdatum och tid](media/talent-batch-history-cleanup-define-recurrence.png)

5. <span data-ttu-id="e9038-133">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9038-133">Select **OK**.</span></span>

6. <span data-ttu-id="e9038-134">Ändra övriga parametrar under **kör i bakgrunden** om det behövs och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9038-134">If needed, change any other parameters under **Run in the background**, and then select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e9038-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e9038-135">Additional resources</span></span>

[<span data-ttu-id="e9038-136">Optimera prestanda med automatiska rensningsuppgifter</span><span class="sxs-lookup"><span data-stu-id="e9038-136">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)
