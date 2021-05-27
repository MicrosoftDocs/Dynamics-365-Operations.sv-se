---
title: Huvudplanering genererar planerade order för fiktiva produkter
description: Planerade order genereras för fiktiva produkter när huvudplaneringen har körts.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026922"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>Huvudplanering genererar planerade order för fiktiva produkter

KB-nummer: 4614729

## <a name="symptoms"></a>Symtom

Planerade order genereras för fiktiva produkter när huvudplaneringen har körts.

## <a name="resolution"></a>Upplösning

Inställningen för alternativet **Fiktiv** för frisläppta produkter bestämmer standardradtypen i strukturlistan (BOM). När alternativet **Fiktiv** är inställt på *Ja* skapar systemet fortfarande planerade order för artikeln, men alternativet **Direkt härlett behov** för varje planerad order ställs in på *Ja*. Därför kan den planerade produktionsordern inte bekräftas på egen hand. I stället inkluderas den alltid automatiskt när den överordnade produktionsordern blir bekräftad. Strukturlisteraderna för den planerade fiktiva ordern inkluderas dessutom i strukturlistan för den överordnade produktionsordern.
