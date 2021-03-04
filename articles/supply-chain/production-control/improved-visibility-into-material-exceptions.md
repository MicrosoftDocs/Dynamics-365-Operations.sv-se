---
title: Insyn i materialundantag
description: Det här avsnittet beskriver hur du kan få bättre insyn i undantag för råmaterial för produktionsorder och batchorder.
author: johanhoffmann
manager: tfehr
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, WHSProdWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 0c17997d9dd04559fb7022fe39bb2b961c1cfc4a
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438015"
---
# <a name="visibility-into-material-exceptions"></a>Insyn i materialundantag

[!include [banner](../includes/banner.md)]

I arbetsytan **Produktionsgolvsledning** ger tre paneler bättre insyn i undantagen för råmaterial för tillverkningsorder och batchorder:

- Ej frisläppta materialrader som behöver åtgärdas
- Obearbetade påfyllnader behöver åtgärdas
- Öppet lagerarbete som behöver åtgärdas

För alla tre paneler jämförs datumet för råmaterial av strukturlistans rader och formelraderna mot arbetsytans datum samt filtren för **Produktionsenhet**, **Resursgrupp**, och **Resurs** som är inställda på menyn **Konfigurera min arbetsyta**. Som standard är arbetsytans datum inställt på det aktuella datumet, men du kan justera det.

En outgiven strukturlisterad eller formelrad kräver åtgärd om råmaterialdatumet för raden är samma som eller tidigare än datumet för arbetsytan och om de uppfyller de villkor som anges av filtren i arbetsytan.

I följande bild representerar den blå stapeln ett produktionsjobb som har tidsplanerats för en resurs. Jobbet är planerat att starta 1 maj 2017 (2017/05/01). Datumet är råmaterialdatumet. Med andra ord måste materialet som tilldelas jobbet på strukturlistan och formelraderna alltså vara klart detta datum. Det andra datumet i bilden, 6 maj 2017 (2017/05/06), representerar arbetsytans datum. I det här exemplet är råmaterialdatumet tidigare än arbetsytans datum. Därför har datumet när förbrukningen av råmaterial skulle starta passerat och strukturlistan och formelraderna uppfyller kraven för åtgärd.

![Exempel på produktionsjobb där råmaterialdatumet tidigare än arbetsytans datum](./media/improved-visibility.png)

## <a name="unreleased-material-lines-needing-attention"></a>Ej frisläppta materialrader som behöver åtgärdas

En strukturlista eller formelrad kan frisläppas till lagerstället på tre sätt:

- Som en del av en order eller batchorderfrisläppning
- Som en manuell frisläppning
- Automatiskt via ett batch-jobb

Mer information finns i [Frisläpp strukturliste- och formelrader till lagerstället](releasing-bom-and-formula-lines-to-warehouse.md). 

Om en strukturlista eller formelrad inte har frisläppts eller endast delvis har frisläppts och arbetsytans datum- och filterkriterier uppfylls kommer raden att inkluderas i beräkningen av det nummer som visas på panelen **Ej frisläppta materialrader som behöver åtgärdas**.

När du väljer panelen öppnas sidan **Frisläppning till lagerställe**. Denna sida visar antalet ej frisläppta strukturliste- och formelrader som indikeras av numret på panelen. De ej frisläppta raderna visas i det övre rutnätet. Det här rutnätet visar den kvantitet som ursprungligen beräknades för raden, den kvantitet som redan har frisläppts och återstående antal som fortfarande måste frisläppas. Du kan lägga till rader från det övre rutnätet till det nedre rutnätet. Från det nedre rutnätet kan du sedan frisläppa de markerade raderna till lagret. Från det nedre rutnätet kan du även justera kvantiteten som ska frisläppas så att endast en delkvantitet frisläpps.

## <a name="unprocessed-waves-needing-attention"></a>Obearbetade påfyllnader behöver åtgärdas

När du frisläpper strukturliste- eller formelrad läggs den till i en ny produktionspåfyllnad eller en befintlig öppen påfyllnad, beroende på produktionspåfyllnadsmallen. Genom konfigurationen av påfyllnadsmallen kan du också ställa in en påfyllnad att bearbetas automatiskt när du frisläpper strukturliste- eller formelraden. När påfyllnaden bearbetas, genereras lagerställearbete för plockning av råmaterial. Om påfyllnadsmallen är konfigurerad så att påfyllnad inte bearbetas vid tiden för frisläppningen kommer påfyllnaden att kvarstå i ett obearbetat tillstånd. Panelen **Obearbetade påfyllnader behöver åtgärdas** visar antalet strukturliste- och formelrader som har frisläppts till lagret på obearbetade påfyllningar och som har ett råmaterialdatum som infaller tidigare än eller samtidigt som arbetsytans datum. Raderna måste också förbrukas av en verksamhetsresurs som tillämpas på arbetsytans filter.

När panelen är markerad öppnas sidan **Alla produktionspåfyllnader**. Den här sidan filtreras av antalet öppna påfyllningar som innehåller påfyllnadsrader från frisläppt strukturliste- och formelrader som uppfyller villkoren för panelen. Från sidan **Alla produktionspåfyllnader** kan du manuellt behandla påfyllnaden.

## <a name="open-warehouse-work-needing-attention"></a>Öppet lagerarbete som behöver åtgärdas

Panelen **Öppet lagerarbete som behöver åtgärdas** visar antalet strukturliste- och formelrader som har frisläppts till lagret på obearbetat arbete och som har ett råmaterialdatum som infaller tidigare än eller samtidigt som arbetsytans datum. Raderna måste också förbrukas av en verksamhetsresurs som tillämpas på arbetsytans filter.

När panelen är markerad öppnas sidan **Allat arbete**. Den här sidan filtreras av antalet öppna arbetsrubriker som innehåller arbetsrader från frisläppt strukturliste- och formelrader som uppfyller villkoren för panelen. Från sidan **Allt arbete** kan du manuellt behandla arbetet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]