---
title: Underhåll begärandetyper
description: I det här avsnittet beskrivs hur du ställer in en typ av underhållsbegäran i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19d529df6c8aab036de59502b4f14101e1a07707
ms.sourcegitcommit: 2c73749779274e0b0abbcb4041bbc1df0fb6d6e4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/26/2019
ms.locfileid: "1790541"
---
# <a name="maintenance-request-types"></a>Underhåll begärandetyper

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Typer av underhållsbegäran används för att kategorisera underhållsbegäranden. Du kan till exempel ha underhållsbegärandetyper som är relaterade till förebyggande underhåll och korrigerande underhåll. Eller du kanske har en särskild typ av underhållsbegäran som används för att hantera reparation av tillgångar (depotreparation).

En typ av underhållbegäran definierar anslutningen med en livscykeltillståndgrupp för underhållsbegäran (underhållslivscykelmodell). Livscykelmodeller för underhållsbegäran definierar de livscykeltillstånd som kan ställas in för en underhållsbegäran. (Exempel på livscykeltillstånd för underhållsbegäran inkluderar **skapad**, **aktiv**och **avslutad**.)

1. Välj **tillgångshantering** \> **inställningar** \> **underhållbegäran** \> **underhållbegärantyper**.
2. Välj **ny** för att skapa en typ av underhållsbegäran.
3. I fältet **underhållbegärantyp** anger du ett ID för underhållbegärantypen.
4. Ange sedan ett namn i fältet **Namn**.
5. På snabbfliken **allmänt** i fältet **livscykelmodell för underhållsbegäran** väljer du en livscykelmodell för underhållsbegäran.
6. I fältet **arbetsordertyp** väljer du en arbetsorder. När en underhållsbegäran konverteras till en arbetsorder får arbetsordern automatiskt den arbetsordertyp som är relaterad till typen av underhållsbegäran.

Följande illustration visar ett exempel på sidan **underhållsbegärandetyper**.

![Figur 1](media/07-setup-for-requests.png)
