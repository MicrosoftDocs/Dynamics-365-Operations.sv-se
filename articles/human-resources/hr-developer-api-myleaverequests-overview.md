---
title: Översikt över MyLeaveRequests
description: MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115546"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="66267-103">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="66267-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="66267-104">MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.</span><span class="sxs-lookup"><span data-stu-id="66267-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="66267-105">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="66267-105">Key</span></span>

  | <span data-ttu-id="66267-106">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="66267-106">Property Name</span></span> | <span data-ttu-id="66267-107">Datatyp</span><span class="sxs-lookup"><span data-stu-id="66267-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="66267-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="66267-108">dataAreaId</span></span>    | <span data-ttu-id="66267-109">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-109">String</span></span>    |
  | <span data-ttu-id="66267-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="66267-110">RequestId</span></span>     | <span data-ttu-id="66267-111">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-111">String</span></span>    |
  | <span data-ttu-id="66267-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="66267-112">LeaveType</span></span>     | <span data-ttu-id="66267-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-113">String</span></span>    |
  | <span data-ttu-id="66267-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="66267-114">LeaveDate</span></span>     | <span data-ttu-id="66267-115">Datum</span><span class="sxs-lookup"><span data-stu-id="66267-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="66267-116">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="66267-116">Properties</span></span>

  | <span data-ttu-id="66267-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="66267-117">Property Name</span></span>     | <span data-ttu-id="66267-118">Datatyp</span><span class="sxs-lookup"><span data-stu-id="66267-118">Data Type</span></span> | <span data-ttu-id="66267-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="66267-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="66267-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="66267-120">dataAreaId</span></span>        | <span data-ttu-id="66267-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-121">String</span></span>    | <span data-ttu-id="66267-122">X</span><span class="sxs-lookup"><span data-stu-id="66267-122">X</span></span>        |
  | <span data-ttu-id="66267-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="66267-123">RequestId</span></span>         | <span data-ttu-id="66267-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-124">String</span></span>    | <span data-ttu-id="66267-125">X</span><span class="sxs-lookup"><span data-stu-id="66267-125">X</span></span>        |
  | <span data-ttu-id="66267-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="66267-126">LeaveType</span></span>         | <span data-ttu-id="66267-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-127">String</span></span>    | <span data-ttu-id="66267-128">X</span><span class="sxs-lookup"><span data-stu-id="66267-128">X</span></span>        |
  | <span data-ttu-id="66267-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="66267-129">LeaveDate</span></span>         | <span data-ttu-id="66267-130">Datum</span><span class="sxs-lookup"><span data-stu-id="66267-130">Date</span></span>      | <span data-ttu-id="66267-131">X</span><span class="sxs-lookup"><span data-stu-id="66267-131">X</span></span>        |
  | <span data-ttu-id="66267-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="66267-132">ReasonCodeId</span></span>      | <span data-ttu-id="66267-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-133">String</span></span>    |          |
  | <span data-ttu-id="66267-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="66267-134">PersonnelNumber</span></span>   | <span data-ttu-id="66267-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-135">String</span></span>    | <span data-ttu-id="66267-136">X</span><span class="sxs-lookup"><span data-stu-id="66267-136">X</span></span>        |
  | <span data-ttu-id="66267-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="66267-137">RequestDate</span></span>       | <span data-ttu-id="66267-138">Datum</span><span class="sxs-lookup"><span data-stu-id="66267-138">Date</span></span>      | <span data-ttu-id="66267-139">X</span><span class="sxs-lookup"><span data-stu-id="66267-139">X</span></span>        |
  | <span data-ttu-id="66267-140">Kommentar</span><span class="sxs-lookup"><span data-stu-id="66267-140">Comment</span></span>           | <span data-ttu-id="66267-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="66267-141">String</span></span>    |          |
  | <span data-ttu-id="66267-142">Status</span><span class="sxs-lookup"><span data-stu-id="66267-142">Status</span></span>            | <span data-ttu-id="66267-143">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="66267-143">Enum</span></span>      | <span data-ttu-id="66267-144">X</span><span class="sxs-lookup"><span data-stu-id="66267-144">X</span></span>        |
  | <span data-ttu-id="66267-145">Tid</span><span class="sxs-lookup"><span data-stu-id="66267-145">Amount</span></span>            | <span data-ttu-id="66267-146">Realtal</span><span class="sxs-lookup"><span data-stu-id="66267-146">Real</span></span>      |          |
  | <span data-ttu-id="66267-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="66267-147">HalfDayDefinition</span></span> | <span data-ttu-id="66267-148">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="66267-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="66267-149">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="66267-149">Actions</span></span>

 | <span data-ttu-id="66267-150">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="66267-150">Action Name</span></span>                               | <span data-ttu-id="66267-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="66267-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="66267-152">skicka</span><span class="sxs-lookup"><span data-stu-id="66267-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="66267-153">Skicka begäran som ska bearbetas av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="66267-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="66267-154">Se även</span><span class="sxs-lookup"><span data-stu-id="66267-154">See also</span></span>

- [<span data-ttu-id="66267-155">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="66267-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="66267-156">Autentisering</span><span class="sxs-lookup"><span data-stu-id="66267-156">Authentication</span></span>](hr-developer-api-authentication.md)