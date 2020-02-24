---
title: Bearbetning av berättigande för anmälan
description: I den här artikeln beskrivs hur du kör bearbetning av berättigande för anmälan.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010545"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="5a6bb-103">Bearbetning av berättigande för anmälan</span><span class="sxs-lookup"><span data-stu-id="5a6bb-103">Process enrollment eligibility</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="5a6bb-104">I den här artikeln beskrivs hur du kör bearbetning av berättigande för anmälan.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="5a6bb-105">I arbetsytan **Förmånshantering** under **bearbetar**, välj **Bearbetning av berättigande för anmälan**.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="5a6bb-106">I dialogrutan **Kör bearbetning av berättigande för förmånsanmälan** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="5a6bb-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="5a6bb-107">Fält</span><span class="sxs-lookup"><span data-stu-id="5a6bb-107">Field</span></span> | <span data-ttu-id="5a6bb-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5a6bb-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="5a6bb-109">Anmälningsperiod</span><span class="sxs-lookup"><span data-stu-id="5a6bb-109">Enrollment period</span></span> | <span data-ttu-id="5a6bb-110">Anmälningsperiod för att bearbeta av berättigande för anmälan.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="5a6bb-111">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="5a6bb-111">Legal entity</span></span> | <span data-ttu-id="5a6bb-112">Juridisk person att bearbeta berättigande för anmälan för.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="5a6bb-113">Arbetare</span><span class="sxs-lookup"><span data-stu-id="5a6bb-113">Worker</span></span> | <span data-ttu-id="5a6bb-114">Arbetare att bearbeta berättigande för anmälan för.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="5a6bb-115">Om du lämnar det här fältet tomt bearbetas en berättigande för anmälan för alla arbetare.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="5a6bb-116">Förmånsplan</span><span class="sxs-lookup"><span data-stu-id="5a6bb-116">Benefit plan</span></span> | <span data-ttu-id="5a6bb-117">Förmånsplan att bearbeta berättigande för anmälan för.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="5a6bb-118">Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="5a6bb-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="5a6bb-119">Ange information för processen.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="5a6bb-120">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="5a6bb-121">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="5a6bb-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-122">Select **OK**.</span></span> <span data-ttu-id="5a6bb-123">Processen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="5a6bb-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a6bb-124">Select **OK**.</span></span>
