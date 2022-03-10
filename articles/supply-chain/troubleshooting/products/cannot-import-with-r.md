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
ms.openlocfilehash: bf6eb0eb755de3f2842c235946bfd7ccad04ccf7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474734"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Du kan inte importera ett objekt med hjälp av entiteten Frisläppta produkter V2

KB-nummer: 4611825

## <a name="symptoms"></a>Symtom

När du försöker importera ett objekt med hjälp av entiteten *Frisläppta produkter V2* visas ett felmeddelande som liknar följande exempel:

> Det går inte att skapa en post i Objekt – spårning av dimensionsgrupper (EcoResTrackingDimensionGroupItem). Artikelnummer: 2040663, Batch. Posten finns redan.

## <a name="resolution"></a>Upplösning

För att importera nyligen frisläppta produkter måste du använda entiteten *Frisläppt produktgenerering V2* istället för entiteten *Frisläppta produkter V2*.
