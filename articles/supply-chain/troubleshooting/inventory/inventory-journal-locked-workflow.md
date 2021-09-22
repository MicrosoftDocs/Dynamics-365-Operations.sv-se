---
title: Lagerjournalen är låst och arbetsflödets batchjobb fungerar inte
description: En av dina lagerjournaler är låst av någon operation och släpps inte
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
ms.openlocfilehash: 8b21ec2e2b3b8546dcb138422c5540053392c179
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477605"
---
# <a name="your-inventory-journal-is-locked-and-the-workflow-batch-job-doesnt-work"></a>Lagerjournalen är låst och arbetsflödets batchjobb fungerar inte

## <a name="symptoms"></a>Symtom

En av dina lagerjournaler är låst av någon operation och släpps inte. Om ett okänt fel till exempel inträffar under bokföringen (vilket är en systemlåsoperation) kan journalen finnas kvar i systemlåst status. I det här fallet arbetsflödet arbetsobjekt hanterare kommer att kasta ett fel medan den gör låsvalidering.

## <a name="resolution"></a>Lösning

Logga in på SQL Server-instansen för Supply Chain Management, och kontrollera om **InventJournalTable.SystemBlocked** är inställt på *1*. Om det är det, se till att journalen inte ska vara i låst status och återställ sedan **InventJournalTable.SystemBlocked** till *0*.
