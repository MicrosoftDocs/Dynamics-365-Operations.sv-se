---
title: Maximalt antal decimaler för lagerhållningsenheten är 0
description: När du försöker bokföra en lagertransaktion eller en lagerreservation visas felmeddelandet "Maximalt antal decimaler för lagerhållningsenheten är 0".
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9dec198e2d77efd2253c80e14d15791cc37f88e1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477671"
---
# <a name="maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Maximalt antal decimaler för lagerhållningsenheten är 0


## <a name="symptoms"></a>Symtom

När du försöker bokföra en lagertransaktion eller en lagerreservation visas följande felmeddelande:

> Maximalt antal decimaler för lagerhållningsenheten är 0.

Det här problemet uppstår när lagertransaktionskvantiteten anges som ett decimalvärde som är under den nivå av precision som fältet stöder. En kvantitet på *0,5* har till exempel angetts för en lagertransaktion, men endast heltalskvantiteter stöds. Därför bör värdet vara *1* i stället för *0,5*.

## <a name="resolution"></a>Lösning

1. Kör följande skript på din SQL Server-instans för att avrunda kvantiteter i lagertransaktionerna. Det här skriptet kommer att korrigera värden i tabellen **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Kör en konsekvenskontroll där alternativet **åtgärda fel** är aktiverat. Denna kontroll kommer att korrigera värden i tabellen **inventSum**.

> [!IMPORTANT]
> Vi rekommenderar starkt att du noggrant redigerar skriptet som krävs för din miljö, testar den i en testmiljö och sedan kontrollerar resulterande data innan du kör skriptet i en produktionsmiljö.
