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
ms.openlocfilehash: fc3381dab77cf80c0fd65f3bc27c11b814e72368631bd0e2145aac0be4f4fba4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760380"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>Ackumulation av kundrabatter misslyckas när artikelrabattgrupper används

KB-nummer: 4611372

## <a name="symptoms"></a>Symtom

När du använder kundrabattavtal (av typen *belopp*) i kombination med artikelrabattgrupper beräknas rabatter, men ackumulationen misslyckas.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat. Artikelgrupper grupperar bara objekt som har samma tröskelvärdesvillkor. Rabattvillkoret (tröskelvärdet) ställs mot beloppet för varje artikel, inte mot det ackumulerade beloppet för någon artikel i artikelgruppen.
