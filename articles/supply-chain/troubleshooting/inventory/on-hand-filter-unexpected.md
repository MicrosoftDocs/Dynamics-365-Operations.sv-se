---
title: Filterfönstret på listsidan Behållning fungerar inte som förväntat
description: Filter i filterfönstret på sidan Behållningslista filtrerar inte resultat som du förväntar dig.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 2b2b233e22378c8710a63dce83d168bfd89eba7f
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920508"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Filterfönstret på listsidan Behållning fungerar inte som förväntat

## <a name="symptoms"></a>Symtom

Filter i filterfönstret på sidan **Behållningslista** filtrerar inte resultat som du förväntar dig.

## <a name="resolution"></a>Lösning

Sidan **Behållningslista** är monterad i en detaljerad lagerbehållning som inkluderar alla tillgängliga dimensioner. Listan på den här sidan är dock en sammanfattning. Därför kan det hända att rader kombineras från källtabellen genom att värdena aggregeras enligt de dimensioner som visas.

Filtren som anges i filterfönstret gäller för källtabellen, inte den aggregerade listan. Det här beteendet kan ibland ge oväntade resultat, vilket visas i [dessa exempel](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples).

Men [filtren som finns i rutnätet](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *gäller* för den aggregerade listan. Dessa filter inkluderar både snabbfilter överst i rutnätet och filtret för varje kolumnrubrik.
