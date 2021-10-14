---
title: Lagermärkesinventering
description: Det här ämnet innehåller information om märkesinventering som du använder för att jämföra det faktiska lagret hos ett lagerställe med lagerbehållningen.
author: yufeihuang
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64315b8c5f0be1dbd19239a8b07746e90aebb0d4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567377"
---
# <a name="inventory-tag-counting"></a>Lagermärkesinventering

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om märkesinventering som du använder för att jämföra det faktiska lagret hos ett lagerställe med lagerbehållningen.

Genom att skapa rader på sidan **Märkesinventering** sätter du ett märkesnummer på varje artikel i lager, t.ex. ett tal mellan 1 och 500. I samband med inventeringen anger du artikelnumret och kvantiteten på ett motsvarande märke. Denna etikett kan sedan användas som bas för inmatning i märkesinventeringsjournalen. När du bokför journalen för märkesinventering, skapas en ny inventeringsjournal baserad på sidan **Inventering**. Den nya journalen är baserad på journalraderna för märkesinventeringen som du har skapat. Om du vill märkesinventera artiklar efter en viss lagerdimension väljer du dimensionen på sidan **Visa dimension** som visas när du skapar märkesinventeringsjournalen. Inventera artiklar på exempelvis ett visst lagerställe genom att markera **Lagerställe**. Om skjutreglager **Lås artiklar under inventeringen** på sidan **Parametrar för hantering av lager och lagerstyrning** är markerad, kan inte artiklar uppdateras fysiskt under inventering. Artiklar i märkesinventeringsjournaler inte dock inte låsta under inventering. Lagertransaktioner skapas inte förrän märkesinventeringsraderna bokförs och överförs till en inventeringsjournal. Om märkena anges slumpmässigt och du vill identifiera märken som saknas, klickar du på kolumnrubriken **Märke** för att sortera raderna efter märke.

## <a name="additional-resources"></a>Ytterligare resurser

[Rullande inventering](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]