---
title: Skicka en ledighetsansökan till arbetsflödet
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
ms.openlocfilehash: 008ee231ca9f0459e332b17cea9f2a3f3e3cc2a5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010646"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="d3259-102">Skicka en ledighetsansökan till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="d3259-102">Submit a leave request to workflow</span></span>

<span data-ttu-id="d3259-103">I Microsoft Dynamics 365 Human Resources kan du använda API:n MyLeaveRequests submit() (Application Programming Interface) för att skicka en begäran till arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="d3259-103">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="d3259-104">Denna API visas som en åtgärd för OData-enheten MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="d3259-104">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3259-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d3259-105">Prerequisites</span></span>

<span data-ttu-id="d3259-106">Tjänstledighetsförfrågan måste sparas i databasen och måste kunna hämtas via MyLeaveRequests-entiteten.</span><span class="sxs-lookup"><span data-stu-id="d3259-106">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="d3259-107">Behörighet</span><span class="sxs-lookup"><span data-stu-id="d3259-107">Permissions</span></span>

<span data-ttu-id="d3259-108">En av följande behörigheter krävs för att anropa denna API.</span><span class="sxs-lookup"><span data-stu-id="d3259-108">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d3259-109">Mer information om behörigheter och hur du väljer dem finns i [Autentisering](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d3259-109">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="d3259-110">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="d3259-110">Permission type</span></span>                    | <span data-ttu-id="d3259-111">Behörigheter (från minst privilegierad till de mest privilegierade)</span><span class="sxs-lookup"><span data-stu-id="d3259-111">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="d3259-112">Delegerad (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="d3259-112">Delegated (work or school account)</span></span> | <span data-ttu-id="d3259-113">användar\_personifiering</span><span class="sxs-lookup"><span data-stu-id="d3259-113">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="d3259-114">HTTPS-begäran</span><span class="sxs-lookup"><span data-stu-id="d3259-114">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="d3259-115">Begäran följer OData-standarder.</span><span class="sxs-lookup"><span data-stu-id="d3259-115">The request conforms to OData standards.</span></span> <span data-ttu-id="d3259-116">Parametrarna {requestId}, {leaveType}, {leaveDate} och {dataArea} refererar till de fält som utgör den sammansatta naturliga nyckeln för MyLeaveRequests-enheten.</span><span class="sxs-lookup"><span data-stu-id="d3259-116">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="d3259-117">När fälten för MyLeaveRequests-entiteten refererar till en enskild rad i tjänstledighetsförfrågan och anropar AP kommer den att skicka hela tjänstledighetsförfrågan (alla rader) till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d3259-117">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="d3259-118">Rubrik för begäran</span><span class="sxs-lookup"><span data-stu-id="d3259-118">Request headers</span></span>

| <span data-ttu-id="d3259-119">Siduvud</span><span class="sxs-lookup"><span data-stu-id="d3259-119">Header</span></span>         | <span data-ttu-id="d3259-120">Value</span><span class="sxs-lookup"><span data-stu-id="d3259-120">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="d3259-121">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="d3259-121">Authorization</span></span>  | <span data-ttu-id="d3259-122">Innehavaren {token} (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="d3259-122">Bearer {token} (required)</span></span> |
| <span data-ttu-id="d3259-123">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="d3259-123">Content-Type</span></span>   | <span data-ttu-id="d3259-124">program/json</span><span class="sxs-lookup"><span data-stu-id="d3259-124">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="d3259-125">Begär brödtext</span><span class="sxs-lookup"><span data-stu-id="d3259-125">Request body</span></span>

<span data-ttu-id="d3259-126">Ange ingen brödtext för den här metoden.</span><span class="sxs-lookup"><span data-stu-id="d3259-126">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="d3259-127">Svar</span><span class="sxs-lookup"><span data-stu-id="d3259-127">Response</span></span>

<span data-ttu-id="d3259-128">Ett lyckat svar är alltid **204 inget innehåll**-svar.</span><span class="sxs-lookup"><span data-stu-id="d3259-128">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="d3259-129">Obehöriga anropare får ett **401-otillåtet** eller **403-förbjudet** svar.</span><span class="sxs-lookup"><span data-stu-id="d3259-129">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="d3259-130">Om överföringen misslyckas (t.ex. vid verifiering), är svaret ett **500 serverfel** och svarstexten innehåller ett JSON-objekt med mer information.</span><span class="sxs-lookup"><span data-stu-id="d3259-130">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="d3259-131">Exempel</span><span class="sxs-lookup"><span data-stu-id="d3259-131">Example</span></span>

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

## <a name="validation-and-error-messages"></a><span data-ttu-id="d3259-132">Validerings- och felmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d3259-132">Validation and error messages</span></span>

<span data-ttu-id="d3259-133">Som en del av anropet till inskickade API skickar personal affärslogiken innan den skickas, vilket garanterar att förfrågan befinner sig i ett giltigt tillstånd för att skickas.</span><span class="sxs-lookup"><span data-stu-id="d3259-133">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="d3259-134">De felmeddelanden som kan visas i svaret om valideringar misslyckas:</span><span class="sxs-lookup"><span data-stu-id="d3259-134">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="d3259-135">Denna begäran innebär att saldot för {LeaveTypeId} hamnar under det minsta tillåtna saldot den {date}.</span><span class="sxs-lookup"><span data-stu-id="d3259-135">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="d3259-136">Det går inte att skicka ledighetsansökan i slutfört läge.</span><span class="sxs-lookup"><span data-stu-id="d3259-136">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="d3259-137">Det går inte att skicka eller spara begäran eftersom inga ändringar har gjorts.</span><span class="sxs-lookup"><span data-stu-id="d3259-137">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="d3259-138">Lägg till eller uppdatera belopp eller tjänstledighetstyp och försök igen.</span><span class="sxs-lookup"><span data-stu-id="d3259-138">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="d3259-139">Ledighetsansökan innehåller en eller flera dagar med samma datum och lämnar typ som en befintlig väntande begäran.</span><span class="sxs-lookup"><span data-stu-id="d3259-139">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="d3259-140">Du måste återkalla den befintliga begäran för att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="d3259-140">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="d3259-141">Orsakskoden {ReasonCodeId} gäller inte för någon av tjänstledighetstyperna i denna begäran.</span><span class="sxs-lookup"><span data-stu-id="d3259-141">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="d3259-142">Tjänstledighetstyp '{LeaveTypeId}' kräver en orsakskod.</span><span class="sxs-lookup"><span data-stu-id="d3259-142">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="d3259-143">Välj lämplig typ och orsakskod.</span><span class="sxs-lookup"><span data-stu-id="d3259-143">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="d3259-144">Ledig tid skickades inte.</span><span class="sxs-lookup"><span data-stu-id="d3259-144">The time off was not submitted successfully.</span></span> <span data-ttu-id="d3259-145">Ledig tid har sparats som en utkastförfrågan.</span><span class="sxs-lookup"><span data-stu-id="d3259-145">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3259-146">Se även</span><span class="sxs-lookup"><span data-stu-id="d3259-146">See also</span></span>

- [<span data-ttu-id="d3259-147">Översikt över MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="d3259-147">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="d3259-148">Autentisering</span><span class="sxs-lookup"><span data-stu-id="d3259-148">Authentication</span></span>](hr-developer-api-authentication.md)