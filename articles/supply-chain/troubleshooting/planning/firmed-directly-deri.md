---
title: Direkt härledda bekräftade order bearbetas av ett arbetsflöde för granskning
description: Direkt härledda bekräftade order bearbetas av ett arbetsflöde med statusen Under granskning.
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
ms.openlocfilehash: d20f1c1d6e8fc83dd996b04bf0321a41f7b39290f306d1ac9f4fcd17514832e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721185"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a>Direkt härledda bekräftade order bearbetas av ett arbetsflöde för granskning

KB-nummer: 4612450

## <a name="symptoms"></a>Symtom

Direkt härledda bekräftade order bearbetas av ett arbetsflöde med statusen *Under granskning*.

## <a name="resolution"></a>Upplösning

När ändringsspårning har aktiverats tilldelas statusen *Under granskning* till bekräftade härledda order (inköpsorder för underleverantörer). Om en inköpsorder härleds (en inköpsorder för underleverantör) skickas den bara till ett arbetsflöde. Om en inköpsorder är en bekräftad planerad inköpsorder godkänns den automatiskt för att säkerställa att planeringsmotorn inte skapar nya planerade order medan inköpsordern fortfarande har statusen *Utkast*.
