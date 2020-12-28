---
title: Behandla prisändringar
description: Bearbeta förmånens prisändringar i Microsoft Dynamics 365 Human Resources när en ny eller befintlig förmånsplan har en ändring i inställningarna för berättiganderegler.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: da42ef6ea91b95903316e35b551b222b8ff3b946
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420564"
---
# <a name="process-rate-changes"></a><span data-ttu-id="602d2-103">Behandla prisändringar</span><span class="sxs-lookup"><span data-stu-id="602d2-103">Process rate changes</span></span>

<span data-ttu-id="602d2-104">Bearbeta förmånens prisändringar i Microsoft Dynamics 365 Human Resources när en ny eller befintlig förmånsplan har en ändring i inställningarna för berättiganderegler.</span><span class="sxs-lookup"><span data-stu-id="602d2-104">Process benefit rate changes in Microsoft Dynamics 365 Human Resources when a new or existing benefit plan has a change in eligibility rule settings.</span></span> <span data-ttu-id="602d2-105">Om en ny berättiganderegel skapas och tilldelas till planen uppmanas systemet att köra om arbetarens berättigande för att kontrollera om medarbetaren kan bli berättigade till planen baserat på nya berättigandealternativ.</span><span class="sxs-lookup"><span data-stu-id="602d2-105">If a new eligibility rule is created and assigned to the plan, this prompts the system to rerun worker eligibility to check if workers may now be eligible for the plan based on new eligibility options.</span></span> 

1. <span data-ttu-id="602d2-106">I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbeta uppdateringar i prisändringar**.</span><span class="sxs-lookup"><span data-stu-id="602d2-106">In the **Benefits management** workspace, under **Processing**, select **Rate change update processing**.</span></span>

2. <span data-ttu-id="602d2-107">I dialogrutan **Kör uppdateringsprocess av förmånspris** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="602d2-107">In the **Run benefit rate update process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="602d2-108">Fält</span><span class="sxs-lookup"><span data-stu-id="602d2-108">Field</span></span> | <span data-ttu-id="602d2-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="602d2-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="602d2-110">**Anmälningsperiod**</span><span class="sxs-lookup"><span data-stu-id="602d2-110">**Enrollment period**</span></span> | <span data-ttu-id="602d2-111">Anmälningsperiod för bearbeta prisändring.</span><span class="sxs-lookup"><span data-stu-id="602d2-111">The enrollment period to process rate changes for.</span></span> |

3. <span data-ttu-id="602d2-112">Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="602d2-112">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="602d2-113">Ange information för processen.</span><span class="sxs-lookup"><span data-stu-id="602d2-113">Enter information for the process.</span></span>

   2. <span data-ttu-id="602d2-114">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="602d2-114">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="602d2-115">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="602d2-115">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="602d2-116">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="602d2-116">Select **OK**.</span></span> <span data-ttu-id="602d2-117">Processen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="602d2-117">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="602d2-118">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="602d2-118">Select **OK**.</span></span>
