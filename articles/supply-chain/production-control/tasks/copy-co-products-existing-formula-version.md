---
title: Kopiera samprodukter från en befintlig formelversion
description: I den här proceduren visas hur du kopierar samprodukter från en befintlig formelversion till en annan formelversion för en frisläppt produkt.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 527fd94613d53a3f0ae81834d5bdaad30dca2833
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579242"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a>Kopiera samprodukter från en befintlig formelversion

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du kopierar samprodukter från en befintlig formelversion till en annan formelversion för en frisläppt produkt. Det är en förutsättning att det finns minst en formelversion som associeras med samprodukter. Demonstrationsdataföretaget USP2 används för att skapa den här proceduren.


## <a name="find-a-released-product"></a>Sök efter en frisläppt produkt
1. Gå till Frisläppta produkter.
2. Klicka på Visa filter.
    * Du håller på att lägga till fältet Produktionstyp i dialogrutan Filter.  
3. Klicka på fältet Lägg till ett filter om du vill lägga till fältet Produktionstyp.
    * I nästa steg måste du manuellt ange Formel i fältet Produktiontyp innan du väljer Verkställ. Detta ställer in filtret i listan över frisläppta produkter.  
4. Ange manuellt Formel i fältet Produktionstyp.
5. Klicka på Verkställ.

## <a name="select-a-released-product"></a>Välj en frisläppt produkt
1. Hitta och markera önskad post i listan.
2. Klicka på Formelversioner.
    * I åtgärdsfönstret Teknik, klicka på Formelversioner.  

## <a name="copy-co-products"></a>Kopiera samprodukter
1. Klicka på Formelversion i åtgärdsfönstret.
2. Klicka på Samprodukter.
3. Klicka på Kopiera.
4. Ange eller välj ett värde i fältet Artikelnummer.
5. I fältet Formelversion, ange eller välj ett värde.
6. Klicka på OK.
7. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]