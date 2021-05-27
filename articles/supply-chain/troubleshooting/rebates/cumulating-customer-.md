---
title: Ackumulation av kundrabatter misslyckas när artikelrabattgrupper används
description: När du använder kundrabattavtal i kombination med artikelrabattgrupper beräknas rabatter, men ackumulationen misslyckas.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026905"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>Ackumulation av kundrabatter misslyckas när artikelrabattgrupper används

KB-nummer: 4611372

## <a name="symptoms"></a>Symtom

När du använder kundrabattavtal (av typen *belopp*) i kombination med artikelrabattgrupper beräknas rabatter, men ackumulationen misslyckas.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat. Artikelgrupper grupperar bara objekt som har samma tröskelvärdesvillkor. Rabattvillkoret (tröskelvärdet) ställs mot beloppet för varje artikel, inte mot det ackumulerade beloppet för någon artikel i artikelgruppen.
