---
title: Kan inte göra lagerreservationer eftersom 0,00 är tillgängligt
description: Du får ett felmeddelande om att systemet kan inte göra reservationer eftersom bara 0,00 är tillgängliga i lagret. Det här problemet orsakas troligen av öppet arbete.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 75d72f7ee1bdecca5a087b75b1de9907b9d244ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477663"
---
# <a name="system-cant-make-reservations-because-000-are-available-in-the-inventory"></a>Systemet kan inte göra reservationer eftersom 0,00 är tillgängliga i lagret

## <a name="symptoms"></a>Symtom

Det här problemet kan uppstå om systemet inte kan uppdatera en lagerkvantitet eftersom det inte finns tillräckligt många lagertransaktioner med de angivna dimensionerna. Följande felmeddelande visas:

> Fysisk behållning Webbplats=%1, Lagerställe=%2, Lagerstatus=tillgänglig, batchnummer=%3, Ägare=%4: %5 kan inte reserveras eftersom endast 0,00 är tillgängligt i lagret.

## <a name="resolution"></a>Lösning

Det här problemet orsakas troligen av öppet arbete. Antingen slutför du arbetet eller tar emot det utan att arbetet skapas. Se till att inga lagertransaktioner fysiskt reserverar kvantiteten. Dessa transaktioner kan till exempel öppna kvalitetsorder, lagerspärrposter och utleveransorder.
