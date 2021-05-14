---
title: Interna tillgångar för service
description: Detta ämne beskriver hur du kan använda Microsoft Dynamics 365 Field Service för att betjäna såväl kundtillgångar som interna tillgångar.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: ebda6b5679ec601513fb6d046725b396e69fe0f3
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941424"
---
# <a name="in-house-assets-for-servicing"></a>Interna tillgångar för service

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Field Service har utformats för att betjäna kundtillgångar. Tillgångshantering för Dynamics 365 Supply Chain Management har utformats för att upprätthålla anläggningstillgångar. Genom att integrera dessa två appar kan du använda Field Service för att betjäna både kundtillgångar och interna tillgångar. Du kan också klassificera tillgångarna, baserat på en funktionell plats eller hierarki och spåra underhållet på en detaljerad nivå.

Mer information finns i [integrera Dynamics 365 Field Service och Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Mallar

Interna tillgångar inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, enligt följande tabell.

| Finance and Operations-appar | Modellstyrda appar i Dynamics 365 | beskrivning |
|-----------------------------|-----------------------------------|-------------|
| Tillgångshantering för livscykelmodeller av tillgångar | msdyn\_assetlifecyclemodels | |
| Tillgångshantering för livscykeltillstånd av tillgångar | msdyn\_assetlifecyclestates | |
| Tillgångar för hantering av tillgångar | msdyn\_customerassets | |
| Tillgångstyper för hantering av tillgångar | msdyn\_customerassetcategories | |
| Livscykelmodeller för funktionsplatsens tillgångshantering | msdyn\_functionallocationlifecyclemodels | |
| Livscykeltillstånd för funktionsplatsens tillgångshantering | msdyn\_functionallocationlifecyclestates | |
| Funktionsplatser för tillgångshantering | msdyn\_functionallocations | |
| Funktionsplatstyper för tillgångshantering | msdyn\_functionallocationtypes | |
| Tillverkare för tillgångshantering | msdyn\_manufacturers | |
| Tillgångshanteringsmodeller | msdyn\_models | |
| Garanti över tillgångshantering | msdyn\_warranties | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]