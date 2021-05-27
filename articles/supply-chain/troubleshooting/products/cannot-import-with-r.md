---
title: Du kan inte importera ett objekt med hjälp av entiteten Frisläppta produkter V2
description: Du kan inte importera ett objekt med hjälp av entiteten Frisläppta produkter V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026907"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Du kan inte importera ett objekt med hjälp av entiteten Frisläppta produkter V2

KB-nummer: 4611825

## <a name="symptoms"></a>Symtom

När du försöker importera ett objekt med hjälp av entiteten *Frisläppta produkter V2* visas ett felmeddelande som liknar följande exempel:

> Det går inte att skapa en post i Objekt – spårning av dimensionsgrupper (EcoResTrackingDimensionGroupItem). Artikelnummer: 2040663, Batch. Posten finns redan.

## <a name="resolution"></a>Upplösning

För att importera nyligen frisläppta produkter måste du använda entiteten *Frisläppt produktgenerering V2* istället för entiteten *Frisläppta produkter V2*.
