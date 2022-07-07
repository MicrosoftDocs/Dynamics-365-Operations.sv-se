---
title: Minska antalet dagar på abonnemangsavgifter
description: Om du vill minska antalet dagar för en befintlig abonnemangsavgift kan du skapa en ny transaktion där du tar bort en tidsperiod som inte längre ska ingå i intervallet för abonnemangsavgiften.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 370722d5c2f66e316d7c37f711cdd086bc53f6a8
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014834"
---
# <a name="reduce-the-days-on-subscription-fees"></a>Minska antalet dagar på abonnemangsavgifter 

[!include [banner](../includes/banner.md)]


Om du vill minska antalet dagar för en befintlig abonnemangsavgift kan du skapa en ny transaktion där du tar bort en tidsperiod som inte längre ska ingå i intervallet för abonnemangsavgiften.

## <a name="reduce-the-days-on-a-subscription-fee"></a>Minska antalet dagar för en abonnemangsavgift

1.  Klicka på **Servicehantering** \> **Serviceabonnemang** \> **Alla serviceabonnemang**. Välj serviceabonnemanget, och i åtgärdsfönstret, klickar du på **Abonnemangsavgifter**

2.  I fältet **abonnemang** väljer du **reduceringsdagar**.

3.  Ange datumintervallet i fältet **Från-datum** och **Till-datum** för abonnemangsavgiften som du vill ta bort från abonnemangsavgiftsperioden, och klicka på **OK**.

Om du vill visa den transaktion som skapas klickar du på **Abonnemang**, klicka på **Avgiftstransaktioner**.

## <a name="example"></a>Exempel

Om en abonnemangstransaktionsperiod löper från 1 januari till 31 januari, och du vill minska perioden med 10 dagar, skapar du en ny transaktion där reduceringsperioden är 1 januari till den 10 januari. (Reduceringsperioden kan också vara 5 januari till 15 januari eller någon annan 10-dagars period.)

Om **Från-datum** för reduceringsperioden är 21 januari (31 minus 10) kan du också ställa in **Till-datum** till något datum efter 31 januari och 10 dagar tas ändå bort från avgiftstransaktionsperioden.

## <a name="see-also"></a>Se även

[Exempel på avdragsdagar](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]