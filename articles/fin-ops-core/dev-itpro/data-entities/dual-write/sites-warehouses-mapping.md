---
title: Integrerade platser och lagerställen
description: I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Dataverse.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: d192343d78f9248e4d1232d6aee1a1f800383805
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679330"
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

