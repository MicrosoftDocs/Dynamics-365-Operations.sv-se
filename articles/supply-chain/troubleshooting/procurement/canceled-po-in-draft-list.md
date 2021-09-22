---
title: Annullerade inköpsorder visas på arbetsytans utkastlista
description: Annullerade inköpsorder visas i utkast listan på arbetsytan för förberedelse av inköpsorder
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f1dc23cd7e5b4b99cb7a9440d7d4666d8396511f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477654"
---
# <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-workspace"></a>Annullerade inköpsorder visas på arbetsytans utkastlista

## <a name="symptoms"></a>Symtom

När du har avbrutit inköpsorder som *bekräftat* visas de inställda inköpsorder fortfarande i listan över utkast till inköpsorder i arbetsordern **Inköpsorderförberedelse**.

## <a name="resolution"></a>Lösning

Det här problemet uppstår endast för inköpsorder som är föremål för ändringshantering. Det beror på att annulleringen betraktas som en ändring som måste godkännas. Godkännandet kan utföras automatiskt av systemet. Därför är processen att skicka den annullerade inköpsordern till arbetsflödet för godkännande så att den kan gå till ett *godkänt* tillstånd. Vid den tidpunkten visas inköpsordern inte längre i listan med utkast till inköpsorder i arbetsytan **Inköpsorder förberedelse**.
