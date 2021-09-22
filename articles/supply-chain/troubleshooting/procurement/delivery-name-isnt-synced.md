---
title: Leveransnamnet synkroniseras inte efter ändring av leveransadress för inköpsorder
description: När du har ändrat leveransadressen i ett inköpsorderhuvud synkroniseras inte leveransnamnet
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 588d1ef6250d249aa4fc9da4f5125e9a34c0255f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477600"
---
# <a name="the-delivery-name-isnt-synced-after-changing-a-purchase-order-delivery-address"></a>Leveransnamnet synkroniseras inte efter ändring av leveransadress för inköpsorder

## <a name="symptoms"></a>Symtom

Adressen i huvudet på en inköpsorder uppdateras till en adress som inte är en leveransadress. Även om adressen uppdateras på inköpsordern uppdateras inte leveransnamnet baserat på den uppdaterade adressen.

## <a name="resolution"></a>Lösning

Detta beteende är av design. Den valda adressen måste klassificeras som en leveransadress. Annars uppdateras inte leveransnamnet utifrån den valda adressen.
