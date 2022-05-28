---
title: Skicka en ledighetsansökan till arbetsflödet
description: I Microsoft Dynamics 365 Human Resources kan du använda API:n MyLeaveRequests submit() (Application Programming Interface) för att skicka en begäran till arbetsflöde.
author: twheeloc
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba2867646ac03953a43404984a5d04d4edb1f5ac
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687007"
---
# <a name="submit-a-leave-request-to-workflow"></a>Skicka en ledighetsansökan till arbetsflödet


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I Microsoft Dynamics 365 Human Resources kan du använda API:n MyLeaveRequests submit() (Application Programming Interface) för att skicka en begäran till arbetsflöde. Denna API visas som en åtgärd för OData-enheten MyLeaveRequests.

## <a name="prerequisites"></a>Förutsättningar

Tjänstledighetsbegäran måste sparas i databasen och måste kunna hämtas via MyLeaveRequests-entiteten.

## <a name="permissions"></a>Behörighet

En av följande behörigheter krävs för att anropa denna API. Mer information om behörigheter och hur du väljer dem finns i [Autentisering](hr-developer-api-authentication.md).

| Behörighetstyp                    | Behörigheter (från minst privilegierad till de mest privilegierade) |
|------------------------------------|--------------------------------------------------------|
| Delegerad (arbets- eller skolkonto) | användar\_personifiering                                    |

## <a name="https-request"></a>HTTPS-begäran

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

Begäran följer OData-standarder. Parametrarna {requestId}, {leaveType}, {leaveDate} och {dataArea} refererar till de fält som utgör den sammansatta naturliga nyckeln för MyLeaveRequests-enheten.

> [!NOTE]
> När fälten för MyLeaveRequests-entiteten refererar till en enskild rad i tjänstledighetsbegäran och anropar AP kommer den att skicka hela tjänstledighetsbegäran (alla rader) till arbetsflödet.

### <a name="request-headers"></a>Rubrik för begäran

| Siduvud         | Value                     |
|----------------|---------------------------|
| Auktorisering  | Innehavaren {token} (obligatoriskt) |
| Innehållstyp   | program/json          |

### <a name="request-body"></a>Begär brödtext

Ange ingen brödtext för den här metoden.

### <a name="response"></a>Svar

Ett lyckat svar är alltid **204 inget innehåll**-svar.

Obehöriga anropare får ett **401-otillåtet** eller **403-förbjudet** svar.

Om överföringen misslyckas (t.ex. vid verifiering), är svaret ett **500 serverfel** och svarstexten innehåller ett JSON-objekt med mer information.

## <a name="example"></a>Exempel

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

## <a name="validation-and-error-messages"></a>Validerings- och felmeddelanden

Som en del av anropet till inskickade API skickar personal affärslogiken innan den skickas, vilket garanterar att begäran befinner sig i ett giltigt tillstånd för att skickas. De felmeddelanden som kan visas i svaret om valideringar misslyckas:

 - Denna begäran innebär att saldot för {LeaveTypeId} hamnar under det minsta tillåtna saldot den {date}.
 - Det går inte att skicka ledighetsansökan i slutfört läge.
 - Det går inte att skicka eller spara begäran eftersom inga ändringar har gjorts. Lägg till eller uppdatera belopp eller tjänstledighetstyp och försök igen.
 - Ledighetsansökan innehåller en eller flera dagar med samma datum och lämnar typ som en befintlig väntande begäran. Du måste återkalla den befintliga begäran för att göra ändringar.
 - Orsakskoden {ReasonCodeId} gäller inte för någon av tjänstledighetstyperna i denna begäran.
 - Tjänstledighetstyp '{LeaveTypeId}' kräver en orsakskod. Välj lämplig typ och orsakskod.
 - Ledig tid skickades inte. Ledig tid har sparats som en utkastbegäran.

## <a name="see-also"></a>Se även

- [Översikt över MyLeaveRequests](hr-developer-api-myleaverequests-overview.md)
- [Autentisering](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
