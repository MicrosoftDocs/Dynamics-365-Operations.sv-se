---
title: Anskaffnings- och källarbetsflöden
description: Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen. Ställ in en godkännandeprocess genom att skapa ett arbetsflöde.
author: kamaybac
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a3542dda667a7ec6d8c7e74d8caafd1a8fc5cee322d85981f635a1add56152d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775589"
---
# <a name="procurement-and-sourcing-workflows"></a>Anskaffnings- och källarbetsflöden

[!include [banner](../includes/banner.md)]

Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen. Ställ in en godkännandeprocess genom att skapa ett arbetsflöde.

Ett arbetsflöde representerar en affärsprocess. Det visar ett dokuments väg genom systemet och anger vem som måste genomföra en uppgift eller godkänna ett dokument. Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:

- **Konsekventa processer** – Du kan definiera godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter. Med arbetsflödessystemet blir det enklare att se till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.
- **Processerna blir synliga** – Du kan spåra status, historik och prestandamått för specifika arbetsflödesinstanser. Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.
- **Centraliserad arbetslista** – Användarna kan visa en centraliserad arbetslista för att visa arbetsflödesuppgifterna och godkännanden som har tilldelats dem för alla arbetsflöden som de deltar i. Detta är tillgängligt på sidan Arbetsuppgifter.

## <a name="the-types-of-workflows-that-you-can-create"></a> De typer av arbetsflöden som du kan skapa

Följande arbetsflödestyper är tillgängliga för Anskaffning och källa.

| Typ | Använd den här typen för att |
|---|---|
| Granskning av inköpsrekvisition | Skapa gransknings- och godkännandearbetsflöden för inköpsrekvisitioner. |
| Granskning av inköpsrekvisitionsrad | Skapa gransknings- och godkännandearbetsflöden för inköpsrekvisitionsrader. |
| Arbetsflöde för inköpsorder | Skapa granskning- och godkännandearbetsflöden för inköpsorder. |
| Arbetsflöde för inköpsorderrad | Skapa granskning- och godkännandearbetsflöden för orderrader. |
| Ansökningsarbetsflöde för leverantörstillägg | Att granska och godkänna arbetsflöden för att lägga till nya leverantörer via leverantörsförfrågningar. |

> [!IMPORTANT]
> När du lägger till ett nytt arbetsflöde kan du också se följande föråldrade arbetsflöden i dialogrutan **Skapa arbetsflöde**. Dessa är relaterade till funktionen *bekräftelse av kvitto* som fanns i [Dynamics AX 2012](/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), men som nu är föråldrade. Dessa arbetsflöden stöds för närvarande inte.
> 
> - Meddelandearbetsflöde för leveransens förfallodatum
> - Meddelandearbetsflöde för mottagen faktura
> - Produktinleveransen godkändes inte i meddelandearbetsflödet
> - Meddelandearbetsflöde för avvisad obekräftad produktinleverans

## <a name="creating-a-workflow"></a>Skapa ett arbetsflöde

Om du vill skapa ett arbetsflöde, gå till Anskaffning och källa &gt; Inställningar &gt; Anskaffnings- och källarbetsflöden och skapa ett nytt arbetsflöde genom att välja vilken typ av arbetsflöden som du vill skapa. 

I arbetsflödets arbetsyta kan du dra arbetsflödeselement till designern och länka elementen till ett flöde. Arbetsflödeselementen bör konfigureras. För arbetsflödeselement för godkännande och uppgift kan du konfigurera vilken deltagare som ska vidta åtgärder.

## <a name="types-of-participants"></a>Typer av deltagare

Du kan tilldela ett godkännandesteg till följande grupper för deltagare.

| Användargrupp | Beskrivning |
|---|---|
| Deltagare | Tilldela godkännandesteget till medlemmar i en grupp eller en roll. |
| Hierarki | Tilldela godkännandesteget till användare i en viss organisationshierarki |
| Användare av arbetsflöde | Tilldela godkännandesteget till användare i arbetsflödet. |
| Kö | Tilldela godkännandesteget till en arbetsuppgiftskö. |
| Användare | Tilldela godkännandesteget till specifika användare. |

## <a name="additional-resources"></a>Ytterligare resurser

- [Definiera affärsprocessarbetsflöden för inköpsrekvisitioner](https://www.microsoft.com/download/details.aspx?id=101821)
- [Arbetsflöde för inköpsrekvisitioner](purchase-requisitions-workflow.md)
- [Integrera leverantörer](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]