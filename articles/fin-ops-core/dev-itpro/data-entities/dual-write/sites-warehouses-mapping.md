---
title: Integrerade platser och lagerställen
description: I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Common Data Service.
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
ms.openlocfilehash: 1b9181211bbb65cdfc46e63f3cee0e9f5bc9f6a4
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173072"
---
# <a name="integrated-sites-and-warehouses"></a>Integrerade platser och lagerställen

[!include [banner](../../includes/banner.md)]



I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Common Data Service. Driftplatser och driftlagerställen är vanliga koncept i en Supply Chain Management-app. De används för att modellera leveranskedjan för ditt företag.

## <a name="templates"></a>Mallar

Med integrationen med Common Data Service finns dessa begrepp och all tillhörande information i Common Data Service med dataenheterna för platser och lagerställen i följande tabell.

Finance and Operations-appar | Andra Dynamics 365-appar | Beskrivning
--------------------------|---------------------------|---
Webbplatser | msdyn_operationalsites | 
Lagerställen | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

