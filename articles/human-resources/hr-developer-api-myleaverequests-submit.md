---
title: Skicka en ledighetsansökan till arbetsflödet
description: I Microsoft Dynamics 365 Human Resources kan du använda API:n MyLeaveRequests submit() (Application Programming Interface) för att skicka en begäran till arbetsflöde.
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
ms.openlocfilehash: 7552a4c921dc4a88034b5d2c87d5a9b47d699ae3
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092024"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="88413-103">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="88413-103">Submit a leave request to workflow</span></span>

<span data-ttu-id="88413-104">I Microsoft Dynamics 365 Human Resources kan du använda API:n MyLeaveRequests submit() (Application Programming Interface) för att skicka en begäran till arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="88413-104">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="88413-105">Denna API visas som en åtgärd för OData-enheten MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="88413-105">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88413-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="88413-106">Prerequisites</span></span>

<span data-ttu-id="88413-107">Tjänstledighetsförfrågan måste sparas i databasen och måste kunna hämtas via MyLeaveRequests-entiteten.</span><span class="sxs-lookup"><span data-stu-id="88413-107">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="88413-108">Behörighet</span><span class="sxs-lookup"><span data-stu-id="88413-108">Permissions</span></span>

<span data-ttu-id="88413-109">En av följande behörigheter krävs för att anropa denna API.</span><span class="sxs-lookup"><span data-stu-id="88413-109">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="88413-110">Mer information om behörigheter och hur du väljer dem finns i [Autentisering](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="88413-110">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="88413-111">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="88413-111">Permission type</span></span>                    | <span data-ttu-id="88413-112">Behörigheter (från minst privilegierad till de mest privilegierade)</span><span class="sxs-lookup"><span data-stu-id="88413-112">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="88413-113">Delegerad (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="88413-113">Delegated (work or school account)</span></span> | <span data-ttu-id="88413-114">användar\_personifiering</span><span class="sxs-lookup"><span data-stu-id="88413-114">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="88413-115">HTTPS-begäran</span><span class="sxs-lookup"><span data-stu-id="88413-115">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="88413-116">Begäran följer OData-standarder.</span><span class="sxs-lookup"><span data-stu-id="88413-116">The request conforms to OData standards.</span></span> <span data-ttu-id="88413-117">Parametrarna {requestId}, {leaveType}, {leaveDate} och {dataArea} refererar till de fält som utgör den sammansatta naturliga nyckeln för MyLeaveRequests-enheten.</span><span class="sxs-lookup"><span data-stu-id="88413-117">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="88413-118">När fälten för MyLeaveRequests-entiteten refererar till en enskild rad i tjänstledighetsförfrågan och anropar AP kommer den att skicka hela tjänstledighetsförfrågan (alla rader) till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="88413-118">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="88413-119">Rubrik för begäran</span><span class="sxs-lookup"><span data-stu-id="88413-119">Request headers</span></span>

| <span data-ttu-id="88413-120">Siduvud</span><span class="sxs-lookup"><span data-stu-id="88413-120">Header</span></span>         | <span data-ttu-id="88413-121">Value</span><span class="sxs-lookup"><span data-stu-id="88413-121">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="88413-122">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="88413-122">Authorization</span></span>  | <span data-ttu-id="88413-123">Innehavaren {token} (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="88413-123">Bearer {token} (required)</span></span> |
| <span data-ttu-id="88413-124">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="88413-124">Content-Type</span></span>   | <span data-ttu-id="88413-125">program/json</span><span class="sxs-lookup"><span data-stu-id="88413-125">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="88413-126">Begär brödtext</span><span class="sxs-lookup"><span data-stu-id="88413-126">Request body</span></span>

<span data-ttu-id="88413-127">Ange ingen brödtext för den här metoden.</span><span class="sxs-lookup"><span data-stu-id="88413-127">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="88413-128">Svar</span><span class="sxs-lookup"><span data-stu-id="88413-128">Response</span></span>

<span data-ttu-id="88413-129">Ett lyckat svar är alltid **204 inget innehåll**-svar.</span><span class="sxs-lookup"><span data-stu-id="88413-129">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="88413-130">Obehöriga anropare får ett **401-otillåtet** eller **403-förbjudet** svar.</span><span class="sxs-lookup"><span data-stu-id="88413-130">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="88413-131">Om överföringen misslyckas (t.ex. vid verifiering), är svaret ett **500 serverfel** och svarstexten innehåller ett JSON-objekt med mer information.</span><span class="sxs-lookup"><span data-stu-id="88413-131">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="88413-132">Exempel</span><span class="sxs-lookup"><span data-stu-id="88413-132">Example</span></span>

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a><span data-ttu-id="88413-133">Validerings- och felmeddelanden</span><span class="sxs-lookup"><span data-stu-id="88413-133">Validation and error messages</span></span>

<span data-ttu-id="88413-134">Som en del av anropet till inskickade API skickar personal affärslogiken innan den skickas, vilket garanterar att förfrågan befinner sig i ett giltigt tillstånd för att skickas.</span><span class="sxs-lookup"><span data-stu-id="88413-134">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="88413-135">De felmeddelanden som kan visas i svaret om valideringar misslyckas:</span><span class="sxs-lookup"><span data-stu-id="88413-135">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="88413-136">Denna begäran innebär att saldot för {LeaveTypeId} hamnar under det minsta tillåtna saldot den {date}.</span><span class="sxs-lookup"><span data-stu-id="88413-136">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="88413-137">Det går inte att skicka ledighetsansökan i slutfört läge.</span><span class="sxs-lookup"><span data-stu-id="88413-137">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="88413-138">Det går inte att skicka eller spara begäran eftersom inga ändringar har gjorts.</span><span class="sxs-lookup"><span data-stu-id="88413-138">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="88413-139">Lägg till eller uppdatera belopp eller tjänstledighetstyp och försök igen.</span><span class="sxs-lookup"><span data-stu-id="88413-139">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="88413-140">Ledighetsansökan innehåller en eller flera dagar med samma datum och lämnar typ som en befintlig väntande begäran.</span><span class="sxs-lookup"><span data-stu-id="88413-140">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="88413-141">Du måste återkalla den befintliga begäran för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="88413-141">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="88413-142">Orsakskoden {ReasonCodeId} gäller inte för någon av tjänstledighetstyperna i denna begäran.</span><span class="sxs-lookup"><span data-stu-id="88413-142">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="88413-143">Tjänstledighetstyp '{LeaveTypeId}' kräver en orsakskod.</span><span class="sxs-lookup"><span data-stu-id="88413-143">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="88413-144">Välj lämplig typ och orsakskod.</span><span class="sxs-lookup"><span data-stu-id="88413-144">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="88413-145">Ledig tid skickades inte.</span><span class="sxs-lookup"><span data-stu-id="88413-145">The time off was not submitted successfully.</span></span> <span data-ttu-id="88413-146">Ledig tid har sparats som en utkastförfrågan.</span><span class="sxs-lookup"><span data-stu-id="88413-146">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="88413-147">Se även</span><span class="sxs-lookup"><span data-stu-id="88413-147">See also</span></span>

- [<span data-ttu-id="88413-148">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="88413-148">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="88413-149">Autentisering</span><span class="sxs-lookup"><span data-stu-id="88413-149">Authentication</span></span>](hr-developer-api-authentication.md)