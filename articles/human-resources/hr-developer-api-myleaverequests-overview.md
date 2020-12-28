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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420521"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="d5f4b-103">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="d5f4b-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="d5f4b-104">MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.</span><span class="sxs-lookup"><span data-stu-id="d5f4b-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="d5f4b-105">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="d5f4b-105">Key</span></span>

  | <span data-ttu-id="d5f4b-106">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="d5f4b-106">Property Name</span></span> | <span data-ttu-id="d5f4b-107">Datatyp</span><span class="sxs-lookup"><span data-stu-id="d5f4b-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="d5f4b-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="d5f4b-108">dataAreaId</span></span>    | <span data-ttu-id="d5f4b-109">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-109">String</span></span>    |
  | <span data-ttu-id="d5f4b-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="d5f4b-110">RequestId</span></span>     | <span data-ttu-id="d5f4b-111">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-111">String</span></span>    |
  | <span data-ttu-id="d5f4b-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="d5f4b-112">LeaveType</span></span>     | <span data-ttu-id="d5f4b-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-113">String</span></span>    |
  | <span data-ttu-id="d5f4b-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="d5f4b-114">LeaveDate</span></span>     | <span data-ttu-id="d5f4b-115">Datum</span><span class="sxs-lookup"><span data-stu-id="d5f4b-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="d5f4b-116">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="d5f4b-116">Properties</span></span>

  | <span data-ttu-id="d5f4b-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="d5f4b-117">Property Name</span></span>     | <span data-ttu-id="d5f4b-118">Datatyp</span><span class="sxs-lookup"><span data-stu-id="d5f4b-118">Data Type</span></span> | <span data-ttu-id="d5f4b-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="d5f4b-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="d5f4b-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="d5f4b-120">dataAreaId</span></span>        | <span data-ttu-id="d5f4b-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-121">String</span></span>    | <span data-ttu-id="d5f4b-122">X</span><span class="sxs-lookup"><span data-stu-id="d5f4b-122">X</span></span>        |
  | <span data-ttu-id="d5f4b-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="d5f4b-123">RequestId</span></span>         | <span data-ttu-id="d5f4b-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-124">String</span></span>    | <span data-ttu-id="d5f4b-125">X</span><span class="sxs-lookup"><span data-stu-id="d5f4b-125">X</span></span>        |
  | <span data-ttu-id="d5f4b-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="d5f4b-126">LeaveType</span></span>         | <span data-ttu-id="d5f4b-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-127">String</span></span>    | <span data-ttu-id="d5f4b-128">X</span><span class="sxs-lookup"><span data-stu-id="d5f4b-128">X</span></span>        |
  | <span data-ttu-id="d5f4b-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="d5f4b-129">LeaveDate</span></span>         | <span data-ttu-id="d5f4b-130">Datum</span><span class="sxs-lookup"><span data-stu-id="d5f4b-130">Date</span></span>      | <span data-ttu-id="d5f4b-131">X</span><span class="sxs-lookup"><span data-stu-id="d5f4b-131">X</span></span>        |
  | <span data-ttu-id="d5f4b-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="d5f4b-132">ReasonCodeId</span></span>      | <span data-ttu-id="d5f4b-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-133">String</span></span>    |          |
  | <span data-ttu-id="d5f4b-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="d5f4b-134">PersonnelNumber</span></span>   | <span data-ttu-id="d5f4b-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-135">String</span></span>    | <span data-ttu-id="d5f4b-136">X</span><span class="sxs-lookup"><span data-stu-id="d5f4b-136">X</span></span>        |
  | <span data-ttu-id="d5f4b-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="d5f4b-137">RequestDate</span></span>       | <span data-ttu-id="d5f4b-138">Datum</span><span class="sxs-lookup"><span data-stu-id="d5f4b-138">Date</span></span>      | <span data-ttu-id="d5f4b-139">X</span><span class="sxs-lookup"><span data-stu-id="d5f4b-139">X</span></span>        |
  | <span data-ttu-id="d5f4b-140">Kommentar</span><span class="sxs-lookup"><span data-stu-id="d5f4b-140">Comment</span></span>           | <span data-ttu-id="d5f4b-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="d5f4b-141">String</span></span>    |          |
  | <span data-ttu-id="d5f4b-142">Status</span><span class="sxs-lookup"><span data-stu-id="d5f4b-142">Status</span></span>            | <span data-ttu-id="d5f4b-143">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="d5f4b-143">Enum</span></span>      | <span data-ttu-id="d5f4b-144">X</span><span class="sxs-lookup"><span data-stu-id="d5f4b-144">X</span></span>        |
  | <span data-ttu-id="d5f4b-145">Tid</span><span class="sxs-lookup"><span data-stu-id="d5f4b-145">Amount</span></span>            | <span data-ttu-id="d5f4b-146">Realtal</span><span class="sxs-lookup"><span data-stu-id="d5f4b-146">Real</span></span>      |          |
  | <span data-ttu-id="d5f4b-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="d5f4b-147">HalfDayDefinition</span></span> | <span data-ttu-id="d5f4b-148">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="d5f4b-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="d5f4b-149">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="d5f4b-149">Actions</span></span>

 | <span data-ttu-id="d5f4b-150">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="d5f4b-150">Action Name</span></span>                               | <span data-ttu-id="d5f4b-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d5f4b-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="d5f4b-152">skicka</span><span class="sxs-lookup"><span data-stu-id="d5f4b-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="d5f4b-153">Skicka begäran som ska bearbetas av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d5f4b-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d5f4b-154">Se även</span><span class="sxs-lookup"><span data-stu-id="d5f4b-154">See also</span></span>

- [<span data-ttu-id="d5f4b-155">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="d5f4b-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="d5f4b-156">Autentisering</span><span class="sxs-lookup"><span data-stu-id="d5f4b-156">Authentication</span></span>](hr-developer-api-authentication.md)