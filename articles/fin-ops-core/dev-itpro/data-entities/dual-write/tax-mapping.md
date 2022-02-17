---
title: Integrerad moms
description: I det här avsnittet beskrivs integreringen av momsdata mellan Finance and Operations och Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 532e6603b74ad0293d65684d2d6858ef31fbc496
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063197"
---
# <a name="integrated-tax"></a>Integrerad moms

[!include [banner](../../includes/banner.md)]



Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt. Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.

## <a name="templates"></a>Mallar

Momsdata inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

| Finance and Operations-appar | Kundengagemangsappar | Beskrivning |
|-----------------------------|-----------------------------------|-------------|
[Artikelmomsgrupp](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Skattemyndigheter](mapping-reference.md#193) | msdyn_taxauthorities | |
[Momsbefrielsekod CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Momsgrupper](mapping-reference.md#195) | msdyn_taxgroups | |
[Bokföringsgrupper V2 för momsredovisning](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Källskattekoder](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Källskattegrupper](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
