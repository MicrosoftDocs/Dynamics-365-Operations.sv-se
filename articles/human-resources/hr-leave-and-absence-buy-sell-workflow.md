---
title: Skapa ett arbetsflöde för köpa och sälja ledighetsansökan
description: Skapa ett arbetsflöde för köpa och sälja ledighetsansökan om du vill hantera köpa och sälja ledighetsansökan på konsekvent sätt i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9ec21cda4779fea8c28b73d25842219da900da9d
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271502"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>Skapa ett arbetsflöde för köpa och sälja ledighetsansökan

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan skapa ett arbetsflöde i Dynamics 365 Human Resources för att hantera köpa och sälja ledighetsansökan konsekvent sätt. Ett arbetsflöde för **köpa och sälja ledighet** gör att du kan:

- Definiera uppgifter
- Bestämma vem som måste utföra uppgifterna
- Ange vem som kan godkänna eller avvisa begäranden

## <a name="create-a-buy-and-sell-leave-request-workflow"></a>Skapa ett arbetsflöde för köpa och sälja ledighetsansökan

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Inställningar**, välj **Personalarbetsflöden**.

3. Välj **ny** och välj sedan **köpa och sälja ledighetsansökan**. 

4. När meddelanderutan **Öppna den här filen?** visas väljer du **öppna** och loggar in med dina företagsuppgifter.

5. Använd arbetsflödesredigeraren när du vill skapa ett arbetsflöde för dina tjänstledighetsansökan. Mer information om hur du arbetar med arbetsflöden finns i [Skapa arbetsflöden – översikt](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Arbetsflödesdataelement för tjänstledighet och ledighetsansökan

Du kan använda följande dataelement för att skapa villkorade eller automatiska godkännanden i arbetsflöden för köpa och sälja ledighetsansökan:

- **Belopp**
- **Policy för att köpa och sälja tjänstledighet**
- **Företag**
- **Skapat av**
- **Skapades datum och klockslag**
- **Slutdatum**
- **Tjänstledighetstyp**
- **Ändrades av**
- **Datum och tid för ändring**
- **ID för begäran**
- **Startdatum**
- **Status** 
- **Insändningsdatum**
- **Inskickad av**
- **Skickad av HR**
- **Skickad av chef**
- **Skickad för**
- **Arbetare**

## <a name="workflow-examples"></a>Exempel på arbetsflöden

Exemplen visar hur du kan skapa olika typer av arbetsflödesvillkor genom att använda dessa dataelement:

- Använd **Skickad av HR** och **Skickad av chef** i en automatisk åtgärd för att automatiskt godkänna köpa och sälja ledighetsansökan som dessa roller skickar för medarbetares räkning. Mer information om automatiska åtgärder finns i [Konfigurera godkännandeprocesser i arbetsflöde](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).

- Använd **Tjänstledighetstyp** i villkorssats eller automatisk åtgärd för att kontrollera hur arbetsflödet skickar förfrågningar gällande vissa tjänstledighetstyper.

## <a name="see-also"></a>Se även

[Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)<br>
[Hantera policyer för köpa och sälja tjänstledighet](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)<br>
[Köpa och sälja tjänstledighet](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
