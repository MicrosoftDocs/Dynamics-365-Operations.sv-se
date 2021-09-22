---
title: Standardmomsgrupp och kassarabatt fylls inte i från fakturakontot
description: En standardmomsgrupp och en standardkassarabatt fylls inte i från fakturakontot
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bb984eb17209dc92e336df5ad475bb0f70c6e35c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477625"
---
# <a name="default-tax-group-and-cash-discount-arent-filled-in-from-the-invoice-account"></a>Standardmomsgrupp och kassarabatt fylls inte i från fakturakontot

## <a name="symptoms"></a>Symtom

Om du använder ett fakturakonto som skiljer sig från kundkontot, fylls inte en standard momsgrupp och en standard kassarabatt i från fakturakontot när en inköpsorder skapas.

## <a name="resolution"></a>Lösning

Detta beteende är av design. Standardvärdena för momsgrupp, kassarabatter och annan prisinformation baseras på kundkontot, inte på fakturakontot.
