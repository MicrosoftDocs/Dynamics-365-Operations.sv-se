---
title: Avbryta ett huvudplaneringsjobb
description: I det här avsnittet beskrivs hur du avbryter ett aktivt planeringsjobb som använder inbyggd planeringsfunktion.
author: ChristianRytt
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 08dd612d9fb01ba2db6d4fcc7db9507a41a4b29f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203927"
---
# <a name="cancel-a-master-planning-job"></a><span data-ttu-id="989ce-103">Avbryta ett huvudplaneringsjobb</span><span class="sxs-lookup"><span data-stu-id="989ce-103">Cancel a master planning job</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="989ce-104">I Microsoft Dynamics 365 Supply Chain Management finns det flera alternativ för att avbryta ett huvudplaneringsjobb.</span><span class="sxs-lookup"><span data-stu-id="989ce-104">In Microsoft Dynamics 365 Supply Chain Management, there are multiple options for canceling a master planning job.</span></span> <span data-ttu-id="989ce-105">Du kanske till exempel vill avbryta ett huvudplaneringsjobb om det startades av misstag eller körs längre än förväntat och du vill avsluta det.</span><span class="sxs-lookup"><span data-stu-id="989ce-105">For example, you may want to cancel a master planning job if it was started by mistake or is running longer than expected and you want to end it.</span></span> <span data-ttu-id="989ce-106">Det bästa sättet att avbryta ett planeringsjobb är från sidan **oavslutade planeringsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="989ce-106">The best way to cancel a planning job is from  the **Unfinished planning processes** page.</span></span> <span data-ttu-id="989ce-107">Andra alternativ från sidorna **Batch-jobb** och **Förbättrade batch-jobb** bör endast användas om du avbryter huvud planerings jobbet från sidan **oavslutade planeringsprocesser** inte slutfördes inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="989ce-107">Alternative options from the **Batch jobs** and **Batch jobs enhanced** pages should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

## <a name="preferred-cancel-option"></a><span data-ttu-id="989ce-108">Önskat alternativ för Avbryt</span><span class="sxs-lookup"><span data-stu-id="989ce-108">Preferred cancel option</span></span>
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a><span data-ttu-id="989ce-109">Avbryt huvudplaneringsjobb från sidan **ej avslutade planeringsprocesser**</span><span class="sxs-lookup"><span data-stu-id="989ce-109">Cancel master planning job from **Unfinished planning processes** page</span></span>
1. <span data-ttu-id="989ce-110">Gå till **Huvudplanering > Förfrågningar och rapporter > Huvudplanering > Oavslutade planeringsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="989ce-110">Go to **Master planning > Inquiries and reports > Master planning > Unfinished planning processes**.</span></span>
2. <span data-ttu-id="989ce-111">Välj raden med planeringsprocessen som du vill avbryta.</span><span class="sxs-lookup"><span data-stu-id="989ce-111">Select the line with the planning process that you want to cancel.</span></span>
3. <span data-ttu-id="989ce-112">Klicka på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="989ce-112">Click **Cancel**.</span></span>

## <a name="additional-cancel-options"></a><span data-ttu-id="989ce-113">Ytterligare alternativ för avbryta</span><span class="sxs-lookup"><span data-stu-id="989ce-113">Additional cancel options</span></span>
<span data-ttu-id="989ce-114">Dessa bör endast användas om avbryt huvudplaneringsjobbet från sidan **oavslutade planeringsprocesser** inte slutfördes inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="989ce-114">These should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a><span data-ttu-id="989ce-115">Ta bort huvudplaneringsjobb från sidan **batchjobb**</span><span class="sxs-lookup"><span data-stu-id="989ce-115">Delete master planning job from the **Batch jobs** page</span></span>
1. <span data-ttu-id="989ce-116">Gå till **Systemadministration > Förfrågninger > Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="989ce-116">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="989ce-117">Välj raden med planeringsjobb som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="989ce-117">Select the line with the planning job that you want to delete.</span></span>
3. <span data-ttu-id="989ce-118">Klicka på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="989ce-118">Click **Delete**.</span></span>

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a><span data-ttu-id="989ce-119">Ta bort huvudplaneringsjobb från sidan **Förbättrade batchjobb**</span><span class="sxs-lookup"><span data-stu-id="989ce-119">Abort master planning job task from the **Batch jobs enhanced** page</span></span>
1. <span data-ttu-id="989ce-120">Gå till **Systemadministration > Förfrågninger > Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="989ce-120">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="989ce-121">Om jobb-ID inte visas i listan klickar du på **växla till utökat formulär**, annars fortsätter du med nästa steg.</span><span class="sxs-lookup"><span data-stu-id="989ce-121">If the job ID is not shown in the list, click **Switch to enhanced form**, otherwise proceed with the next step.</span></span>
3. <span data-ttu-id="989ce-122">Öppna batch-jobb.</span><span class="sxs-lookup"><span data-stu-id="989ce-122">Open the batch job.</span></span> <span data-ttu-id="989ce-123">Klicka på **jobb-ID** för batch-jobbet med aktiviteter som du vill avsluta.</span><span class="sxs-lookup"><span data-stu-id="989ce-123">Click the **Job ID** for the batch job with tasks that you want to end.</span></span>
4. <span data-ttu-id="989ce-124">I **Batchaktiviteter**, välj aktiviteterna som ska avslutas.</span><span class="sxs-lookup"><span data-stu-id="989ce-124">In **Batch tasks**, select the tasks to end.</span></span>
5. <span data-ttu-id="989ce-125">På snabbfliken **batchuppgifter** klickar du på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="989ce-125">On the **Batch tasks** FastTab, click **Abort**.</span></span>
