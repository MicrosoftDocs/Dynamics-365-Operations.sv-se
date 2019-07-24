---
title: Lagermärkesinventering
description: Det här ämnet innehåller information om märkesinventering som du använder för att jämföra det faktiska lagret hos ett lagerställe med lagerbehållningen.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 704330d136afee08fcee36db19acf72297fddac8
ms.sourcegitcommit: a237fc58ddb94ff798fac70feaf1431e00080489
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2019
ms.locfileid: "1624871"
---
# <a name="inventory-tag-counting"></a>Lagermärkesinventering

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Det här ämnet innehåller information om märkesinventering som du använder för att jämföra det faktiska lagret hos ett lagerställe med lagerbehållningen.

Genom att skapa rader på sidan **Märkesinventering** sätter du ett märkesnummer på varje artikel i lager, t.ex. ett tal mellan 1 och 500. I samband med inventeringen anger du artikelnumret och kvantiteten på ett motsvarande märke. Denna etikett kan sedan användas som bas för inmatning i märkesinventeringsjournalen. När du bokför journalen för märkesinventering, skapas en ny inventeringsjournal baserad på sidan **Inventering**. Den nya journalen är baserad på journalraderna för märkesinventeringen som du har skapat. Om du vill märkesinventera artiklar efter en viss lagerdimension väljer du dimensionen på sidan **Visa dimension** som visas när du skapar märkesinventeringsjournalen. Inventera artiklar på exempelvis ett visst lagerställe genom att markera **Lagerställe**. Om skjutreglager **Lås artiklar under inventeringen** på sidan **Parametrar för hantering av lager och lagerstyrning** är markerad, kan inte artiklar uppdateras fysiskt under inventering. Artiklar i märkesinventeringsjournaler inte dock inte låsta under inventering. Lagertransaktioner skapas inte förrän märkesinventeringsraderna bokförs och överförs till en inventeringsjournal. Om märkena anges slumpmässigt och du vill identifiera märken som saknas, klickar du på kolumnrubriken **Märke** för att sortera raderna efter märke.

## <a name="additional-resources"></a>Ytterligare resurser

[Rullande inventering](../warehousing/cycle-counting.md)
