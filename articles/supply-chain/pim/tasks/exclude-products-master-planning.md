---
title: Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering
description: Den här proceduren beskriver hur du skapar ett nytt livscykeltillstånd för produkt som exkluderar produkter från huvudplanering och strukturlistenivåberäkningen.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f9573fd220cd8b6a58f81e4d17ca65234f41beb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437527"
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