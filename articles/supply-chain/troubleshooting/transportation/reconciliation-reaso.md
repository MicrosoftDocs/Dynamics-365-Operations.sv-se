---
title: Du kan bara lägga till huvudkontot som kreditkonto av avstämningsskäl
description: När du ställer in en avstämningsorsak i transporthantering kan du bara lägga till huvudkontot som kreditkonto.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026901"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a>Du kan bara lägga till huvudkontot som kreditkonto av avstämningsskäl

KB-nummer: 4603538

## <a name="symptoms"></a>Symtom

När du ställer in en avstämningsorsak i transporthantering kan du bara lägga till huvudkontot som kreditkonto. Du kan inte lägga till ett kostnadsställe eller någon annan dimension som kreditkonto. Med debetkontot kan du dock välja andra dimensioner.

## <a name="resolution"></a>Upplösning

Om avstämningen inte görs för att betala leverantören men för att kreditera ett visst huvudkonto, tillåter systemet inte att du väljer en ekonomisk dimension för kreditkontot när du ställer in avstämningsorsaken.

Om kontostrukturen kräver ett specifikt ekonomiskt dimensionsvärde för kredithuvudkontot kan den resulterande leverantörsjournalen inte bokföras automatiskt, eftersom värdet för den ekonomiska dimensionen saknas. Därför måste du först ange kreditkontot manuellt med hjälp av sidan **Fakturajournal**.

Eftersom ett dimensionsvärde krävs för kreditkontot kan leverantörsfakturajournalen inte bokföras automatiskt. Du måste bokföra det manuellt när du har lagt till dimensionsvärdet manuellt på huvudkontot för kreditraden.
