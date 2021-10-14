---
title: Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering
description: Den här proceduren beskriver hur du skapar ett nytt livscykeltillstånd för produkt som exkluderar produkter från huvudplanering och strukturlistenivåberäkningen.
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7f72be341b81515b7c5540d66f61647df93af41
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567041"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering

[!include [banner](../../includes/banner.md)]

Den här proceduren beskriver hur du skapar ett nytt livscykeltillstånd för produkt som exkluderar produkter från huvudplanering och strukturlistenivåberäkningen.


## <a name="create-an-obsolete-state"></a>Skapa ett föråldrat tillstånd
1. Gå till Produktinformationshantering > Inställningar > produktlivscykeltillstånd.
2. Klicka på Ny.
3. Ange ett värde i fältet Tillstånd.
4. Välj Nej i fältet Är aktiv för planering.
5. Ange ett värde i fältet Beskrivning.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Koppla föråldrade tillståndet till frisläppt produkt
1. Stäng sidan.
2. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
3. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Söknamn med värdet "M00".
4. Klicka på Redigera.
5. Markera vald rad i listan.
6. Ange eller välj ett värde i fältet produktlivscykeltillstånd.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]