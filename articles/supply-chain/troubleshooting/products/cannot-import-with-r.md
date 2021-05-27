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
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a><span data-ttu-id="8784e-103">Du kan inte importera ett objekt med hjälp av entiteten Frisläppta produkter V2</span><span class="sxs-lookup"><span data-stu-id="8784e-103">You can't import an item by using the Released products V2 entity</span></span>

<span data-ttu-id="8784e-104">KB-nummer: 4611825</span><span class="sxs-lookup"><span data-stu-id="8784e-104">KB number: 4611825</span></span>

## <a name="symptoms"></a><span data-ttu-id="8784e-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="8784e-105">Symptoms</span></span>

<span data-ttu-id="8784e-106">När du försöker importera ett objekt med hjälp av entiteten *Frisläppta produkter V2* visas ett felmeddelande som liknar följande exempel:</span><span class="sxs-lookup"><span data-stu-id="8784e-106">When you try to import an item by using the *Released products V2* entity, you receive an error message that resembles the following example:</span></span>

> <span data-ttu-id="8784e-107">Det går inte att skapa en post i Objekt – spårning av dimensionsgrupper (EcoResTrackingDimensionGroupItem).</span><span class="sxs-lookup"><span data-stu-id="8784e-107">Cannot create a record in Items - tracking dimension groups (EcoResTrackingDimensionGroupItem).</span></span> <span data-ttu-id="8784e-108">Artikelnummer: 2040663, Batch.</span><span class="sxs-lookup"><span data-stu-id="8784e-108">Item number: 2040663, Batch.</span></span> <span data-ttu-id="8784e-109">Posten finns redan.</span><span class="sxs-lookup"><span data-stu-id="8784e-109">The record already exists.</span></span>

## <a name="resolution"></a><span data-ttu-id="8784e-110">Upplösning</span><span class="sxs-lookup"><span data-stu-id="8784e-110">Resolution</span></span>

<span data-ttu-id="8784e-111">För att importera nyligen frisläppta produkter måste du använda entiteten *Frisläppt produktgenerering V2* istället för entiteten *Frisläppta produkter V2*.</span><span class="sxs-lookup"><span data-stu-id="8784e-111">To import new released products, you must use the *Released product creation V2* entity instead of the *Released products V2* entity.</span></span>
