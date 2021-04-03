---
title: Skapa en ledighetsansökan till arbetsflödet
description: Skapa ett arbetsflöde för tjänstledighet och ledighetsansökan om du vill hantera ledighetsansökningar på ett konsekvent sätt i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c2c2020c68c4aca3594a2532d32f968ab76f6b7b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463320"
---
# <a name="create-a-leave-request-workflow"></a>Skapa en ledighetsansökan till arbetsflödet

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

5. Använd arbetsflödesredigeraren när du vill skapa ett arbetsflöde för dina tjänstledighetsansökan. Mer information om hur du arbetar med arbetsflöden finns i [Skapa arbetsflöden – översikt](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)

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

- Använd **Orsakskod** i en villkorssats för att vidarebefordra förfrågningar om sjukfrånvaro med orsakskoden **Kirurgiskt ingrepp** till HR för godkännande medan alla andra orsakskoder skickas till chefen. Mer information om villkorssatser finns i [Konfigurera villkorliga beslut i arbetsflöde](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow). 

- Använd **Skickad av HR** och **Skickad av chef** i en automatisk åtgärd för att automatiskt godkänna tjänstledighet som dessa roller skickar för medarbetares räkning. Mer information om automatiska åtgärder finns i [Konfigurera godkännandeprocesser i arbetsflöde](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).

- Använd **Tjänstledighetstyp** i villkorssats eller automatisk åtgärd för att kontrollera hur arbetsflödet skickar förfrågningar gällande vissa tjänstledighetstyper.

## <a name="see-also"></a>Se även

- [Översikt över tjänstledighet och frånvaro](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]