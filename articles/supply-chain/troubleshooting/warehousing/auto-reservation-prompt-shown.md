---
title: Uppmaning om automatisk reservation av visas med tillgängligt lager
description: När du använder en artikel på ett lagerställe där lagerställeprocesser inte har aktiverats visas prompten för automatisk reservation. Ange alla dimensioner ovanför Plats.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a15502ce8c5bc61d37cedd746985176408a2f362
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477669"
---
# <a name="auto-reservation-prompt-for-batch-number-is-shown-even-with-available-inventory"></a>Uppmaning om automatisk reservation av batchnummer visas även med tillgängligt lager

## <a name="symptoms"></a>Symtom

När du använder ett objekt som har ett *batch ovan* bokningshierarki i ett lager som inte har aktiverat lagerprocesser och automatisk bokning är aktiverad visas snabbokningsprompten för ett batchnummer även om bara en batch är tillgänglig för plockning.

Om du använder samma artikel på ett lagerställe där lagerställeprocesser har aktiverats visas dock inte prompten för automatisk reservation.

## <a name="resolution"></a>Lösning

Om en reservationshierarki definieras som *batch ovan* eller *serie ovan*, måste referensdimensionen (**batchnummer** eller **serienummer**) måste alltid anges på beställning. Lagerställeprocesser kan eventuellt fylla i informationen om ett enda batch- eller serienummer finns tillgängligt. Eftersom lagerstället inte är aktiverat för lagerställeprocesser måste användaren alltid specificera alla dimensioner ovan **Plats**.
