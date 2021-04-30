---
title: Skapa ett arbetsflöde för köpa och sälja ledighetsansökan
description: Skapa ett arbetsflöde för köpa och sälja ledighetsansökan om du vill hantera köpa och sälja ledighetsansökan på konsekvent sätt i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15cedc16fbdbb5d25daa262f094a56bb8fe2f5cc
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892715"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="3a602-103">Skapa ett arbetsflöde för köpa och sälja ledighetsansökan</span><span class="sxs-lookup"><span data-stu-id="3a602-103">Create a buy and sell leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3a602-104">Du kan skapa ett arbetsflöde i Dynamics 365 Human Resources för att hantera köpa och sälja ledighetsansökan konsekvent sätt.</span><span class="sxs-lookup"><span data-stu-id="3a602-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="3a602-105">Ett arbetsflöde för **köpa och sälja ledighet** gör att du kan:</span><span class="sxs-lookup"><span data-stu-id="3a602-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="3a602-106">Definiera uppgifter</span><span class="sxs-lookup"><span data-stu-id="3a602-106">Define tasks</span></span>
- <span data-ttu-id="3a602-107">Bestämma vem som måste utföra uppgifterna</span><span class="sxs-lookup"><span data-stu-id="3a602-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="3a602-108">Ange vem som kan godkänna eller avvisa begäranden</span><span class="sxs-lookup"><span data-stu-id="3a602-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="3a602-109">Skapa ett arbetsflöde för köpa och sälja ledighetsansökan</span><span class="sxs-lookup"><span data-stu-id="3a602-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="3a602-110">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="3a602-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="3a602-111">Under **Inställningar**, välj **Personalarbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="3a602-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="3a602-112">Välj **ny** och välj sedan **köpa och sälja ledighetsansökan**.</span><span class="sxs-lookup"><span data-stu-id="3a602-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="3a602-113">När meddelanderutan **Öppna den här filen?** visas väljer du **öppna** och loggar in med dina företagsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3a602-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="3a602-114">Använd arbetsflödesredigeraren när du vill skapa ett arbetsflöde för dina tjänstledighetsansökan.</span><span class="sxs-lookup"><span data-stu-id="3a602-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="3a602-115">Mer information om hur du arbetar med arbetsflöden finns i [Skapa arbetsflöden – översikt](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span><span class="sxs-lookup"><span data-stu-id="3a602-115">For more information about working with workflows, see [Create workflows overview](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="3a602-116">Arbetsflödesdataelement för tjänstledighet och ledighetsansökan</span><span class="sxs-lookup"><span data-stu-id="3a602-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="3a602-117">Du kan använda följande dataelement för att skapa villkorade eller automatiska godkännanden i arbetsflöden för köpa och sälja ledighetsansökan:</span><span class="sxs-lookup"><span data-stu-id="3a602-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="3a602-118">**Belopp**</span><span class="sxs-lookup"><span data-stu-id="3a602-118">**Amount**</span></span>
- <span data-ttu-id="3a602-119">**Policy för att köpa och sälja tjänstledighet**</span><span class="sxs-lookup"><span data-stu-id="3a602-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="3a602-120">**Företag**</span><span class="sxs-lookup"><span data-stu-id="3a602-120">**Company**</span></span>
- <span data-ttu-id="3a602-121">**Skapat av**</span><span class="sxs-lookup"><span data-stu-id="3a602-121">**Created by**</span></span>
- <span data-ttu-id="3a602-122">**Skapades datum och klockslag**</span><span class="sxs-lookup"><span data-stu-id="3a602-122">**Created date and time**</span></span>
- <span data-ttu-id="3a602-123">**Slutdatum**</span><span class="sxs-lookup"><span data-stu-id="3a602-123">**End date**</span></span>
- <span data-ttu-id="3a602-124">**Tjänstledighetstyp**</span><span class="sxs-lookup"><span data-stu-id="3a602-124">**Leave type**</span></span>
- <span data-ttu-id="3a602-125">**Ändrades av**</span><span class="sxs-lookup"><span data-stu-id="3a602-125">**Modified by**</span></span>
- <span data-ttu-id="3a602-126">**Datum och tid för ändring**</span><span class="sxs-lookup"><span data-stu-id="3a602-126">**Modified date and time**</span></span>
- <span data-ttu-id="3a602-127">**ID för begäran**</span><span class="sxs-lookup"><span data-stu-id="3a602-127">**Request ID**</span></span>
- <span data-ttu-id="3a602-128">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="3a602-128">**Start date**</span></span>
- <span data-ttu-id="3a602-129">**Status**</span><span class="sxs-lookup"><span data-stu-id="3a602-129">**Status**</span></span> 
- <span data-ttu-id="3a602-130">**Insändningsdatum**</span><span class="sxs-lookup"><span data-stu-id="3a602-130">**Submission date**</span></span>
- <span data-ttu-id="3a602-131">**Inskickad av**</span><span class="sxs-lookup"><span data-stu-id="3a602-131">**Submitted by**</span></span>
- <span data-ttu-id="3a602-132">**Skickad av HR**</span><span class="sxs-lookup"><span data-stu-id="3a602-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="3a602-133">**Skickad av chef**</span><span class="sxs-lookup"><span data-stu-id="3a602-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="3a602-134">**Skickad för**</span><span class="sxs-lookup"><span data-stu-id="3a602-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="3a602-135">**Arbetare**</span><span class="sxs-lookup"><span data-stu-id="3a602-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="3a602-136">Exempel på arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="3a602-136">Workflow examples</span></span>

<span data-ttu-id="3a602-137">Exemplen visar hur du kan skapa olika typer av arbetsflödesvillkor genom att använda dessa dataelement:</span><span class="sxs-lookup"><span data-stu-id="3a602-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="3a602-138">Använd **Skickad av HR** och **Skickad av chef** i en automatisk åtgärd för att automatiskt godkänna köpa och sälja ledighetsansökan som dessa roller skickar för medarbetares räkning.</span><span class="sxs-lookup"><span data-stu-id="3a602-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="3a602-139">Mer information om automatiska åtgärder finns i [Konfigurera godkännandeprocesser i arbetsflöde](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="3a602-139">For more information about automatic actions, see [Configure approval processes in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span></span>

- <span data-ttu-id="3a602-140">Använd **Tjänstledighetstyp** i villkorssats eller automatisk åtgärd för att kontrollera hur arbetsflödet skickar förfrågningar gällande vissa tjänstledighetstyper.</span><span class="sxs-lookup"><span data-stu-id="3a602-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a602-141">Se även</span><span class="sxs-lookup"><span data-stu-id="3a602-141">See also</span></span>

[<span data-ttu-id="3a602-142">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="3a602-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="3a602-143">Hantera principer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="3a602-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]