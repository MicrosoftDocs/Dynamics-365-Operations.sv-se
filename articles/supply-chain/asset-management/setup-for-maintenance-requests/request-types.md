---
title: Typer av underhållsbegäranden
description: I denna artikel beskrivs hur du konfigurerar en typ av underhållsbegäran i Tillgångshantering.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a2d707cc9c0aa4863968651a8434883cc1322eb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888713"
---
# <a name="maintenance-request-types"></a>Underhåll begärandetyper

[!include [banner](../../includes/banner.md)]

 

Typer av underhållsbegäran används för att kategorisera underhållsbegäranden. Du kan till exempel ha underhållsbegärandetyper som är relaterade till förebyggande underhåll och korrigerande underhåll. Eller du kanske har en särskild typ av underhållsbegäran som används för att hantera reparation av tillgångar (depotreparation).

En typ av underhållbegäran definierar anslutningen med en livscykeltillståndgrupp för underhållsbegäran (underhållslivscykelmodell). Livscykelmodeller för underhållsbegäran definierar de livscykeltillstånd som kan ställas in för en underhållsbegäran. (Exempel på livscykeltillstånd för underhållsbegäran inkluderar **skapad**, **aktiv** och **avslutad**.)

1. Välj **Tillgångshantering** \> **inställningar** \> **underhållbegäran** \> **underhållbegärantyper**.
2. Välj **ny** för att skapa en typ av underhållsbegäran.
3. I fältet **underhållbegärantyp** anger du ett ID för underhållbegärantypen.
4. Ange sedan ett namn i fältet **Namn**.
5. På snabbfliken **allmänt** i fältet **livscykelmodell för underhållsbegäran** väljer du en livscykelmodell för underhållsbegäran.
6. I fältet **arbetsordertyp** väljer du en arbetsorder. När en underhållsbegäran konverteras till en arbetsorder får arbetsordern automatiskt den arbetsordertyp som är relaterad till typen av underhållsbegäran.

Följande illustration visar ett exempel på sidan **underhållsbegärandetyper**.

![Sidan Typer av underhållsbegäranden.](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]