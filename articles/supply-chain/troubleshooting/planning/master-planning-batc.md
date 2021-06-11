---
title: Det går inte att filtrera huvudplaneringsartiklar efter relaterade disponeringsgruppvärden
description: Det går inte att filtrera huvudplaneringsartiklar efter relaterade disponeringsgruppvärden.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049491"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a>Det går inte att filtrera huvudplaneringsartiklar efter relaterade disponeringsgruppvärden

KB-nummer: 4612572

## <a name="symptoms"></a>Symtom

Du vill filtrera artiklarna som inkluderas i ett batchjobb för huvudplanering utifrån värdena för relaterade poster från artikel disponeringsregistret. (Du vill till exempel filtrera artiklar efter värdet **Leverantör** och/eller **Disponeringsgrupp**). Med filterinställningarna för batchjobbet kan du skapa en koppling från registret **Artikel** till **Artikeldisponering** och ange sedan fältvärden från artikeldisponeringsregistret i din fråga. När du har slutfört inställningen skapar systemet ändå planerade order för hela artikeldisponeringen, inte bara för de artiklar som matchar de angivna fältvärdena från registret för artikeldisponering.

## <a name="resolution"></a>Lösning

Batchjobbfiltret kan bara filtreras för artiklar. Även om du kan lägga till en koppling till registret **Artikeldisponering**, påverkar inte de filterinställningar som du gör mot registret frågans utdata. Under körning kör systemet planering för alla disponeringsgrupper och alla variationer som de filtrerade artiklarna har. När en artikel redan har inkluderats i körningen påverkas inte planeringsutdata av de disponeringsgrupper som inkluderas i artikelfiltret.
