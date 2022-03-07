---
title: Enheten och enhetskvantiteten fungerar inte korrekt i lagerjournalen
description: Enheten och enhetskvantiteten fungerar inte korrekt i lagerjournalen
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
ms.openlocfilehash: 39f462ae325aa1104a25a8290daed70388e624ec
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477613"
---
# <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>Enheten och enhetskvantiteten fungerar inte korrekt i lagerjournalen

## <a name="symptoms"></a>Symtom

Du kanske stöter på ett eller båda av följande problem när du arbetar med enheter och kvantiteter i en lagerjournal:

- Du ser inte enheter eller enhetskvantiteter i lagerjournalen medan en enhet med konvertering ställs in för den frisläppta produkten och du kan inte ändra enheten i lagerjournalen.
- Du ser fälten **Antal** och **Enhet** i lagerjournalen, men du ser inte fältet **enhetskvantitet**. Om du ändrar enheten, anger ett antal och bokför journalen, visar journalen fortfarande den ursprungliga måttenheten för den kvantiteten.

## <a name="resolution"></a>Lösning

Gör så här om du vill åtgärda problemet.

1. I arbetsytan **Funktionshantering** se till att funktionen *Använda måttenhet och kvantitet i lagerjournaler* är aktiverad. Den här funktionen lägger till fälten **Enhet** och **Enhetskvantitet** i journalen.
1. När funktionen har aktiverats använder du fälten **Antal**, **Enhetskvantitet** och **Enhet** på följande sätt:

    - **Antal** – Ange kvantiteten med hjälp av standardenheten som har definierats för den frisläppta produkten. Standardenheten i sig visas dock inte här. Om en konvertering ställs in mellan standardenheten och den enhet som är markerad i fältet **Enhet** uppdateras fältet **Antal** automatiskt, baserat på valen i fälten **Enhetskvantitet** och **Enhet**.
    - **Enhetskvantitet** – Ange mängden i den enhet som har valts i fältet **Enhet**.
    - **Enhet** – Välj den enhet som ska kopplas till värdet i fältet **Enhetskvantitet**.
