---
title: Översikt över MyLeaveRequests
description: MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092047"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="2db8e-103">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="2db8e-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="2db8e-104">MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.</span><span class="sxs-lookup"><span data-stu-id="2db8e-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="2db8e-105">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="2db8e-105">Key</span></span>

  | <span data-ttu-id="2db8e-106">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="2db8e-106">Property Name</span></span> | <span data-ttu-id="2db8e-107">Datatyp</span><span class="sxs-lookup"><span data-stu-id="2db8e-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="2db8e-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="2db8e-108">dataAreaId</span></span>    | <span data-ttu-id="2db8e-109">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-109">String</span></span>    |
  | <span data-ttu-id="2db8e-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="2db8e-110">RequestId</span></span>     | <span data-ttu-id="2db8e-111">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-111">String</span></span>    |
  | <span data-ttu-id="2db8e-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="2db8e-112">LeaveType</span></span>     | <span data-ttu-id="2db8e-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-113">String</span></span>    |
  | <span data-ttu-id="2db8e-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="2db8e-114">LeaveDate</span></span>     | <span data-ttu-id="2db8e-115">Datum</span><span class="sxs-lookup"><span data-stu-id="2db8e-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="2db8e-116">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="2db8e-116">Properties</span></span>

  | <span data-ttu-id="2db8e-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="2db8e-117">Property Name</span></span>     | <span data-ttu-id="2db8e-118">Datatyp</span><span class="sxs-lookup"><span data-stu-id="2db8e-118">Data Type</span></span> | <span data-ttu-id="2db8e-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="2db8e-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="2db8e-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="2db8e-120">dataAreaId</span></span>        | <span data-ttu-id="2db8e-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-121">String</span></span>    | <span data-ttu-id="2db8e-122">X</span><span class="sxs-lookup"><span data-stu-id="2db8e-122">X</span></span>        |
  | <span data-ttu-id="2db8e-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="2db8e-123">RequestId</span></span>         | <span data-ttu-id="2db8e-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-124">String</span></span>    | <span data-ttu-id="2db8e-125">X</span><span class="sxs-lookup"><span data-stu-id="2db8e-125">X</span></span>        |
  | <span data-ttu-id="2db8e-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="2db8e-126">LeaveType</span></span>         | <span data-ttu-id="2db8e-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-127">String</span></span>    | <span data-ttu-id="2db8e-128">X</span><span class="sxs-lookup"><span data-stu-id="2db8e-128">X</span></span>        |
  | <span data-ttu-id="2db8e-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="2db8e-129">LeaveDate</span></span>         | <span data-ttu-id="2db8e-130">Datum</span><span class="sxs-lookup"><span data-stu-id="2db8e-130">Date</span></span>      | <span data-ttu-id="2db8e-131">X</span><span class="sxs-lookup"><span data-stu-id="2db8e-131">X</span></span>        |
  | <span data-ttu-id="2db8e-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="2db8e-132">ReasonCodeId</span></span>      | <span data-ttu-id="2db8e-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-133">String</span></span>    |          |
  | <span data-ttu-id="2db8e-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="2db8e-134">PersonnelNumber</span></span>   | <span data-ttu-id="2db8e-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-135">String</span></span>    | <span data-ttu-id="2db8e-136">X</span><span class="sxs-lookup"><span data-stu-id="2db8e-136">X</span></span>        |
  | <span data-ttu-id="2db8e-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="2db8e-137">RequestDate</span></span>       | <span data-ttu-id="2db8e-138">Datum</span><span class="sxs-lookup"><span data-stu-id="2db8e-138">Date</span></span>      | <span data-ttu-id="2db8e-139">X</span><span class="sxs-lookup"><span data-stu-id="2db8e-139">X</span></span>        |
  | <span data-ttu-id="2db8e-140">Kommentar</span><span class="sxs-lookup"><span data-stu-id="2db8e-140">Comment</span></span>           | <span data-ttu-id="2db8e-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="2db8e-141">String</span></span>    |          |
  | <span data-ttu-id="2db8e-142">Status</span><span class="sxs-lookup"><span data-stu-id="2db8e-142">Status</span></span>            | <span data-ttu-id="2db8e-143">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="2db8e-143">Enum</span></span>      | <span data-ttu-id="2db8e-144">X</span><span class="sxs-lookup"><span data-stu-id="2db8e-144">X</span></span>        |
  | <span data-ttu-id="2db8e-145">Tid</span><span class="sxs-lookup"><span data-stu-id="2db8e-145">Amount</span></span>            | <span data-ttu-id="2db8e-146">Realtal</span><span class="sxs-lookup"><span data-stu-id="2db8e-146">Real</span></span>      |          |
  | <span data-ttu-id="2db8e-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="2db8e-147">HalfDayDefinition</span></span> | <span data-ttu-id="2db8e-148">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="2db8e-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="2db8e-149">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="2db8e-149">Actions</span></span>

 | <span data-ttu-id="2db8e-150">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="2db8e-150">Action Name</span></span>                               | <span data-ttu-id="2db8e-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2db8e-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="2db8e-152">skicka</span><span class="sxs-lookup"><span data-stu-id="2db8e-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="2db8e-153">Skicka begäran som ska bearbetas av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="2db8e-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2db8e-154">Se även</span><span class="sxs-lookup"><span data-stu-id="2db8e-154">See also</span></span>

- [<span data-ttu-id="2db8e-155">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="2db8e-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="2db8e-156">Autentisering</span><span class="sxs-lookup"><span data-stu-id="2db8e-156">Authentication</span></span>](hr-developer-api-authentication.md)