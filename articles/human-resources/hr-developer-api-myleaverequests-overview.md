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
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465520"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="4b65e-103">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="4b65e-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4b65e-104">MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.</span><span class="sxs-lookup"><span data-stu-id="4b65e-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="4b65e-105">Nyckelord</span><span class="sxs-lookup"><span data-stu-id="4b65e-105">Key</span></span>

  | <span data-ttu-id="4b65e-106">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="4b65e-106">Property Name</span></span> | <span data-ttu-id="4b65e-107">Datatyp</span><span class="sxs-lookup"><span data-stu-id="4b65e-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="4b65e-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="4b65e-108">dataAreaId</span></span>    | <span data-ttu-id="4b65e-109">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-109">String</span></span>    |
  | <span data-ttu-id="4b65e-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="4b65e-110">RequestId</span></span>     | <span data-ttu-id="4b65e-111">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-111">String</span></span>    |
  | <span data-ttu-id="4b65e-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="4b65e-112">LeaveType</span></span>     | <span data-ttu-id="4b65e-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-113">String</span></span>    |
  | <span data-ttu-id="4b65e-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="4b65e-114">LeaveDate</span></span>     | <span data-ttu-id="4b65e-115">Datum</span><span class="sxs-lookup"><span data-stu-id="4b65e-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="4b65e-116">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="4b65e-116">Properties</span></span>

  | <span data-ttu-id="4b65e-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="4b65e-117">Property Name</span></span>     | <span data-ttu-id="4b65e-118">Datatyp</span><span class="sxs-lookup"><span data-stu-id="4b65e-118">Data Type</span></span> | <span data-ttu-id="4b65e-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="4b65e-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="4b65e-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="4b65e-120">dataAreaId</span></span>        | <span data-ttu-id="4b65e-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-121">String</span></span>    | <span data-ttu-id="4b65e-122">X</span><span class="sxs-lookup"><span data-stu-id="4b65e-122">X</span></span>        |
  | <span data-ttu-id="4b65e-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="4b65e-123">RequestId</span></span>         | <span data-ttu-id="4b65e-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-124">String</span></span>    | <span data-ttu-id="4b65e-125">X</span><span class="sxs-lookup"><span data-stu-id="4b65e-125">X</span></span>        |
  | <span data-ttu-id="4b65e-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="4b65e-126">LeaveType</span></span>         | <span data-ttu-id="4b65e-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-127">String</span></span>    | <span data-ttu-id="4b65e-128">X</span><span class="sxs-lookup"><span data-stu-id="4b65e-128">X</span></span>        |
  | <span data-ttu-id="4b65e-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="4b65e-129">LeaveDate</span></span>         | <span data-ttu-id="4b65e-130">Datum</span><span class="sxs-lookup"><span data-stu-id="4b65e-130">Date</span></span>      | <span data-ttu-id="4b65e-131">X</span><span class="sxs-lookup"><span data-stu-id="4b65e-131">X</span></span>        |
  | <span data-ttu-id="4b65e-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="4b65e-132">ReasonCodeId</span></span>      | <span data-ttu-id="4b65e-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-133">String</span></span>    |          |
  | <span data-ttu-id="4b65e-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="4b65e-134">PersonnelNumber</span></span>   | <span data-ttu-id="4b65e-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-135">String</span></span>    | <span data-ttu-id="4b65e-136">X</span><span class="sxs-lookup"><span data-stu-id="4b65e-136">X</span></span>        |
  | <span data-ttu-id="4b65e-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="4b65e-137">RequestDate</span></span>       | <span data-ttu-id="4b65e-138">Datum</span><span class="sxs-lookup"><span data-stu-id="4b65e-138">Date</span></span>      | <span data-ttu-id="4b65e-139">X</span><span class="sxs-lookup"><span data-stu-id="4b65e-139">X</span></span>        |
  | <span data-ttu-id="4b65e-140">Kommentar</span><span class="sxs-lookup"><span data-stu-id="4b65e-140">Comment</span></span>           | <span data-ttu-id="4b65e-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="4b65e-141">String</span></span>    |          |
  | <span data-ttu-id="4b65e-142">Status</span><span class="sxs-lookup"><span data-stu-id="4b65e-142">Status</span></span>            | <span data-ttu-id="4b65e-143">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="4b65e-143">Enum</span></span>      | <span data-ttu-id="4b65e-144">X</span><span class="sxs-lookup"><span data-stu-id="4b65e-144">X</span></span>        |
  | <span data-ttu-id="4b65e-145">Tid</span><span class="sxs-lookup"><span data-stu-id="4b65e-145">Amount</span></span>            | <span data-ttu-id="4b65e-146">Realtal</span><span class="sxs-lookup"><span data-stu-id="4b65e-146">Real</span></span>      |          |
  | <span data-ttu-id="4b65e-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="4b65e-147">HalfDayDefinition</span></span> | <span data-ttu-id="4b65e-148">Fasttexttyp</span><span class="sxs-lookup"><span data-stu-id="4b65e-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="4b65e-149">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="4b65e-149">Actions</span></span>

 | <span data-ttu-id="4b65e-150">Namn på åtgärd</span><span class="sxs-lookup"><span data-stu-id="4b65e-150">Action Name</span></span>                               | <span data-ttu-id="4b65e-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4b65e-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="4b65e-152">skicka</span><span class="sxs-lookup"><span data-stu-id="4b65e-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="4b65e-153">Skicka begäran som ska bearbetas av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="4b65e-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4b65e-154">Se även</span><span class="sxs-lookup"><span data-stu-id="4b65e-154">See also</span></span>

- [<span data-ttu-id="4b65e-155">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="4b65e-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="4b65e-156">Autentisering</span><span class="sxs-lookup"><span data-stu-id="4b65e-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]