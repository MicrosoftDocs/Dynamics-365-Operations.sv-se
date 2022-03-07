---
title: Planerad tillverkningsorder måste tidsplaneras innan den kan bekräftas
description: När du försöker bekräfta en planerad order visas ett felmeddelande om att ordern måste tidsplaneras innan den kan bekräftas.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294186"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a>Planerad tillverkningsorder måste tidsplaneras innan den kan bekräftas

Felkod: SYS309802

## <a name="symptoms"></a>Symtom

När du har bekräftat planerade order visas följande felmeddelande:

> Den planerade produktionsordern måste tidsplaneras innan den kan bekräftas.

## <a name="cause"></a>Orsak

De planerade start- och slutdatumen kan inte vara tomma.

## <a name="resolution"></a>Lösning

Följ de här stegen om du vill ange start- och slutdatum för den planerade ordern.

1. Gå till **Huvudplanering \> Huvudplanering \> Planerade order**.
1. Öppna relevant planerad ordern.
1. På snabbflikarna **Allmänt**, i avsnittet **Tidsplanerat**, anger du datum i fälten **Startdatum** och **Slutdatum**.
