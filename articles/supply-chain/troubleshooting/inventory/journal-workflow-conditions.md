---
title: Arbetsflödesvillkoren för lagerjournaler gäller på journalnivå, inte på radnivå
description: Arbetsflödesvillkor för lagerjournal gäller endast på journalnivå, inte på radnivå.
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
ms.openlocfilehash: 46bdde7f09c639fbefd46162431762b056d521ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477631"
---
# <a name="inventory-journal-workflow-conditions-apply-at-the-journal-level-not-line-level"></a>Arbetsflödesvillkoren för lagerjournaler gäller på journalnivå, inte på radnivå

## <a name="symptoms"></a>Symtom

Det här problemet kan du uppleva om du till exempel försöker ställa in ett arbetsflödesvillkor för lagerjournal på kostnadsbeloppet. Du ställer in villkoret så att steg 1 endast körs när kostnadsbeloppet är mindre än 100. Du ställer in ett annat villkor så att steg 2 endast körs när kostnadsbeloppet är mer än eller lika med 100. När arbetsflödet körs visar sedan arbetsflödeshistoriken bara en rad, och det första villkoret utvärderas alltid som *sant*, oavsett vilket värde som skickas.

## <a name="workaround"></a>Lösning

I aktuella versionen gäller endast arbetsflödesvillkor för lagerjournal på journalnivå, inte på radnivå. Detta beteende är av design. Vi rekommenderar att du anger dina villkor endast på journalnivåattribut.
