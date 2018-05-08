---
title: "Förpackningsmaterial och avgifter"
description: "Avgifter för förpackningsmaterial betalas i vissa intervaller till ett återvinningsföretag. Ett belopp per viktenhet måste betalas för varje material som en förpackningsenhet består av. Avgifter för förpackningsmaterial beräknas och rapporteras, men inga redovisningstransaktioner bokförs eftersom avgifterna inte räknas som skatter som måste betalas till en myndighet."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b131cdfa2f0e3b6a8f116464323d49eaa4584634
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="packing-materials-and-fees"></a>Förpackningsmaterial och avgifter

[!include [banner](../includes/banner.md)]

Avgifter för förpackningsmaterial betalas i vissa intervaller till ett återvinningsföretag. Ett belopp per viktenhet måste betalas för varje material som en förpackningsenhet består av. Avgifter för förpackningsmaterial beräknas och rapporteras, men inga redovisningstransaktioner bokförs eftersom avgifterna inte räknas som skatter som måste betalas till en myndighet.

Vikt och avgifter för förpackningsmaterial beräknas för försäljnings- och inköpsorderrader.

Du kan definiera en eller fler förpackningsenheter för en artikel, för en förpackningsgrupp med artiklar eller för alla artiklar. En förpackningsenhet består av förpackningsmaterialen, deras vikt och antalet artiklar i förpackningsenheten. En kod för förpackningsmaterial tilldelas varje typ av förpackningsmaterial som definieras. Baserat på koden för förpackningsmaterial kan du ange ett pris för en angiven period. Debitering för förpackningsmaterial beräknas utifrån den här informationen.

| **Obs!**                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Även om ditt företag inte betalar avgifter för förpackningsmaterial kan du använda funktionen för att beräkna statistik om förpackningsmaterialets vikt. |

## <a name="setup-requirements-for-packing-material-fees"></a>Ställa in krav för avgifter för förpackningsmaterial
Innan du beräknar vikter eller avgifter för förpackningsmaterial, eller båda, måste du skapa följande basdata:

-   Förpackningsgrupper – Skapa förpackningsgrupper att tilldela till artiklar.
-   Förpackningsmaterialskoder – Skapa förpackningsmaterialskoder för varje typ av förpackningsmaterial som definieras.
-   Förpackningsenheter – Ange en förpackningsenhet för en artikel, för en förpackningsgrupp eller för alla artiklar. För varje förpackningsenhet definierar du vilket förpackningsmaterial som ska inkluderas, tilldelar vikter och, i fältet Faktor för förpackningsenhet, anger du konverteringsfaktorn från lagerenheten.
-   Avgifter för förpackningsmaterial – Ange avgifter för förpackningsmaterial per kod för förpackningsmaterial. För varje materialtyp anger du giltighetsperioden, priset per material, valutan och enheten.

## <a name="packing-units-on-sales-order-lines"></a>Förpackningsenheter på försäljningsorderrader
När du skapar en försäljningsorderrad görs en kontroll av huruvida förpackningsenheter har angetts för artikeln. I sådana fall uppdateras försäljningsorderraden med den angivna förpackningsenheten och kvantiteten i förpackningsenheten. Kvantiteten i förpackningsenheten baseras på den beställda kvantiteten delat med antalet artiklar i den valda förpackningsenheten. Om ingen förpackningsenhet har angetts kan du manuellt ange en förpackningsenhet och en kvantitet i förpackningsenheten på försäljningsorderraden. Det går också att ändra förpackningsenheten och kvantiteten i förpackningsenheten när du bokför försäljningsorderraden. Det här är relevant om försäljningsorderraden bara levereras eller faktureras delvis. När du fakturerar försäljningsordern skapas transaktioner för förpackningsmaterial. Transaktioner för förpackningsmaterial innehåller vikten för emballagematerialen för försäljningsraden. Du kan också ändra transaktionerna efter faktureringen och sedan skapa nya transaktioner.

## <a name="packing-units-on-purchase-order-lines"></a>Förpackningsenheter på inköpsorderrader
Förpackningsmaterialstransaktioner för en inköpsorderrad skapas inte av systemet. Du kan skapa transaktioner för fakturerade inköpsorderrader manuellt på sidan **Förpackningsmaterialtransaktioner**.

## <a name="set-up-customer-packaging-material-fee-license-numbers"></a>Ställ in kundens licensnummer för förpackningsmaterialavgift
Om kunden ska betala förpackningsmaterialavgifterna anger du kundens licensnummer för förpackningsmaterialavgifter på sidan **Kunder**. När kunden har tilldelats ett licensnummer beräknas förpackningsmaterialavgifterna automatiskt när försäljningsorder faktureras. Efter faktureringen avmarkeras kryssrutan **Beräkna avgift** på sidan **Förpackningsmaterialtransaktioner** eftersom du inte behöver beräkna och skriva ut en rapport. Du kan skriva ut vikter för förpackningsmaterial på fakturan och informera kunderna om att de ska betala avgifterna. 

Om ditt företag ska betala förpackningsmaterialavgifterna ska du inte fylla i kundens licensnummer. Efter faktureringen markeras kryssrutan **Beräkna avgift** på sidan **Förpackningsmaterialtransaktioner**. Detta innebär att avgifterna beräknas när en rapport skapas. Du kan skriva ut vikterna på fakturan och informera kunderna om att ditt företag betalar avgifterna.

## <a name="print-packaging-material-weights-on-invoices"></a>Skriv ut vikter på förpackningsmaterial på fakturor
Du kan skriva ut vikter för förpackningsmaterial på fakturan och ange vem som betalar förpackningsmaterialavgifterna. Vikterna sammanställs efter förpackningsmaterialkod.






