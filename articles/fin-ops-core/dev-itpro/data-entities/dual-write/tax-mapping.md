---
title: Integrerad moms
description: I det här avsnittet beskrivs integreringen av skattedata mellan Finance and Operations och Common Data Service.
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
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 68461f375c6d5b04f224331dc192c921cf3c4d04
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979339"
---
# <a name="integrated-tax"></a>Integrerad moms

[!include [banner](../../includes/banner.md)]



Momsinställningsdata definierar inställningen för både indirekta skatter (GST, moms) och källskatt. Den beskriver momsberäkningsregeln, momssatsen, skatteredovisningen, kvittningen och andra begrepp.

## <a name="templates"></a>Mallar

Momsdata inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Finance and Operations-appar | Modellstyrda appar i Dynamics 365 | beskrivning |
-------------------------|---------------------------------|----|
Artikelmomsgrupp | msdyn_taxitemgroups |
Skattemyndigheter | msdyn_taxauthorities |
Momsbefrielsekod CDS | msdyn_taxexemptcodes |
Momsgrupper | msdyn_taxgroups |
Bokföringsgrupper V2 för momsredovisning | msdyn_taxpostinggroups |
Källskattekoder | msdyn_withholdingtaxcodes |
Källskattegrupper | msdyn_withholdingtaxgroups | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

