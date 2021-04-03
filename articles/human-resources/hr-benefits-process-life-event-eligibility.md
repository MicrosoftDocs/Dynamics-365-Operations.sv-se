---
title: Bearbetning av berättigande för livshändelse
description: I den här artikeln beskrivs hur du kör bearbetning av berättigande för livshändelse.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: fdb2f00675fa5191e05dcb99525c1ec9a8b16bd2
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466288"
---
# <a name="process-life-event-eligibility"></a><span data-ttu-id="8df44-103">Bearbetning av berättigande för livshändelse</span><span class="sxs-lookup"><span data-stu-id="8df44-103">Process life event eligibility</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8df44-104">I den här artikeln beskrivs hur du kör bearbetning av berättigande för livshändelse.</span><span class="sxs-lookup"><span data-stu-id="8df44-104">This article shows you how to run the process for life event eligibility.</span></span>

1. <span data-ttu-id="8df44-105">I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbetning av berättigande för livshändelse**.</span><span class="sxs-lookup"><span data-stu-id="8df44-105">In the **Benefits management** workspace, under **Processing**, select **Life event eligibility processing**.</span></span>

2. <span data-ttu-id="8df44-106">I dialogrutan **Kör bearbetning av berättigande för livshändelse** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="8df44-106">In the **Run life event eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="8df44-107">Fält</span><span class="sxs-lookup"><span data-stu-id="8df44-107">Field</span></span> | <span data-ttu-id="8df44-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8df44-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="8df44-109">**Anmälningsperiod**</span><span class="sxs-lookup"><span data-stu-id="8df44-109">**Enrollment period**</span></span> | <span data-ttu-id="8df44-110">Anmälningsperiod för bearbetning av berättigande för livshändelse.</span><span class="sxs-lookup"><span data-stu-id="8df44-110">The enrollment period to process life event eligibility for.</span></span> |

3. <span data-ttu-id="8df44-111">Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="8df44-111">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="8df44-112">Ange information för processen.</span><span class="sxs-lookup"><span data-stu-id="8df44-112">Enter information for the process.</span></span>

   2. <span data-ttu-id="8df44-113">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8df44-113">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="8df44-114">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="8df44-114">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="8df44-115">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8df44-115">Select **OK**.</span></span> <span data-ttu-id="8df44-116">Processen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="8df44-116">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="8df44-117">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8df44-117">Select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]