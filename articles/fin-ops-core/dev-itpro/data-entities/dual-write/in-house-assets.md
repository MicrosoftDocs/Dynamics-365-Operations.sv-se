---
title: Interna tillgångar för service
description: Detta ämne beskriver hur du kan använda Microsoft Dynamics 365 Field Service för att betjäna såväl kundtillgångar som interna tillgångar.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: b3e741c85fcad2abc18879280ef7332ae091c984
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289263"
---
# <a name="in-house-assets-for-servicing"></a>Interna tillgångar för service

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Field Service har utformats för att betjäna kundtillgångar. Tillgångshantering för Dynamics 365 Supply Chain Management har utformats för att upprätthålla anläggningstillgångar. Genom att integrera dessa två appar kan du använda Field Service för att betjäna både kundtillgångar och interna tillgångar. Du kan också klassificera tillgångarna, baserat på en funktionell plats eller hierarki och spåra underhållet på en detaljerad nivå.

Mer information finns i [integrera Dynamics 365 Field Service och Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Mallar

Interna tillgångar inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, enligt följande tabell.

| Finance and Operations-appar | Kundengagemangsappar | beskrivning |
|-----------------------------|-----------------------------------|-------------|
[Tillgångshantering för livscykelmodeller av tillgångar](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[Tillgångshantering för livscykeltillstånd av tillgångar](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[Tillgångstyper för hantering av tillgångar](mapping-reference.md#124) | msdyn_customerassetcategories | |
[Tillgångar för hantering av tillgångar](mapping-reference.md#125) | msdyn_customerassets | |
[Livscykelmodeller för funktionsplatsens tillgångshantering](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[Livscykeltillstånd för funktionsplatsens tillgångshantering](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[Funktionsplatstyper för tillgångshantering](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[Funktionsplatser för tillgångshantering](mapping-reference.md#136) | msdyn_functionallocations | |
[Tillverkare för tillgångshantering](mapping-reference.md#153) | msdyn_manufacturers | |
[Tillgångshanteringsmodeller](mapping-reference.md#154) | msdyn_models | |
[Garanti över tillgångshantering](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
