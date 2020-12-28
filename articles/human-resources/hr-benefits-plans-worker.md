---
title: Skapa förmånsplaner för arbetare
description: Du kan skapa pensionsplaner för arbetare i Microsoft Dynamics 365 Human Resources för att välja förmånsplaner för medarbetare och för att bekräfta förmånsplanens val.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitPlanEmployee, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ebd19cba8dd7cac8ccf6d17d4206731be87a225
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420541"
---
# <a name="create-worker-benefit-plans"></a><span data-ttu-id="4d7fd-103">Skapa förmånsplaner för arbetare</span><span class="sxs-lookup"><span data-stu-id="4d7fd-103">Create worker benefit plans</span></span>

<span data-ttu-id="4d7fd-104">Du kan skapa pensionsplaner för arbetare i Microsoft Dynamics 365 Human Resources för att välja förmånsplaner för medarbetare och för att bekräfta förmånsplanens val.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-104">You can create worker benefit plans in Microsoft Dynamics 365 Human Resources to select benefit plans for employees and to confirm benefit plan selections.</span></span> <span data-ttu-id="4d7fd-105">Vanligtvis väljer medarbetare själv förmånsplaner med hjälp av medarbetarens självbetjäning och en förmånsadministratör bekräftar valen.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-105">Typically, employees select benefit plans themselves by using Employee self service, and then a benefits administrator confirms the selections.</span></span> 

1. <span data-ttu-id="4d7fd-106">I arbetsytan **Hantering av förmåner** under **Planer**, välj **Förmånsplaner för arbetare**.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-106">In the **Benefits management** workspace, under **Plans**, select **Worker benefit plans**.</span></span>

2. <span data-ttu-id="4d7fd-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-107">Select **New**.</span></span>

3. <span data-ttu-id="4d7fd-108">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="4d7fd-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="4d7fd-109">Fält</span><span class="sxs-lookup"><span data-stu-id="4d7fd-109">Field</span></span> | <span data-ttu-id="4d7fd-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4d7fd-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="4d7fd-111">Period</span><span class="sxs-lookup"><span data-stu-id="4d7fd-111">Period</span></span> | <span data-ttu-id="4d7fd-112">Anger en förmånsperiod som ska användas för att filtrera planerna på snabbfliken planer. Filtrera planerna så att du kan välja en delmängd av alla planposter så att du kan bekräfta delmängden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-112">Specifies a benefits period to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> <span data-ttu-id="4d7fd-113">Välj till exempel en period som du skapat med namnet 2015 för att bekräfta alla förmånsanmälningsval för 2015.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-113">For example, select a period you created called 2015 to confirm all the benefit enrollment selections for 2015.</span></span> |
   | <span data-ttu-id="4d7fd-114">Arbetare</span><span class="sxs-lookup"><span data-stu-id="4d7fd-114">Worker</span></span> | <span data-ttu-id="4d7fd-115">Anger en arbetare som ska användas för att filtrera planerna på snabbfliken planer. Filtrera planerna så att du kan välja en delmängd av alla planposter så att du kan bekräfta delmängden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-115">Specifies a worker to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="4d7fd-116">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="4d7fd-116">Legal entity</span></span> | <span data-ttu-id="4d7fd-117">Anger en juridisk person som ska användas för att filtrera planerna på snabbfliken planer. Filtrera planerna så att du kan välja en delmängd av alla planposter så att du kan bekräfta delmängden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-117">Specifies a legal entity to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="4d7fd-118">Omfattningsalternativ</span><span class="sxs-lookup"><span data-stu-id="4d7fd-118">Coverage option</span></span> | <span data-ttu-id="4d7fd-119">Anger en omfattningsalternativ som ska användas för att filtrera planerna på snabbfliken planer. Filtrera planerna så att du kan välja en delmängd av alla planposter så att du kan bekräfta delmängden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-119">Specifies a coverage option to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="4d7fd-120">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="4d7fd-120">Default</span></span> | <span data-ttu-id="4d7fd-121">Filtrerar förmånsplanerna baserat på om de är en standardplan.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-121">Filters the benefit plans based on whether they are a default plan.</span></span> <span data-ttu-id="4d7fd-122">Filtrera planerna för att hjälpa dig att välja en delmängd av alla planposter så att du kan bekräfta delmängden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-122">Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="4d7fd-123">Status</span><span class="sxs-lookup"><span data-stu-id="4d7fd-123">Status</span></span> | <span data-ttu-id="4d7fd-124">Filtrerar förmånsplaner utifrån deras status.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-124">Filters benefit plans based on their status.</span></span> <span data-ttu-id="4d7fd-125">Filtrera planerna för att hjälpa dig att välja en delmängd av alla planposter så att du kan bekräfta delmängden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-125">Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="4d7fd-126">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="4d7fd-126">Confirmation</span></span> | <span data-ttu-id="4d7fd-127">Anger en bekräftelsestatus som ska användas för att filtrera planerna på snabbfliken planer. Filtrera planerna så att du kan välja en delmängd av alla planposter så att du kan bekräfta delmängden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-127">Specifies the confirmation status to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="4d7fd-128">Annullera</span><span class="sxs-lookup"><span data-stu-id="4d7fd-128">Cancellation</span></span> | <span data-ttu-id="4d7fd-129">Anger annulleringsstatus som ska användas för att filtrera planerna på snabbfliken planer. Filtrera planerna så att du kan välja en delmängd av alla planposter så att du kan bekräfta delmängden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-129">Specifies the cancellation status to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="4d7fd-130">Filter för giltighetsdatum</span><span class="sxs-lookup"><span data-stu-id="4d7fd-130">Effective date filter</span></span> | <span data-ttu-id="4d7fd-131">Filtrerar planerna efter om de har förfallit, är aktiva eller kommer att vara aktiva i framtiden.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-131">Filters the plans based on whether they’re expired, active, or will be active in the future.</span></span> <span data-ttu-id="4d7fd-132">Markera kryssrutorna som motsvarar de planer som du vill visa på snabbfliken abonnemang på snabbfliken planer.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-132">Select the check boxes that correspond to the plans you want to see in the Plans fast tab.</span></span> |
   | <span data-ttu-id="4d7fd-133">Planer</span><span class="sxs-lookup"><span data-stu-id="4d7fd-133">Plans</span></span> | <span data-ttu-id="4d7fd-134">Fliken Planer innehåller de planer som uppfyller angivna filterkriterier.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-134">The Plans fast tab contains the plans that meet the filter criteria you specified.</span></span> <span data-ttu-id="4d7fd-135">De relevanta konfigurationsalternativen som har ställts in av personalen och de registreringar som valts av medarbetare tas med på varje rad.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-135">The relevant configuration options that were set by HR staff and the enrollment selections that were chosen by employees are included on each line.</span></span> <span data-ttu-id="4d7fd-136">I det kvalificerade fältet anges om det finns en valideringskonflikt med planurvalet.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-136">The Qualified field specifies whether there is a validation conflict with the plan selection.</span></span> |

4. <span data-ttu-id="4d7fd-137">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4d7fd-137">Select **Save**.</span></span>
