---
title: Integrerad moms
description: I den här artikeln beskrivs integreringen av momsdata mellan Ekonomi och drift och Dataverse.
author: josaw
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 8f148b710e2294edf1e402b9b8b22cb24e60a1f2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288807"
---
# <a name="integrated-tax"></a>Integrerad moms

[!include [banner](../../includes/banner.md)]



Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt. Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.

## <a name="templates"></a>Mallar

Momsdata inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

| Appar för ekonomi och drift | Kundengagemangsappar | Beskrivning |
|-----------------------------|-----------------------------------|-------------|
[Artikelmomsgrupp](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Skattemyndigheter](mapping-reference.md#193) | msdyn_taxauthorities | |
[Momsbefrielsekod CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Momsgrupper](mapping-reference.md#195) | msdyn_taxgroups | |
[Bokföringsgrupper V2 för momsredovisning](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Källskattekoder](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Källskattegrupper](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

