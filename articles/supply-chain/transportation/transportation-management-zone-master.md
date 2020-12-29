---
title: Transporthantering – zonmall
description: Det här ämnet förklarar hur transporthantering innebär att du kan dela upp geografiska platser i zoner.
author: Henrikan
manager: ''
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSZoneMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2112e7131281cd485b580fd71536981c1ba4aefd
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438135"
---
# <a name="transportation-management-zone-master"></a><span data-ttu-id="5d804-103">Transporthantering – zonmall</span><span class="sxs-lookup"><span data-stu-id="5d804-103">Transportation management zone master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d804-104">Transporthantering innebär att du kan dela upp geografiska platser i zoner.</span><span class="sxs-lookup"><span data-stu-id="5d804-104">Transport management lets you divide geographic locations into zones.</span></span> <span data-ttu-id="5d804-105">Att dela platser i zoner kan vara till hjälp när du vill:</span><span class="sxs-lookup"><span data-stu-id="5d804-105">Dividing locations into zones can help to:</span></span>

- <span data-ttu-id="5d804-106">**Att förenkla transportpriserna** – det kan vara enklare att göra zoner än enskilda platsbaserade priser, särskilt när transportplatser sprids.</span><span class="sxs-lookup"><span data-stu-id="5d804-106">**Simplify transportation pricing** – Zone-wise pricing can be simpler than individual location-based pricing, especially when transportation locations are scattered.</span></span>
- <span data-ttu-id="5d804-107">**Optimera lastplanering** – genom att konsolidera belastningar efter zoner.</span><span class="sxs-lookup"><span data-stu-id="5d804-107">**Optimize load planning** – By consolidating loads by zones.</span></span>
- <span data-ttu-id="5d804-108">**Optimera flödesplanering** – genom att tilldela specifika flödesplaner till specifika zoner.</span><span class="sxs-lookup"><span data-stu-id="5d804-108">**Optimize route planning** – By assigning specific route plans to specific zones.</span></span>

<span data-ttu-id="5d804-109">Du definierar zoner baserat på värdena i fältet metadata (t.ex. land, postnummerintervall eller transportföretag) som kvalificerar varje zon.</span><span class="sxs-lookup"><span data-stu-id="5d804-109">You define zones based on the metadata field values (such as country, zip code range, or carrier service) that qualify each zone.</span></span> <span data-ttu-id="5d804-110">Zondefinitioner behövs inte om din transport prissättning inte använder ett zonbegrepp.</span><span class="sxs-lookup"><span data-stu-id="5d804-110">Zone definitions aren't required if your transportation pricing doesn't employ a zone concept.</span></span>
