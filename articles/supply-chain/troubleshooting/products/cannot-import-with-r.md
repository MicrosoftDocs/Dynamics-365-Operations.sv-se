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
ms.openlocfilehash: efd773313f89784d8fca6b37d867e204cb2d06ab29694a19cbec7eed107a8019
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764702"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Du kan inte importera ett objekt med hjälp av entiteten Frisläppta produkter V2

KB-nummer: 4611825

## <a name="symptoms"></a>Symtom

När du försöker importera ett objekt med hjälp av entiteten *Frisläppta produkter V2* visas ett felmeddelande som liknar följande exempel:

> Det går inte att skapa en post i Objekt – spårning av dimensionsgrupper (EcoResTrackingDimensionGroupItem). Artikelnummer: 2040663, Batch. Posten finns redan.

## <a name="resolution"></a>Upplösning

För att importera nyligen frisläppta produkter måste du använda entiteten *Frisläppt produktgenerering V2* istället för entiteten *Frisläppta produkter V2*.
