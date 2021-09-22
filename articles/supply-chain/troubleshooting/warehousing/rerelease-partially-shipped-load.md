---
title: Det går inte att frisläppa en delvis levererad last till lagerstället igen
description: I tidigare versioner kan du inte frisläppa en delvis skeppad last när du använder vissa funktioner med ofullständiga reservationer. Det här har åtgärdats.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0380e1963a38f2be55b31e06b3845f935661eed2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477649"
---
# <a name="cant-re-release-a-partially-shipped-load-to-the-warehouse"></a>Det går inte att frisläppa en delvis levererad last till lagerstället igen

## <a name="symptoms"></a>Symtom

Du kan inte frisläppa en delvis levererad last till lagerstället. När du gör frisläppningen till lagerstället visas meddelandet "åtgärden är slutförd", men ingenting händer och inget arbete skapas för den återstående kvantiteten. Det här problemet uppstår när du använder funktionen för transportlast och det finns en ofullständig reservation.

## <a name="resolution"></a>Lösning

[KB-ärende 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("delvis levererade laster kan återpåfyllas och återbearbetas") har korrigerats i [version 10.0.15](/dynamics365/supply-chain/get-started/whats-new-scm-10-0-15).
