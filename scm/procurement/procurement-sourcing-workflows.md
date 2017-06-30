---
title: "Anskaffnings- och källarbetsflöden"
description: "Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen. Ställ in en godkännandeprocess genom att skapa ett arbetsflöde."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 67bdb8436ff379b0e55cfe1660597e8f93235eeb
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="procurement-and-sourcing-workflows"></a>Anskaffnings- och källarbetsflöden

[!include[banner](../includes/banner.md)]


Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen. Ställ in en godkännandeprocess genom att skapa ett arbetsflöde.

Ett arbetsflöde representerar en affärsprocess. Det visar ett dokuments väg genom systemet och anger vem som måste genomföra en uppgift eller godkänna ett dokument. Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:
-   **Konsekventa processer** – Du kan definiera godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter. Med arbetsflödessystemet blir det enklare att se till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.
-   **Processerna blir synliga** – Du kan spåra status, historik och prestandamått för specifika arbetsflödesinstanser. Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.
-   **Centraliserad arbetslista** – Användarna kan visa en centraliserad arbetslista för att visa arbetsflödesuppgifterna och godkännanden som har tilldelats dem för alla arbetsflöden som de deltar i. Detta är tillgängligt på sidan Arbetsuppgifter.

## <a name="the-types-of-workflows-that-you-can-create"></a> De typer av arbetsflöden som du kan skapa
Följande arbetsflödestyper är tillgängliga för Anskaffning och källa.

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| **Typ**                         | **Använd den här typen för att**                                          |
| Granskning av inköpsrekvisition      | Skapa granskningsarbetsflöden för inköpsrekvisitioner.            |
| Granskning av inköpsrekvisitionsrad | Skapa granskningsarbetsflöden för inköpsrekvisitionsrader.       |
| Arbetsflöde för inköpsorder          | Skapa granskning- och godkännandearbetsflöden för inköpsorder.     |
| Arbetsflöde för inköpsorderrad     | Skapa granskning- och godkännandearbetsflöden för orderrader. |

## <a name="creating-a-workflow"></a>Skapa ett arbetsflöde
Om du vill skapa ett arbetsflöde, gå till Anskaffning och källa &gt; Inställningar &gt; Anskaffnings- och källarbetsflöden och skapa ett nytt arbetsflöde genom att välja vilken typ av arbetsflöden som du vill skapa.  

I arbetsflödets arbetsyta kan du dra arbetsflödeselement till designern och länka elementen till ett flöde. Arbetsflödeselementen bör konfigureras. För arbetsflödeselement för godkännande och uppgift kan du konfigurera vilken deltagare som ska vidta åtgärder.
Typer av deltagare
----------------------

Du kan tilldela ett godkännandesteg till följande grupper för deltagare.

| Användargrupp    | Beskrivning                                                               |
|---------------|---------------------------------------------------------------------------|
| Deltagare   | Tilldela godkännandesteget till medlemmar i en grupp eller en roll.                   |
| Hierarki     | Tilldela godkännandesteget till användare i en viss organisationshierarki |
| Användare av arbetsflöde | Tilldela godkännandesteget till användare i arbetsflödet.                       |
| Kö         | Tilldela godkännandesteget till en arbetsuppgiftskö.                            |
| Användare          | Tilldela godkännandesteget till specifika användare.                               |



<a name="see-also"></a>Se även
--------

[Definiera affärsprocessarbetsflöden för inköpsrekvisitioner](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Arbetsflöde för inköpsrekvisitioner](purchase-requisitions-workflow.md)




