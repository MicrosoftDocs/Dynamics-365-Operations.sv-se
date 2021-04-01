---
title: Underhåll begärandetyper
description: I det här avsnittet beskrivs hur du ställer in en typ av underhållsbegäran i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e4f622cda62cad13a8146cbc26bc2e5f1a45222
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261199"
---
# <a name="maintenance-request-types"></a>Underhåll begärandetyper

[!include [banner](../../includes/banner.md)]

 

Typer av underhållsbegäran används för att kategorisera underhållsbegäranden. Du kan till exempel ha underhållsbegärandetyper som är relaterade till förebyggande underhåll och korrigerande underhåll. Eller du kanske har en särskild typ av underhållsbegäran som används för att hantera reparation av tillgångar (depotreparation).

En typ av underhållbegäran definierar anslutningen med en livscykeltillståndgrupp för underhållsbegäran (underhållslivscykelmodell). Livscykelmodeller för underhållsbegäran definierar de livscykeltillstånd som kan ställas in för en underhållsbegäran. (Exempel på livscykeltillstånd för underhållsbegäran inkluderar **skapad**, **aktiv** och **avslutad**.)

1. Välj **tillgångshantering** \> **inställningar** \> **underhållbegäran** \> **underhållbegärantyper**.
2. Välj **ny** för att skapa en typ av underhållsbegäran.
3. I fältet **underhållbegärantyp** anger du ett ID för underhållbegärantypen.
4. Ange sedan ett namn i fältet **Namn**.
5. På snabbfliken **allmänt** i fältet **livscykelmodell för underhållsbegäran** väljer du en livscykelmodell för underhållsbegäran.
6. I fältet **arbetsordertyp** väljer du en arbetsorder. När en underhållsbegäran konverteras till en arbetsorder får arbetsordern automatiskt den arbetsordertyp som är relaterad till typen av underhållsbegäran.

Följande illustration visar ett exempel på sidan **underhållsbegärandetyper**.

![Sidan Typer av underhållsbegäran](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]