---
title: Behandla prisändringar
description: Bearbeta förmånens prisändringar i Microsoft Dynamics 365 Human Resources när en ny eller befintlig förmånsplan har en ändring i inställningarna för berättiganderegler.
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
ms.openlocfilehash: 9ebe5cfc2bdf7790770d27ece2dc67f7677db593
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010557"
---
# <a name="process-rate-changes"></a><span data-ttu-id="9f960-103">Behandla prisändringar</span><span class="sxs-lookup"><span data-stu-id="9f960-103">Process rate changes</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="9f960-104">Bearbeta förmånens prisändringar i Microsoft Dynamics 365 Human Resources när en ny eller befintlig förmånsplan har en ändring i inställningarna för berättiganderegler.</span><span class="sxs-lookup"><span data-stu-id="9f960-104">Process benefit rate changes in Microsoft Dynamics 365 Human Resources when a new or existing benefit plan has a change in eligibility rule settings.</span></span> <span data-ttu-id="9f960-105">Om en ny berättiganderegel skapas och tilldelas till planen uppmanas systemet att köra om arbetarens berättigande för att kontrollera om medarbetaren kan bli berättigade till planen baserat på nya berättigandealternativ.</span><span class="sxs-lookup"><span data-stu-id="9f960-105">If a new eligibility rule is created and assigned to the plan, this prompts the system to re-run worker eligibility to check if workers may now be eligible for the plan based on new eligibility options.</span></span> 

1. <span data-ttu-id="9f960-106">I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbeta uppdateringar i prisändringar**.</span><span class="sxs-lookup"><span data-stu-id="9f960-106">In the **Benefits management** workspace, under **Processing**, select **Rate change update processing**.</span></span>

2. <span data-ttu-id="9f960-107">I dialogrutan **Kör uppdateringsprocess av förmånspris** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="9f960-107">In the **Run benefit rate update process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="9f960-108">Fält</span><span class="sxs-lookup"><span data-stu-id="9f960-108">Field</span></span> | <span data-ttu-id="9f960-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9f960-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="9f960-110">Anmälningsperiod</span><span class="sxs-lookup"><span data-stu-id="9f960-110">Enrollment period</span></span> | <span data-ttu-id="9f960-111">Anmälningsperiod för bearbeta prisändring.</span><span class="sxs-lookup"><span data-stu-id="9f960-111">The enrollment period to process rate changes for.</span></span> |

3. <span data-ttu-id="9f960-112">Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="9f960-112">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="9f960-113">Ange information för processen.</span><span class="sxs-lookup"><span data-stu-id="9f960-113">Enter information for the process.</span></span>

   2. <span data-ttu-id="9f960-114">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f960-114">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="9f960-115">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f960-115">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="9f960-116">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f960-116">Select **OK**.</span></span> <span data-ttu-id="9f960-117">Processen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="9f960-117">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="9f960-118">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f960-118">Select **OK**.</span></span>
