---
title: Felsöka produktkonfiguratorn
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktkonfiguratorn.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e6cfeb6a2b4166dfa9a5a5cc1b7d3d913b865ce2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999616"
---
# <a name="troubleshoot-the-product-configurator"></a>Felsöka produktkonfiguratorn

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktkonfiguratorn.

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a>Artikeltext skrivs över när jag konfigurerar en produkt på en försäljningsorderrad.

### <a name="issue-description"></a>Problembeskrivning

Det här problemet uppstår när du skapar en försäljningsorderrad för en konfigurerbar artikel och sedan ändrar artikelns text. När du konfigurerar artikeln och sedan väljer **OK** skrivs texten över med standardtexten.

### <a name="issue-resolution"></a>Problemlösning

Detta är ett förväntat beteende. Textfältet innehåller variantnamnet, som endast fylls i när du har konfigurerat raden. Därför måste du ändra texten när du har konfigurerat raden, inte före.

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Heltalsattribut avrundas felaktigt när produkt konfigurationsmodeller beräknas.

### <a name="issue-description"></a>Problembeskrivning

Det här problemet kan uppstå när du utför följande serie åtgärder:

1. Ställ in följande attribut i en modell för produktionskonfiguration:

    - Indata (heltal)
    - Procent (decimal)
    - Resultat (heltal)

2. Skapa en beräkning som har följande uttryck:

    *Resultat* = *indata* × *procent* ÷ 100

I det här fallet har heltalsresultatet inte alltid avrundats korrekt. Indata är till exempel 1 000 och procentsatsen är 2,40. Därför förväntar du att heltalsresultatet ska vara 24 eftersom 2,40 procent av 1 000 är 24 (eller 24,00 i decimalform). I stället visas resultatet 23. När procentsatsen är 2,39 avrundas dock beräkningen till 24 i stället för 23. När procentsatsen är 2,50 avrundas beräkningen till 25, som förväntat.

### <a name="issue-resolution"></a>Problemlösning

Det här problemet beror på det sätt som Microsoft Solver Foundation internt representerar tal genom att använda bråktal. I föregående exempel representeras resultatet av beräkningen där procentsatsen är 2,40 som 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375. När .NET skickar det här värdet som ett heltal returneras 23.

Det här beteendet ändras inte eftersom andra scenarier är beroende av den. I föregående exempel kan du åtgärda problemet genom att införa ytterligare ett decimalattribut och en beräkning.

Du kan till exempel ställa in följande attribut i en modell för produktionskonfiguration:

- Indata (heltal)
- Procent (decimal)
- ResultDecimal (decimal)
- ResultInteger (heltal)

Du kan sedan lägga till följande beräkningar:

- *ResultDecimal* = *Indata* × *Procent* ÷ 100
- *ResultInteger* = *ResultDecimal*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]