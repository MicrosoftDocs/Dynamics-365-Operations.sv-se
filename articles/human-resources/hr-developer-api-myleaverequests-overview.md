---
title: Översikt över MyLeaveRequests
description: MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f29d5cf1469b58b4ea1837dc82b9513f5c002609
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054966"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="afbb1-103">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="afbb1-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="afbb1-104">MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.</span><span class="sxs-lookup"><span data-stu-id="afbb1-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="afbb1-105">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="afbb1-105">Key</span></span>

  | <span data-ttu-id="afbb1-106">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="afbb1-106">Property Name</span></span> | <span data-ttu-id="afbb1-107">Datatyp</span><span class="sxs-lookup"><span data-stu-id="afbb1-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="afbb1-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="afbb1-108">dataAreaId</span></span>    | <span data-ttu-id="afbb1-109">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-109">String</span></span>    |
  | <span data-ttu-id="afbb1-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="afbb1-110">RequestId</span></span>     | <span data-ttu-id="afbb1-111">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-111">String</span></span>    |
  | <span data-ttu-id="afbb1-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="afbb1-112">LeaveType</span></span>     | <span data-ttu-id="afbb1-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-113">String</span></span>    |
  | <span data-ttu-id="afbb1-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="afbb1-114">LeaveDate</span></span>     | <span data-ttu-id="afbb1-115">Datum</span><span class="sxs-lookup"><span data-stu-id="afbb1-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="afbb1-116">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="afbb1-116">Properties</span></span>

  | <span data-ttu-id="afbb1-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="afbb1-117">Property Name</span></span>     | <span data-ttu-id="afbb1-118">Datatyp</span><span class="sxs-lookup"><span data-stu-id="afbb1-118">Data Type</span></span> | <span data-ttu-id="afbb1-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="afbb1-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="afbb1-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="afbb1-120">dataAreaId</span></span>        | <span data-ttu-id="afbb1-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-121">String</span></span>    | <span data-ttu-id="afbb1-122">X</span><span class="sxs-lookup"><span data-stu-id="afbb1-122">X</span></span>        |
  | <span data-ttu-id="afbb1-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="afbb1-123">RequestId</span></span>         | <span data-ttu-id="afbb1-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-124">String</span></span>    | <span data-ttu-id="afbb1-125">X</span><span class="sxs-lookup"><span data-stu-id="afbb1-125">X</span></span>        |
  | <span data-ttu-id="afbb1-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="afbb1-126">LeaveType</span></span>         | <span data-ttu-id="afbb1-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-127">String</span></span>    | <span data-ttu-id="afbb1-128">X</span><span class="sxs-lookup"><span data-stu-id="afbb1-128">X</span></span>        |
  | <span data-ttu-id="afbb1-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="afbb1-129">LeaveDate</span></span>         | <span data-ttu-id="afbb1-130">Datum</span><span class="sxs-lookup"><span data-stu-id="afbb1-130">Date</span></span>      | <span data-ttu-id="afbb1-131">X</span><span class="sxs-lookup"><span data-stu-id="afbb1-131">X</span></span>        |
  | <span data-ttu-id="afbb1-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="afbb1-132">ReasonCodeId</span></span>      | <span data-ttu-id="afbb1-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-133">String</span></span>    |          |
  | <span data-ttu-id="afbb1-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="afbb1-134">PersonnelNumber</span></span>   | <span data-ttu-id="afbb1-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-135">String</span></span>    | <span data-ttu-id="afbb1-136">X</span><span class="sxs-lookup"><span data-stu-id="afbb1-136">X</span></span>        |
  | <span data-ttu-id="afbb1-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="afbb1-137">RequestDate</span></span>       | <span data-ttu-id="afbb1-138">Datum</span><span class="sxs-lookup"><span data-stu-id="afbb1-138">Date</span></span>      | <span data-ttu-id="afbb1-139">X</span><span class="sxs-lookup"><span data-stu-id="afbb1-139">X</span></span>        |
  | <span data-ttu-id="afbb1-140">Kommentar</span><span class="sxs-lookup"><span data-stu-id="afbb1-140">Comment</span></span>           | <span data-ttu-id="afbb1-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="afbb1-141">String</span></span>    |          |
  | <span data-ttu-id="afbb1-142">Status</span><span class="sxs-lookup"><span data-stu-id="afbb1-142">Status</span></span>            | <span data-ttu-id="afbb1-143">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="afbb1-143">Enum</span></span>      | <span data-ttu-id="afbb1-144">X</span><span class="sxs-lookup"><span data-stu-id="afbb1-144">X</span></span>        |
  | <span data-ttu-id="afbb1-145">Tid</span><span class="sxs-lookup"><span data-stu-id="afbb1-145">Amount</span></span>            | <span data-ttu-id="afbb1-146">Realtal</span><span class="sxs-lookup"><span data-stu-id="afbb1-146">Real</span></span>      |          |
  | <span data-ttu-id="afbb1-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="afbb1-147">HalfDayDefinition</span></span> | <span data-ttu-id="afbb1-148">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="afbb1-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="afbb1-149">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="afbb1-149">Actions</span></span>

 | <span data-ttu-id="afbb1-150">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="afbb1-150">Action Name</span></span>                               | <span data-ttu-id="afbb1-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="afbb1-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="afbb1-152">skicka</span><span class="sxs-lookup"><span data-stu-id="afbb1-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="afbb1-153">Skicka begäran som ska bearbetas av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="afbb1-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="afbb1-154">Se även</span><span class="sxs-lookup"><span data-stu-id="afbb1-154">See also</span></span>

- [<span data-ttu-id="afbb1-155">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="afbb1-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="afbb1-156">Autentisering</span><span class="sxs-lookup"><span data-stu-id="afbb1-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]