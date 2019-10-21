---
title: Konfigurera arbetsflöden för utgifter
description: Du kan skapa ett arbetsflöde för att granska och godkänna rese- och utgiftsdokument.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86cadf7277fbb7e08dad4b5dc2a46e1c6ce5a888
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179962"
---
# <a name="set-up-workflows-for-expense"></a>Konfigurera arbetsflöden för utgifter

[!include [banner](../includes/banner.md)]

 Du kan skapa ett arbetsflöde för att granska och godkänna rese- och utgiftsdokument. De dokument för vilka arbetsflöden kan definieras inkluderar utgiftsrapporter, reserekvisitioner samt begäranden om förskott.

Ett arbetsflöde representerar en affärsprocess. Det visar ett dokuments väg genom systemet och anger vem som måste genomföra en uppgift eller godkänna ett dokument. Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:

-   **Konsekventa processer** – Du kan definiera godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter. Med arbetsflödessystemet blir det enklare att se till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.

-   Processerna blir synliga – Du kan spåra status, historik och prestandamått för specifika arbetsflödesinstanser. Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.

-   Centraliserad arbetslista – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet. 

**De typer av arbetsflöden du kan skapa**

Följande tabell listar de typer av arbetsflöden som du kan skapa under **Utgift**.


|              <strong>Typ</strong>              |                   <strong>Använd den här typen för att</strong>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <strong>Utgiftsrapport</strong>         |            Skapa arbetsflöden för godkännande av utgiftsrapporter.             |
|  <strong>Automatisk bokföring av utgiftsrapport</strong>   |        Skapa automatiska arbetsflöden för bokföring av utgiftsrapporter.        |
|       <strong>Utgiftsradartikel</strong>        |     Skapa arbetsflöden för godkännande av radobjekt i utgiftsrapporter.      |
| <strong>Automatisk bokföring av utgiftsradartiklar</strong> | Skapa automatiska arbetsflöden för bokföring av radobjekt i utgiftsrapporter. |
|       <strong>Reserekvisition</strong>       |          Skapa arbetsflöden för godkännande av reserekvisitioner.           |
|      <strong>Förskottsbegäran</strong>      |         Skapa arbetsflöden för godkännande av begäranden om förskott.          |
|        <strong>Momsåterbetalning</strong>        | Skapa arbetsflöden för godkännande av återbetalande av moms  |

