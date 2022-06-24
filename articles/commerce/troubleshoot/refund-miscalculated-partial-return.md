---
title: Återbetalningsbara avgifter beräknas fel baserat på den returnerade kvantiteten
description: Denna artikel innehåller felsökningsvägledning som kan hjälpa kassörer som upptäcker felaktiga återbetalningsbara avgifter i kassan (POS) för den kvantitet med artiklar som returneras.
author: gvrmohanreddy
ms.date: 03/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 7a84207f587a826b9acdfd818c64220c5327bde1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890253"
---
# <a name="refundable-charges-are-miscalculated-based-on-the-quantity-returned"></a>Återbetalningsbara avgifter beräknas fel baserat på den returnerade kvantiteten

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan hjälpa kassörer som upptäcker felaktiga återbetalningsbara avgifter i kassan (POS) för den kvantitet med artiklar som returneras.

## <a name="description"></a>Beskrivning

En kund returnerar en delkvantitet av artiklarna som köpts in för en försäljningsorder med återbetalningsbara avgifter på radnivå. I stället för att visa en delvis återbetalning visar POS alla avgifter som återbetalningsbara.

En kund köper till exempel en kvantitet på fem artiklar $5 per artikel, för total kostnad för $25. Kunden returnerar sedan tre av de fem artiklarna. Kassören visas dock en $25 återbetalningsbar avgift i POS, i stället för den förväntade $15 återbetalningsbar avgift för de tre artiklarna som returnerats.

## <a name="resolution"></a>Lösning

### <a name="turn-on-the-enable-refunding-charges-based-on-the-refunded-quantity-feature"></a>Aktivera återbetalningsavgifter baserat på den återbetalade kvantiteten

Från och med Microsoft Dynamics 365 Commerce version 10.0.26, gör funktionen **Aktivera återbetalningsavgifter baserat på den återbetalade kvantiteten** det möjligt att beräkna återbetalningsbara avgifter på radnivå baserat på mängden varor som returneras.

Aktivera funktionen **Aktivera återbetalningsavgifter baserade på funktionen för återbetalad kvantitet** i Commerce headquarters genom att följa dessa steg.

1. Öppna arbetsytan **Funktionshantering** (**Systemadministratör \> Arbetsytor \> Funktionshantering**).
1. Sök efter och välj aktivera återbetalningsavgifter baserat på funktionen för **Aktivera återbetalningsavgifter baserade på funktionen för återbetalad kvantitet**.
1. Välj **Aktivera nu** i höger fönster.
