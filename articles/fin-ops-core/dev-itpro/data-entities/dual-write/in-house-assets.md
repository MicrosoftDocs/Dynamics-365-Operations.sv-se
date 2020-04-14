---
title: Interna tillgångar för service
description: I det här avsnittet beskrivs hur du kan använda Microsoft Dynamics 365 Field Service för att serva både kundtillgångar och interna tillgångar.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 1e423199d0639db5e403e280880036b590149095
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172956"
---
# <a name="in-house-assets-for-servicing"></a>Interna tillgångar för service

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Field Service har utformats för att betjäna kundtillgångar. Tillgångshantering för Dynamics 365 Supply Chain Management har utformats för att upprätthålla anläggningstillgångar. Genom att integrera dessa två appar kan du använda Field Service för att betjäna både kundtillgångar och interna tillgångar. Du kan också klassificera tillgångarna, baserat på en funktionell plats eller hierarki och spåra underhållet på en detaljerad nivå.

Mer information finns i [integrera Dynamics 365 Field Service och Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Mallar

Interna tillgångar inkluderar en samling entitetsmappningar som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

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
