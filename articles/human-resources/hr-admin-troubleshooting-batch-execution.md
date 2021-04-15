---
title: Återställ låsta batchjobb
description: I det här avsnittet beskrivs hur du löser problem med batchjobb som är låsta.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 01ef0bf8ccc486614eec42d3fb6f0b2941fc47c0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794959"
---
# <a name="reset-stuck-batch-jobs"></a><span data-ttu-id="81adb-103">Återställ låsta batchjobb</span><span class="sxs-lookup"><span data-stu-id="81adb-103">Reset stuck batch jobs</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a><span data-ttu-id="81adb-104">Utleverans</span><span class="sxs-lookup"><span data-stu-id="81adb-104">Issue</span></span>

<span data-ttu-id="81adb-105">Microsoft Dynamics 365 Human Resources kan uppleva problem med batchjobb som sitter fast i antingen ett **Utförande** eller **Avbrytande** tillstånd och inte är fullständig.</span><span class="sxs-lookup"><span data-stu-id="81adb-105">Microsoft Dynamics 365 Human Resources can experience issues with batch jobs that are stuck in either an **Executing** or **Canceling** state and don't complete.</span></span>

## <a name="resolution"></a><span data-ttu-id="81adb-106">Upplösning</span><span class="sxs-lookup"><span data-stu-id="81adb-106">Resolution</span></span>

<span data-ttu-id="81adb-107">När ett batchjobb har körts fast i läget **Utförande** eller **Avbrytande** kan du återställa statusen genom att framtvinga annulleringen av jobbet.</span><span class="sxs-lookup"><span data-stu-id="81adb-107">When a batch job is stuck in an **Executing** or **Canceling** state, you can reset the status by forcing the cancellation of the job.</span></span> <span data-ttu-id="81adb-108">När du har annullerat det kan du återställa batchjobbet genom att ange det till **Väntande** tillstånd.</span><span class="sxs-lookup"><span data-stu-id="81adb-108">After you cancel it, you can reset the batch job by setting it to a **Waiting** status.</span></span> <span data-ttu-id="81adb-109">Den kommer då att hämtas igen för körning i nästa planerade batchkörning.</span><span class="sxs-lookup"><span data-stu-id="81adb-109">It will then be picked up again for execution in the next scheduled batch run.</span></span>

1. <span data-ttu-id="81adb-110">I arbetsytan **Systemadministration**, välj sidan **Länkar** och välj **Batch-jobb**.</span><span class="sxs-lookup"><span data-stu-id="81adb-110">In the **System administration** workspace, select the **Links** page, and select **Batch jobs**.</span></span>

2. <span data-ttu-id="81adb-111">I listsidan **Batch-jobb**, välj det jobb som behöver återställas.</span><span class="sxs-lookup"><span data-stu-id="81adb-111">On the **Batch job** list page, select the job that needs to be reset.</span></span>

3. <span data-ttu-id="81adb-112">Välj på åtgärdsmenyfliken **Tvinna annullering** och bekräfta åtgärden.</span><span class="sxs-lookup"><span data-stu-id="81adb-112">On the action ribbon, select **Force cancel**, and confirm the action.</span></span>

   > [!NOTE]
   > <span data-ttu-id="81adb-113">Åtgärden **Tvinga annullering** är bara tillgänglig när det valda batchjobbet har statusvärdet **Utföra** eller **Annullera** och inga batchkörnings- eller avbokningsprocesser körs för jobbet.</span><span class="sxs-lookup"><span data-stu-id="81adb-113">The **Force cancel** action is only available when the selected batch job has a status of either **Executing** or **Canceling**, and no batch execution or cancellation processes are running for the job.</span></span>

4. <span data-ttu-id="81adb-114">På åtgärdsmenyfliken väljer du **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="81adb-114">On the action ribbon, select **Change status**.</span></span>

5. <span data-ttu-id="81adb-115">På sidan **Välj ny status**, välj **Väntar** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="81adb-115">On the **Select new status** page, select **Waiting**, and then select **OK**.</span></span>

   ![Välj ett nytt batchjobbstatus](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a><span data-ttu-id="81adb-117">Se även</span><span class="sxs-lookup"><span data-stu-id="81adb-117">See also</span></span>

[<span data-ttu-id="81adb-118">Optimera prestandan genom att schemalägga batchjobb efter kontorstid</span><span class="sxs-lookup"><span data-stu-id="81adb-118">Optimize performance by scheduling batch jobs after hours</span></span>](hr-admin-troubleshooting-batch-jobs.md)<br>
[<span data-ttu-id="81adb-119">Optimera prestanda med automatiska rensningsuppgifter</span><span class="sxs-lookup"><span data-stu-id="81adb-119">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
