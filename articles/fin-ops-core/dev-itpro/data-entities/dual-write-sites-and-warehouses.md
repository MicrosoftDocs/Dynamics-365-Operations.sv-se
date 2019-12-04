---
title: Integrerade platser och lagerställen
description: I det här avsnittet beskrivs integreringen av plats- och lagerställedata mellan Finance and Operations och Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 4cf402e2811aaf92ddfa78eaf6d8887d88d93cbc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771008"
---
# <a name="integrated-sites-and-warehouses"></a>Integrerade platser och lagerställen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs integreringen av plats- och lagerställedata mellan Finance and Operations och Common Data Service. Driftplatser och driftlagerställen är vanliga koncept i en Supply Chain Management-app. De används för att modellera leveranskedjan för ditt företag.

## <a name="templates"></a>Mallar

Med integrationen med Common Data Service finns dessa begrepp och all tillhörande information i Common Data Service med dataenheterna för platser och lagerställen i följande tabell.

Finance and Operations-appar | Andra Dynamics 365-appar | Beskrivning
--------------------------|---------------------------|---
Webbplatser | msdyn_operationalsites | 
Lagerställen | msdyn_warehouses | 

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [operational sites](dual-write/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](dual-write/InventWarehouseEntity-msdyn-warehouse.md)]

