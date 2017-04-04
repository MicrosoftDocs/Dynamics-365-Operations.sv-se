---
title: "Lagermärkesinventering"
description: "Det här avsnittet innehåller information om märkesinventering som du använder för att jämföra det faktiska lagret hos ett lagerställe med lagerbehållningen."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 896b91647b65843bf67211cab68b4dd08e379b18
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-tag-counting"></a>Lagermärkesinventering

Det här avsnittet innehåller information om märkesinventering som du använder för att jämföra det faktiska lagret hos ett lagerställe med lagerbehållningen. 

Genom att skapa rader på de **Märkesinventering** sidan du sätt ett märkesnummer på varje artikel i lager, t ex ett tal mellan 1 och 500. Under inventeringen anger du artikelnumret och kvantiteten för ett motsvarande märke. Denna etikett kan sedan användas som bas för inmatning i märkesinventeringsjournalen. När du bokför journalen för märkesinventering, skapas en ny inventeringsjournal baserad på sidan **Inventering**. Den nya journalen är baserad på journalraderna för märkesinventeringen som du har skapat. Om du vill märkesinventera artiklar efter en viss lagerdimension väljer du dimensionen på sidan **Visa dimension** som visas när du skapar märkesinventeringsjournalen. Inventera artiklar på exempelvis ett visst lagerställe genom att markera **Lagerställe**. Om skjutreglager **Lås artiklar under inventeringen** på sidan **Parametrar för hantering av lager och lagerstyrning** är markerad, kan inte artiklar uppdateras fysiskt under inventering. Artiklar i märkesinventeringsjournaler inte dock inte låsta under inventering. Lagertransaktioner skapas inte förrän märkesinventeringsraderna bokförs och överförs till en inventeringsjournal. Om märkena anges slumpmässigt och du vill identifiera märken som saknas, klickar du på kolumnrubriken **Märke** för att sortera raderna efter märke.

<a name="see-also"></a>Se även
--------

[Cycle counting](../warehousing/cycle-counting.md)

