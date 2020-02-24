---
title: Översikt över MyLeaveRequests
description: ''
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
ms.openlocfilehash: 66f161d6736b1bb544d02871d9d51b2949b1cfa0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010595"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="b634e-102">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="b634e-102">MyLeaveRequests overview</span></span>

<span data-ttu-id="b634e-103">MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.</span><span class="sxs-lookup"><span data-stu-id="b634e-103">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="b634e-104">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="b634e-104">Key</span></span>

  | <span data-ttu-id="b634e-105">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="b634e-105">Property Name</span></span> | <span data-ttu-id="b634e-106">Datatyp</span><span class="sxs-lookup"><span data-stu-id="b634e-106">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="b634e-107">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="b634e-107">dataAreaId</span></span>    | <span data-ttu-id="b634e-108">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-108">String</span></span>    |
  | <span data-ttu-id="b634e-109">RequestId</span><span class="sxs-lookup"><span data-stu-id="b634e-109">RequestId</span></span>     | <span data-ttu-id="b634e-110">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-110">String</span></span>    |
  | <span data-ttu-id="b634e-111">LeaveType</span><span class="sxs-lookup"><span data-stu-id="b634e-111">LeaveType</span></span>     | <span data-ttu-id="b634e-112">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-112">String</span></span>    |
  | <span data-ttu-id="b634e-113">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="b634e-113">LeaveDate</span></span>     | <span data-ttu-id="b634e-114">Datum</span><span class="sxs-lookup"><span data-stu-id="b634e-114">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="b634e-115">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="b634e-115">Properties</span></span>

  | <span data-ttu-id="b634e-116">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="b634e-116">Property Name</span></span>     | <span data-ttu-id="b634e-117">Datatyp</span><span class="sxs-lookup"><span data-stu-id="b634e-117">Data Type</span></span> | <span data-ttu-id="b634e-118">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="b634e-118">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="b634e-119">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="b634e-119">dataAreaId</span></span>        | <span data-ttu-id="b634e-120">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-120">String</span></span>    | <span data-ttu-id="b634e-121">X</span><span class="sxs-lookup"><span data-stu-id="b634e-121">X</span></span>        |
  | <span data-ttu-id="b634e-122">RequestId</span><span class="sxs-lookup"><span data-stu-id="b634e-122">RequestId</span></span>         | <span data-ttu-id="b634e-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-123">String</span></span>    | <span data-ttu-id="b634e-124">X</span><span class="sxs-lookup"><span data-stu-id="b634e-124">X</span></span>        |
  | <span data-ttu-id="b634e-125">LeaveType</span><span class="sxs-lookup"><span data-stu-id="b634e-125">LeaveType</span></span>         | <span data-ttu-id="b634e-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-126">String</span></span>    | <span data-ttu-id="b634e-127">X</span><span class="sxs-lookup"><span data-stu-id="b634e-127">X</span></span>        |
  | <span data-ttu-id="b634e-128">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="b634e-128">LeaveDate</span></span>         | <span data-ttu-id="b634e-129">Datum</span><span class="sxs-lookup"><span data-stu-id="b634e-129">Date</span></span>      | <span data-ttu-id="b634e-130">X</span><span class="sxs-lookup"><span data-stu-id="b634e-130">X</span></span>        |
  | <span data-ttu-id="b634e-131">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="b634e-131">ReasonCodeId</span></span>      | <span data-ttu-id="b634e-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-132">String</span></span>    |          |
  | <span data-ttu-id="b634e-133">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="b634e-133">PersonnelNumber</span></span>   | <span data-ttu-id="b634e-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-134">String</span></span>    | <span data-ttu-id="b634e-135">X</span><span class="sxs-lookup"><span data-stu-id="b634e-135">X</span></span>        |
  | <span data-ttu-id="b634e-136">RequestDate</span><span class="sxs-lookup"><span data-stu-id="b634e-136">RequestDate</span></span>       | <span data-ttu-id="b634e-137">Datum</span><span class="sxs-lookup"><span data-stu-id="b634e-137">Date</span></span>      | <span data-ttu-id="b634e-138">X</span><span class="sxs-lookup"><span data-stu-id="b634e-138">X</span></span>        |
  | <span data-ttu-id="b634e-139">Kommentar</span><span class="sxs-lookup"><span data-stu-id="b634e-139">Comment</span></span>           | <span data-ttu-id="b634e-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="b634e-140">String</span></span>    |          |
  | <span data-ttu-id="b634e-141">Status</span><span class="sxs-lookup"><span data-stu-id="b634e-141">Status</span></span>            | <span data-ttu-id="b634e-142">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="b634e-142">Enum</span></span>      | <span data-ttu-id="b634e-143">X</span><span class="sxs-lookup"><span data-stu-id="b634e-143">X</span></span>        |
  | <span data-ttu-id="b634e-144">Tid</span><span class="sxs-lookup"><span data-stu-id="b634e-144">Amount</span></span>            | <span data-ttu-id="b634e-145">Realtal</span><span class="sxs-lookup"><span data-stu-id="b634e-145">Real</span></span>      |          |
  | <span data-ttu-id="b634e-146">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="b634e-146">HalfDayDefinition</span></span> | <span data-ttu-id="b634e-147">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="b634e-147">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="b634e-148">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="b634e-148">Actions</span></span>

 | <span data-ttu-id="b634e-149">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="b634e-149">Action Name</span></span>                               | <span data-ttu-id="b634e-150">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b634e-150">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="b634e-151">skicka</span><span class="sxs-lookup"><span data-stu-id="b634e-151">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="b634e-152">Skicka begäran som ska bearbetas av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="b634e-152">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b634e-153">Se även</span><span class="sxs-lookup"><span data-stu-id="b634e-153">See also</span></span>

- [<span data-ttu-id="b634e-154">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="b634e-154">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="b634e-155">Autentisering</span><span class="sxs-lookup"><span data-stu-id="b634e-155">Authentication</span></span>](hr-developer-api-authentication.md)