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
# <a name="transportation-management-zone-master"></a>Transporthantering – zonmall

[!include [banner](../includes/banner.md)]

Transporthantering innebär att du kan dela upp geografiska platser i zoner. Att dela platser i zoner kan vara till hjälp när du vill:

- **Att förenkla transportpriserna** – det kan vara enklare att göra zoner än enskilda platsbaserade priser, särskilt när transportplatser sprids.
- **Optimera lastplanering** – genom att konsolidera belastningar efter zoner.
- **Optimera flödesplanering** – genom att tilldela specifika flödesplaner till specifika zoner.

Du definierar zoner baserat på värdena i fältet metadata (t.ex. land, postnummerintervall eller transportföretag) som kvalificerar varje zon. Zondefinitioner behövs inte om din transport prissättning inte använder ett zonbegrepp.
