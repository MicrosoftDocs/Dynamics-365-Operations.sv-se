---
title: Bearbeta ändring av livshändelse
description: Bearbeta ändring av livshändelse i Microsoft Dynamics 365 Human Resources för ändringar i livshändelser.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a3cddc6205660b48abd9067bfdcaa04c9d2ba541
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790918"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="02a6c-103">Bearbeta ändring av livshändelse</span><span class="sxs-lookup"><span data-stu-id="02a6c-103">Process life event changes</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="02a6c-104">Bearbeta ändring av livshändelse i Microsoft Dynamics 365 Human Resources för två ändringar i livshändelser:</span><span class="sxs-lookup"><span data-stu-id="02a6c-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="02a6c-105">Födelsedagsändringar</span><span class="sxs-lookup"><span data-stu-id="02a6c-105">Birthday changes</span></span>
- <span data-ttu-id="02a6c-106">Ändringar av berättiganderegelns giltighet</span><span class="sxs-lookup"><span data-stu-id="02a6c-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="02a6c-107">I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbeta ändringar i livshändelser**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="02a6c-108">I dialogrutan **Kör ändringsprocess för livshändelse** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="02a6c-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="02a6c-109">Fält</span><span class="sxs-lookup"><span data-stu-id="02a6c-109">Field</span></span> | <span data-ttu-id="02a6c-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="02a6c-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="02a6c-111">Anmälningsperiod</span><span class="sxs-lookup"><span data-stu-id="02a6c-111">Enrollment period</span></span> | <span data-ttu-id="02a6c-112">Anmälningsperiod för bearbeta ändring av livshändelse.</span><span class="sxs-lookup"><span data-stu-id="02a6c-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="02a6c-113">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="02a6c-113">Legal entity</span></span> | <span data-ttu-id="02a6c-114">Juridisk person för bearbeta ändring av livshändelse.</span><span class="sxs-lookup"><span data-stu-id="02a6c-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="02a6c-115">Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="02a6c-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="02a6c-116">Ange information för processen.</span><span class="sxs-lookup"><span data-stu-id="02a6c-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="02a6c-117">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="02a6c-118">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="02a6c-119">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-119">Select **OK**.</span></span> <span data-ttu-id="02a6c-120">Processen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="02a6c-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="02a6c-121">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-121">Select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]