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
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6527c4887ccd3085d63dd64c104a94e6354f536b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996477"
---
# <a name="transportation-management-zone-master"></a>Transporthantering – zonmall

[!include [banner](../includes/banner.md)]

Transporthantering innebär att du kan dela upp geografiska platser i zoner. Att dela platser i zoner kan vara till hjälp när du vill:

- **Att förenkla transportpriserna** – det kan vara enklare att göra zoner än enskilda platsbaserade priser, särskilt när transportplatser sprids.
- **Optimera lastplanering** – genom att konsolidera belastningar efter zoner.
- **Optimera flödesplanering** – genom att tilldela specifika flödesplaner till specifika zoner.

Du definierar zoner baserat på värdena i fältet metadata (t.ex. land, postnummerintervall eller transportföretag) som kvalificerar varje zon. Zondefinitioner behövs inte om din transport prissättning inte använder ett zonbegrepp.
