---
title: Skapa en ledighetsansökan till arbetsflödet
description: Skapa ett arbetsflöde för tjänstledighet och ledighetsansökan om du vill hantera ledighetsansökningar på ett konsekvent sätt i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 707b986c41cde2d4e26bdb4c5218b87b27702cee
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065186"
---
# <a name="create-a-leave-request-workflow"></a>Skapa en ledighetsansökan till arbetsflödet


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan skapa ett arbetsflöde i Dynamics 365 Human Resources för att hantera ledighetsansökningar på ett konsekvent sätt. Ett arbetsflöde för **tjänstledighet och frånvaro** gör att du kan:

- Definiera uppgifter
- Bestämma vem som måste utföra uppgifterna
- Ange vem som kan godkänna eller avvisa begäranden

## <a name="create-a-leave-and-absence-request-workflow"></a>Skapa ett arbetsflöde för tjänstledighet och ledighetsansökan

1. På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.

2. Under **Inställningar**, välj **Personalarbetsflöden**.

3. Välj **ny** och välj sedan **tjänstledighets- och frånvaroansökningar**. 

4. När meddelanderutan **Öppna den här filen?** visas väljer du **öppna** och loggar in med dina företagsuppgifter.

5. Använd arbetsflödesredigeraren när du vill skapa ett arbetsflöde för dina tjänstledighetsansökan. Mer information om hur du arbetar med arbetsflöden finns i [Skapa arbetsflöden – översikt](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Arbetsflödesdataelement för tjänstledighet och ledighetsansökan

Du kan använda följande dataelement för att skapa villkorade eller automatiska godkännanden i arbetsflöden för tjänstledighets- och ledighetsansökningar:

- **Belopp**
- **Kommentar**
- **Företag**
- **Skapades av**
- **Skapat datum och klockslag**
- **Slutdatum**
- **Tjänstledighetstyp**
- **Ändrades av**
- **Datum och tid för ändring**
- **Orsakskod**
- **ID för begäran**
- **Startdatum**
- **Status** 
- **Insändningsdatum**
- **Inskickad av**
- **Skickad av HR**
- **Skickad av chef**
- **Skickad för**
- **Arbetare**
- **Typ av arbetare**

Exemplen visar hur du kan skapa olika typer av arbetsflödesvillkor genom att använda dessa dataelement:

- Använd **Orsakskod** i en villkorssats för att vidarebefordra förfrågningar om sjukfrånvaro med orsakskoden **Kirurgiskt ingrepp** till HR för godkännande medan alla andra orsakskoder skickas till chefen. Mer information om villkorssatser finns i [Konfigurera villkorliga beslut i arbetsflöde](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md). 

- Använd **Skickad av HR** och **Skickad av chef** i en automatisk åtgärd för att automatiskt godkänna tjänstledighet som dessa roller skickar för medarbetares räkning. Mer information om automatiska åtgärder finns i [Konfigurera godkännandeprocesser i arbetsflöde](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).

- Använd **Tjänstledighetstyp** i villkorssats eller automatisk åtgärd för att kontrollera hur arbetsflödet skickar förfrågningar gällande vissa tjänstledighetstyper.

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
