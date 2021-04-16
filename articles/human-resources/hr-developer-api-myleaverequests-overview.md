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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803643"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="84a58-103">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="84a58-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="84a58-104">MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.</span><span class="sxs-lookup"><span data-stu-id="84a58-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="84a58-105">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="84a58-105">Key</span></span>

  | <span data-ttu-id="84a58-106">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="84a58-106">Property Name</span></span> | <span data-ttu-id="84a58-107">Datatyp</span><span class="sxs-lookup"><span data-stu-id="84a58-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="84a58-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="84a58-108">dataAreaId</span></span>    | <span data-ttu-id="84a58-109">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-109">String</span></span>    |
  | <span data-ttu-id="84a58-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="84a58-110">RequestId</span></span>     | <span data-ttu-id="84a58-111">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-111">String</span></span>    |
  | <span data-ttu-id="84a58-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="84a58-112">LeaveType</span></span>     | <span data-ttu-id="84a58-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-113">String</span></span>    |
  | <span data-ttu-id="84a58-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="84a58-114">LeaveDate</span></span>     | <span data-ttu-id="84a58-115">Datum</span><span class="sxs-lookup"><span data-stu-id="84a58-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="84a58-116">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="84a58-116">Properties</span></span>

  | <span data-ttu-id="84a58-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="84a58-117">Property Name</span></span>     | <span data-ttu-id="84a58-118">Datatyp</span><span class="sxs-lookup"><span data-stu-id="84a58-118">Data Type</span></span> | <span data-ttu-id="84a58-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="84a58-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="84a58-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="84a58-120">dataAreaId</span></span>        | <span data-ttu-id="84a58-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-121">String</span></span>    | <span data-ttu-id="84a58-122">X</span><span class="sxs-lookup"><span data-stu-id="84a58-122">X</span></span>        |
  | <span data-ttu-id="84a58-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="84a58-123">RequestId</span></span>         | <span data-ttu-id="84a58-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-124">String</span></span>    | <span data-ttu-id="84a58-125">X</span><span class="sxs-lookup"><span data-stu-id="84a58-125">X</span></span>        |
  | <span data-ttu-id="84a58-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="84a58-126">LeaveType</span></span>         | <span data-ttu-id="84a58-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-127">String</span></span>    | <span data-ttu-id="84a58-128">X</span><span class="sxs-lookup"><span data-stu-id="84a58-128">X</span></span>        |
  | <span data-ttu-id="84a58-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="84a58-129">LeaveDate</span></span>         | <span data-ttu-id="84a58-130">Datum</span><span class="sxs-lookup"><span data-stu-id="84a58-130">Date</span></span>      | <span data-ttu-id="84a58-131">X</span><span class="sxs-lookup"><span data-stu-id="84a58-131">X</span></span>        |
  | <span data-ttu-id="84a58-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="84a58-132">ReasonCodeId</span></span>      | <span data-ttu-id="84a58-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-133">String</span></span>    |          |
  | <span data-ttu-id="84a58-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="84a58-134">PersonnelNumber</span></span>   | <span data-ttu-id="84a58-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-135">String</span></span>    | <span data-ttu-id="84a58-136">X</span><span class="sxs-lookup"><span data-stu-id="84a58-136">X</span></span>        |
  | <span data-ttu-id="84a58-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="84a58-137">RequestDate</span></span>       | <span data-ttu-id="84a58-138">Datum</span><span class="sxs-lookup"><span data-stu-id="84a58-138">Date</span></span>      | <span data-ttu-id="84a58-139">X</span><span class="sxs-lookup"><span data-stu-id="84a58-139">X</span></span>        |
  | <span data-ttu-id="84a58-140">Kommentar</span><span class="sxs-lookup"><span data-stu-id="84a58-140">Comment</span></span>           | <span data-ttu-id="84a58-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="84a58-141">String</span></span>    |          |
  | <span data-ttu-id="84a58-142">Status</span><span class="sxs-lookup"><span data-stu-id="84a58-142">Status</span></span>            | <span data-ttu-id="84a58-143">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="84a58-143">Enum</span></span>      | <span data-ttu-id="84a58-144">X</span><span class="sxs-lookup"><span data-stu-id="84a58-144">X</span></span>        |
  | <span data-ttu-id="84a58-145">Tid</span><span class="sxs-lookup"><span data-stu-id="84a58-145">Amount</span></span>            | <span data-ttu-id="84a58-146">Realtal</span><span class="sxs-lookup"><span data-stu-id="84a58-146">Real</span></span>      |          |
  | <span data-ttu-id="84a58-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="84a58-147">HalfDayDefinition</span></span> | <span data-ttu-id="84a58-148">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="84a58-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="84a58-149">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="84a58-149">Actions</span></span>

 | <span data-ttu-id="84a58-150">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="84a58-150">Action Name</span></span>                               | <span data-ttu-id="84a58-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="84a58-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="84a58-152">skicka</span><span class="sxs-lookup"><span data-stu-id="84a58-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="84a58-153">Skicka begäran som ska bearbetas av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="84a58-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="84a58-154">Se även</span><span class="sxs-lookup"><span data-stu-id="84a58-154">See also</span></span>

- [<span data-ttu-id="84a58-155">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="84a58-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="84a58-156">Autentisering</span><span class="sxs-lookup"><span data-stu-id="84a58-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]