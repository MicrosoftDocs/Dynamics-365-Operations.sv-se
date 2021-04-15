---
title: Integrerade platser och lagerställen
description: I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Dataverse.
author: t-benebo
ms.date: 10/09/2019
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
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 533635ece005636dcee4e24d1d132111e1e2b370
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750676"
---
# <a name="integrated-sites-and-warehouses"></a>Integrerade platser och lagerställen

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Dataverse. Driftplatser och driftlagerställen är vanliga koncept i en Supply Chain Management-app. De används för att modellera leveranskedjan för ditt företag.

## <a name="templates"></a>Mallar

Med integrationen med Dataverse finns dessa begrepp och all tillhörande information i Dataverse med datatabellerna för platser och lagerställen i följande tabell.

Finance and Operations-appar | Andra Dynamics 365-appar | beskrivning
--------------------------|---------------------------|---
Webbplatser | msdyn_operationalsites | 
Lagerställen | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]