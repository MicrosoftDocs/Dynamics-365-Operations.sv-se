---
title: Skapa en ledighetsansökan till arbetsflödet
description: Skapa ett arbetsflöde för tjänstledighet och ledighetsansökan om du vill hantera ledighetsansökningar på ett konsekvent sätt i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 209f0ec7236778cc0a828102e554b02206b45b73
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420528"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="f3b80-103">Skapa en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="f3b80-103">Create a leave request workflow</span></span>

<span data-ttu-id="f3b80-104">Du kan skapa ett arbetsflöde i Dynamics 365 Human Resources för att hantera ledighetsansökningar på ett konsekvent sätt.</span><span class="sxs-lookup"><span data-stu-id="f3b80-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="f3b80-105">Ett arbetsflöde för **tjänstledighet och frånvaro** gör att du kan:</span><span class="sxs-lookup"><span data-stu-id="f3b80-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="f3b80-106">Definiera uppgifter</span><span class="sxs-lookup"><span data-stu-id="f3b80-106">Define tasks</span></span>
- <span data-ttu-id="f3b80-107">Bestämma vem som måste utföra uppgifterna</span><span class="sxs-lookup"><span data-stu-id="f3b80-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="f3b80-108">Ange vem som kan godkänna eller avvisa begäranden</span><span class="sxs-lookup"><span data-stu-id="f3b80-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="f3b80-109">Skapa ett arbetsflöde för tjänstledighet och ledighetsansökan</span><span class="sxs-lookup"><span data-stu-id="f3b80-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="f3b80-110">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="f3b80-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="f3b80-111">Under **Inställningar**, välj **Personalarbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="f3b80-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="f3b80-112">Välj **ny** och välj sedan **tjänstledighets- och frånvaroansökningar**.</span><span class="sxs-lookup"><span data-stu-id="f3b80-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="f3b80-113">När meddelanderutan **Öppna den här filen?** visas väljer du **öppna** och loggar in med dina företagsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="f3b80-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="f3b80-114">Använd arbetsflödesredigeraren när du vill skapa ett arbetsflöde för dina tjänstledighetsansökan.</span><span class="sxs-lookup"><span data-stu-id="f3b80-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="f3b80-115">Mer information om hur du arbetar med arbetsflöden finns i [Skapa arbetsflöden - översikt](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="f3b80-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="f3b80-116">Arbetsflödesdataelement för tjänstledighet och ledighetsansökan</span><span class="sxs-lookup"><span data-stu-id="f3b80-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="f3b80-117">Du kan använda följande dataelement för att skapa villkorade eller automatiska godkännanden i arbetsflöden för tjänstledighets- och ledighetsansökningar:</span><span class="sxs-lookup"><span data-stu-id="f3b80-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="f3b80-118">**Belopp**</span><span class="sxs-lookup"><span data-stu-id="f3b80-118">**Amount**</span></span>
- <span data-ttu-id="f3b80-119">**Kommentar**</span><span class="sxs-lookup"><span data-stu-id="f3b80-119">**Comment**</span></span>
- <span data-ttu-id="f3b80-120">**Företag**</span><span class="sxs-lookup"><span data-stu-id="f3b80-120">**Company**</span></span>
- <span data-ttu-id="f3b80-121">**Skapades av**</span><span class="sxs-lookup"><span data-stu-id="f3b80-121">**Created by**</span></span>
- <span data-ttu-id="f3b80-122">**Skapat datum och klockslag**</span><span class="sxs-lookup"><span data-stu-id="f3b80-122">**Created date and time**</span></span>
- <span data-ttu-id="f3b80-123">**Slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f3b80-123">**End date**</span></span>
- <span data-ttu-id="f3b80-124">**Tjänstledighetstyp**</span><span class="sxs-lookup"><span data-stu-id="f3b80-124">**Leave type**</span></span>
- <span data-ttu-id="f3b80-125">**Ändrades av**</span><span class="sxs-lookup"><span data-stu-id="f3b80-125">**Modified by**</span></span>
- <span data-ttu-id="f3b80-126">**Datum och tid för ändring**</span><span class="sxs-lookup"><span data-stu-id="f3b80-126">**Modified date and time**</span></span>
- <span data-ttu-id="f3b80-127">**Orsakskod**</span><span class="sxs-lookup"><span data-stu-id="f3b80-127">**Reason code**</span></span>
- <span data-ttu-id="f3b80-128">**ID för begäran**</span><span class="sxs-lookup"><span data-stu-id="f3b80-128">**Request ID**</span></span>
- <span data-ttu-id="f3b80-129">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="f3b80-129">**Start date**</span></span>
- <span data-ttu-id="f3b80-130">**Status**</span><span class="sxs-lookup"><span data-stu-id="f3b80-130">**Status**</span></span> 
- <span data-ttu-id="f3b80-131">**Insändningsdatum**</span><span class="sxs-lookup"><span data-stu-id="f3b80-131">**Submission date**</span></span>
- <span data-ttu-id="f3b80-132">**Inskickad av**</span><span class="sxs-lookup"><span data-stu-id="f3b80-132">**Submitted by**</span></span>
- <span data-ttu-id="f3b80-133">**Skickad av HR**</span><span class="sxs-lookup"><span data-stu-id="f3b80-133">**Submitted by Human resources**</span></span>
- <span data-ttu-id="f3b80-134">**Skickad av chef**</span><span class="sxs-lookup"><span data-stu-id="f3b80-134">**Submitted by Manager**</span></span>
- <span data-ttu-id="f3b80-135">**Skickad för**</span><span class="sxs-lookup"><span data-stu-id="f3b80-135">**Submitted on behalf**</span></span>
- <span data-ttu-id="f3b80-136">**Arbetare**</span><span class="sxs-lookup"><span data-stu-id="f3b80-136">**Worker**</span></span>
- <span data-ttu-id="f3b80-137">**Typ av arbetare**</span><span class="sxs-lookup"><span data-stu-id="f3b80-137">**Worker type**</span></span>

<span data-ttu-id="f3b80-138">Exemplen visar hur du kan skapa olika typer av arbetsflödesvillkor genom att använda dessa dataelement:</span><span class="sxs-lookup"><span data-stu-id="f3b80-138">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="f3b80-139">Använd **Orsakskod** i en villkorssats för att vidarebefordra förfrågningar om sjukfrånvaro med orsakskoden **Kirurgiskt ingrepp** till HR för godkännande medan alla andra orsakskoder skickas till chefen.</span><span class="sxs-lookup"><span data-stu-id="f3b80-139">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="f3b80-140">Mer information om villkorssatser finns i [Konfigurera villkorliga beslut i arbetsflöde](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span><span class="sxs-lookup"><span data-stu-id="f3b80-140">For more information about conditional statements, see [Configure conditional decisions in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span></span> 

- <span data-ttu-id="f3b80-141">Använd **Skickad av HR** och **Skickad av chef** i en automatisk åtgärd för att automatiskt godkänna tjänstledighet som dessa roller skickar för medarbetares räkning.</span><span class="sxs-lookup"><span data-stu-id="f3b80-141">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="f3b80-142">Mer information om automatiska åtgärder finns i [Konfigurera godkännandeprocesser i arbetsflöde](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="f3b80-142">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="f3b80-143">Använd **Tjänstledighetstyp** i villkorssats eller automatisk åtgärd för att kontrollera hur arbetsflödet skickar förfrågningar gällande vissa tjänstledighetstyper.</span><span class="sxs-lookup"><span data-stu-id="f3b80-143">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3b80-144">Se även</span><span class="sxs-lookup"><span data-stu-id="f3b80-144">See also</span></span>

- [<span data-ttu-id="f3b80-145">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="f3b80-145">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
