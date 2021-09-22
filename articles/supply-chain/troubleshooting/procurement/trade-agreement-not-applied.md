---
title: Handelsavtalsvillkoren används inte för importerade orderrader
description: Priser och rabatter för handelsavtal tillämpas inte på försäljnings- eller inköpsorderrader som importeras via datahantering
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: fef38819efaff2f2a927cf09fc7f469490149574
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477660"
---
# <a name="trade-agreement-conditions-arent-applied-to-imported-order-lines"></a>Handelsavtalsvillkoren används inte för importerade orderrader

## <a name="symptoms"></a>Symtom

Handelsavtal som tillämpas på försäljnings- eller inköpsorderrader tillämpas inte på rader som importeras via datahantering. Samma handelsavtal tillämpas emellertid på försäljnings- eller inköpsorderrader som skapas manuellt.

## <a name="cause"></a>Orsak

Om inköpsorderrader som importeras via datahantering redan inkluderar prisinformation kommer handelsavtalet inte att utvärderas igen för dessa rader. Om t.ex. **Radrabatt i procent** eller om något av pris- och rabattvärdena är inställda för en rad, kommer inte handelsavtalen att letas upp för den raden.

## <a name="workaround"></a>Lösning

Det här beteendet förväntas och används på liknande sätt för både försäljningsorder och inköpsorder.

Importera inköpsorderraderna utan att ange någon prisinformation. Handelsavtalen kommer sedan att tillämpas och inköpsorderraderna uppdateras baserat på de definierade handelsavtalen.
