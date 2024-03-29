---
title: Skapa ett arbetsflöde för köpa och sälja ledighetsansökan
description: Skapa ett arbetsflöde för köpa och sälja ledighetsansökan om du vill hantera köpa och sälja ledighetsansökan på konsekvent sätt i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fabe2333bbf76edf31b77c0d5fce044273333de2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869819"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>Skapa ett arbetsflöde för köpa och sälja ledighetsansökan


>[!Important]
>Funktionen som anges i den här artikeln är för närvarande tillgänglig för kunder med fristående Dynamics 365 Human Resources. Vissa eller alla funktionerna kommer att vara tillgängliga i en kommande version av Finance-infrastrukturen efter Finance version 10.0.26.


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
