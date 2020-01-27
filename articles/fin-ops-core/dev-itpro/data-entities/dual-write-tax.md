---
title: Integrerad moms
description: I det här avsnittet beskrivs integreringen av momsdata mellan Finance and Operations och Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 86e74086a5a74c7af5f2572d1a653a1658d729c0
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853869"
---
# <a name="integrated-tax"></a>Integrerad moms

[!include [banner](../includes/banner.md)]

Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt. Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.

## <a name="templates"></a>Mallar

Momsdata inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Finance and Operations   | Andra Dynamics 365-appar
-------------------------|---------------------------------
Skattekoder                  | msdyn\_taxcodes.md
Skattegrupper               | msdyn\_taxgroups.md
Artikelmomsgrupper          | msdyn\_taxitemgroups.md
Undantag från skatteplikt           | msdyn\_taxexemptcodes.md
Skattemyndighet          | msdyn\_taxauthorities.md
Källskattekoder      | msdyn\_withholdingtaxcodes.md
Källskattegrupper   | msdyn\_withholdingtaxgroups.md
Momsgrupp för huvudbokskonto | msdyn\_taxpostinggroups  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

