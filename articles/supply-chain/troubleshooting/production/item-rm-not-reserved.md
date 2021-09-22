---
title: Artikel RM kan inte reserveras när en produktionsorder släpps
description: 'När du släpper en produktionsorder kan du får felmeddelandet : "Artikel RM kunde inte reserveras helt." Se till att hela kvantiteten är tillgänglig eller reservera artiklar manuellt.'
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 528895252d661bb012f49190c15853989833064d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477659"
---
# <a name="item-rm-cant-be-fully-reserved-when-a-production-order-is-released"></a>Artikel RM kan inte reserveras helt när en produktionsorder släpps

## <a name="symptoms"></a>Symtom

Om inte alla radartiklar för strukturlistan är fysiskt tillgängliga när en produktionsorder släpps till ett lagerställe, och principen **Släpp till lagerställe** anges till *Kräv fullständig reservation* visas följande felmeddelande:

> Objekt RM kunde inte reserveras helt. Se till att hela kvantiteten är tillgänglig, eller reservera artiklarna manuellt om fältet reservation på strukturlisteraden är inställt på manuell eller startad. Det gick inte att släppa ordern till lagerstället eftersom det inte gick att reservera vissa material.

## <a name="resolution"></a>Lösning

Detta är avsiktligt och fungerar som förväntat. Rätta till det här problemet genom att följa de anvisningar som visas i felmeddelandet: "Se till att hela kvantiteten är tillgänglig, eller reservera artiklarna manuellt om fältet Reservation på strukturlisteraden är inställt på Manuell eller Startad."
