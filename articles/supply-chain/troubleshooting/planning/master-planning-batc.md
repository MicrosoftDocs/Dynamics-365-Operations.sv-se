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
ms.openlocfilehash: 9750a73f0962179512c5e21a614a276c313ff975b7494f31589ca936886ecf6e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781403"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a>Det går inte att filtrera huvudplaneringsartiklar efter relaterade disponeringsgruppvärden

KB-nummer: 4612572

## <a name="symptoms"></a>Symtom

Du vill filtrera artiklarna som inkluderas i ett batchjobb för huvudplanering utifrån värdena för relaterade poster från artikel disponeringsregistret. (Du vill till exempel filtrera artiklar efter värdet **Leverantör** och/eller **Disponeringsgrupp**). Med filterinställningarna för batchjobbet kan du skapa en koppling från registret **Artikel** till **Artikeldisponering** och ange sedan fältvärden från artikeldisponeringsregistret i din fråga. När du har slutfört inställningen skapar systemet ändå planerade order för hela artikeldisponeringen, inte bara för de artiklar som matchar de angivna fältvärdena från registret för artikeldisponering.

## <a name="resolution"></a>Lösning

Batchjobbfiltret kan bara filtreras för artiklar. Även om du kan lägga till en koppling till registret **Artikeldisponering**, påverkar inte de filterinställningar som du gör mot registret frågans utdata. Under körning kör systemet planering för alla disponeringsgrupper och alla variationer som de filtrerade artiklarna har. När en artikel redan har inkluderats i körningen påverkas inte planeringsutdata av de disponeringsgrupper som inkluderas i artikelfiltret.
