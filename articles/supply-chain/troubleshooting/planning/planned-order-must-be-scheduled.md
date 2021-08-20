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
ms.openlocfilehash: a89f5f98895be5b934dbdc1194fa58b9af34f9cbc7f5e2092f6f47791dd52400
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777753"
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
