---
title: Lagerjournalarbetsflödet slutförs aldrig och det går inte att bearbeta journalen
description: När du har skickat ett arbetsflöde för godkännande av journaler slutar arbetsflödesbearbetningen att svara och du kan inte redigera eller bearbeta dina journaler.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 5e8168a20a1fa4f52d28129eebb9931b31157ced
ms.sourcegitcommit: ab690bc897699ff8a4c489e749251fe0367050ca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2022
ms.locfileid: "8488979"
---
# <a name="inventory-journal-workflow-never-completes-and-the-journal-cant-be-processed"></a>Lagerjournalarbetsflödet slutförs aldrig och det går inte att bearbeta journalen

## <a name="symptoms"></a>Symtom

När du har skickat ett arbetsflöde för godkännande av journaler slutar arbetsflödesbearbetningen att svara och du kan inte redigera eller bearbeta dina journaler.

## <a name="resolution"></a>Lösning

Det finns flera orsaker till att arbetsflödesbearbetningen kanske inte har slutförts. Kontrollera om följande problem:

- Gå till **Lagerhantering &gt; Inställningar &gt; Arbetsflöden för lagerhantering** och granska konfigurationen av det berörda arbetsflödet. Mer information finns i [Godkännandearbetsflöden för lagerjournal](../../inventory/inventory-journal-workflow.md).
- Arbetsflödet kanske stöter på ett undantag eller ett fel. Granska arbetsobjektshistoriken för det berörda arbetsflödet för att se om det inkluderar ett programfel som avslutar arbetsflödet.
- Lagerjournalen kan bara uppdateras eller redigeras om den är godkänd. Om återkallande är aktivt kan du försöka återkalla journalen. Körning av batchjobbet för arbetsflöde kanske stängs av på grund av flera skäl. Vissa av dessa orsaker kan bero på problemet med arbetsflödesramverket.
