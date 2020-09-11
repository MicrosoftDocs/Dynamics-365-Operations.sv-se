---
title: Bearbeta ändring av livshändelse
description: Bearbeta ändring av livshändelse i Microsoft Dynamics 365 Human Resources för ändringar i livshändelser.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39d1e94347809a1756fc4f66e5edc345c70eaf39
ms.sourcegitcommit: 9723b5ff40c84677316d71e185cf862556b32cf9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2020
ms.locfileid: "3741446"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="3ff7d-103">Bearbeta ändring av livshändelse</span><span class="sxs-lookup"><span data-stu-id="3ff7d-103">Process life event changes</span></span>

<span data-ttu-id="3ff7d-104">Bearbeta ändring av livshändelse i Microsoft Dynamics 365 Human Resources för två ändringar i livshändelser:</span><span class="sxs-lookup"><span data-stu-id="3ff7d-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="3ff7d-105">Födelsedagsändringar</span><span class="sxs-lookup"><span data-stu-id="3ff7d-105">Birthday changes</span></span>
- <span data-ttu-id="3ff7d-106">Ändringar av berättiganderegelns giltighet</span><span class="sxs-lookup"><span data-stu-id="3ff7d-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="3ff7d-107">I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbeta ändringar i livshändelser**.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="3ff7d-108">I dialogrutan **Kör ändringsprocess för livshändelse** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="3ff7d-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="3ff7d-109">Fält</span><span class="sxs-lookup"><span data-stu-id="3ff7d-109">Field</span></span> | <span data-ttu-id="3ff7d-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3ff7d-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="3ff7d-111">Anmälningsperiod</span><span class="sxs-lookup"><span data-stu-id="3ff7d-111">Enrollment period</span></span> | <span data-ttu-id="3ff7d-112">Anmälningsperiod för bearbeta ändring av livshändelse.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="3ff7d-113">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="3ff7d-113">Legal entity</span></span> | <span data-ttu-id="3ff7d-114">Juridisk person för bearbeta ändring av livshändelse.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="3ff7d-115">Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="3ff7d-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="3ff7d-116">Ange information för processen.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="3ff7d-117">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="3ff7d-118">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="3ff7d-119">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-119">Select **OK**.</span></span> <span data-ttu-id="3ff7d-120">Processen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="3ff7d-121">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ff7d-121">Select **OK**.</span></span>
