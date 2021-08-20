---
title: Integrerad moms
description: I det här avsnittet beskrivs integreringen av skattedata mellan Finance and Operations och Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: rhaertle
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: c7e76294944196670ed4b02ebf785c1bed7b5106f73d4b66a15a19c9a4235cbf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738562"
---
# <a name="integrated-tax"></a>Integrerad moms

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt. Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.

## <a name="templates"></a>Mallar

Momsdata inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

| Finance and Operations-appar | Kundengagemangsappar | beskrivning |
|-----------------------------|-----------------------------------|-------------|
[Artikelmomsgrupp](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Skattemyndigheter](mapping-reference.md#193) | msdyn_taxauthorities | |
[Momsbefrielsekod CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Momsgrupper](mapping-reference.md#195) | msdyn_taxgroups | |
[Bokföringsgrupper V2 för momsredovisning](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Källskattekoder](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Källskattegrupper](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
