---
title: Bokför införseljournalen för returnerade produkter
description: Bokför införseljournalen för returnerade produkter
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 184ce418ff2ec4b891a24b2b75d37b6b4f5d23f3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006651"
---
# <a name="post-arrival-journal-for-returned-products"></a>Bokför införseljournalen för returnerade produkter 

[!include [banner](../includes/banner.md)]


Om du vill bearbeta en retur, validera först returkvantiteten, uppdatera kvantitetsfältet i artikelinförseljournalen. Därefter välja en dispositionskod eller ange att de returnerade artiklarna måste kontrolleras. När du har slutfört de här stegen kan du bokföra artikelinförseljournalen för returordern.

1.  Klicka på **Lagerhantering** \> **Periodisk** \> **Införselöversikt**.

2.  I filtret **inställningsnamn** väljer du **returorder**.

3.  Om listan med inleveranser är lång kan du använda fälten i området **Intervall** för att begränsa listan.

4.  Hitta raden för den returorder som du vill bokföra, markera rutan **Välj för införsel** och klicka på **Starta införsel**.

5.  Klicka på **journaler**\>**visa införsel från inleveranser** för att öppna formuläret **platsjournal**.
    

    > [!TIP]
    > <P>Om du vill visa detaljerad information markerar du en journal och klickar på <STRONG>Rader</STRONG>.</P>


6.  Gör de uppdateringar som du vill göra och klicka sedan på **Bokför**.

När journalen har bokförts registreras de returnerade artiklarna i lagret och formuläret **Returorder** visar information om att artiklarna har inlevererats till lagerstället.

## <a name="see-also"></a>Se även

[Platsjournal (formulär)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]