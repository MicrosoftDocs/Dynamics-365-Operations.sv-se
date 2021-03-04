---
title: Produktens livscykeltillstånd – översikt
description: Ett livscykeltillstånd för produkt beskriver livscykelstatusen för en frisläppt produkt eller produktvariant.
author: cvocph
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 51a6b19e84f368bf72b664e120f262ddcf7c7611
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438127"
---
# <a name="product-lifecycle-state-overview"></a>Produktens livscykeltillstånd – översikt

[!include [banner](../includes/banner.md)]

Ett livscykeltillstånd för produkt beskriver livscykelstatusen för en frisläppt produkt eller produktvariant. Produktens livscykeltillstånd definieras av användaren, vanligtvis en produktchef eller en produktmallchef. Specifika affärsprocesser, t.ex. huvudplanering kan påverkas av ett visst livscykeltillstånd.

En frisläppt produkt eller produktvariant kan vara kopplade till ett livscykeltillstånd för produkten som dokumenterar med vilket livscykeltillstånd för en viss produkt eller variant används för närvarande. Du kan definiera valfritt antal produktlivscykeltillstånd genom att tilldela ett tillståndsnamn och beskrivning. Du kan välja ett livscykeltillstånd som standardläge för nya frisläppta produkter. Frisläppta produktvarianter ärver deras produktlivscykeltillstånd från deras frisläppa produktmallar när de skapas. När du ändrar livscykeltillståndet i en frisläppt produktmall kan du välja att uppdatera alla befintliga varianter som har samma ursprungliga tillstånd.  

## <a name="create-a-new-product-lifecycle-state"></a>Skapa ett nytt livscykeltillstånd för produkt

- För att skapa ett nytt produktlivscykeltillstånd, se [Skapa ett nytt produktlivscykeltillstånd](tasks/new-product-lifecycle-state.md).

- För att skapa ett standard produktlivscykeltillstånd, se [Skapa ett standard produktlivscykeltillstånd](tasks/default-product-lifecycle-state.md).

## <a name="associate-product-lifecycle-states-to-released-products"></a>Associera produktlivscykeltillstånd till frisläppta produkter  

Det finns flera sätt att associera ett produktlivscykeltillstånd till frisläppta produkter eller produktvarianter.

- Vid skapandet av en ny frisläppt produkt tilldelas standard **produktlivscykeltillstånd** automatiskt.
- Vid frisläppning av en produkt till en juridisk person kommer standard **produktlivscykeltillstånd** tilldelas automatiskt.
- Vid frisläppning av en produktvariant för en juridisk person i **produktlivscykeltillstånd** som associeras med den utgivna produktmallen i den här juridiska personen tilldelas automatiskt till den nya varianten.

Du kan uppdatera produktlivscykeltillståndet manuellt med hjälp av:

- Listsidan **frisläppta produkter** eller **detaljvy**.
- Listsidan **frisläppta produktvarianter** eller **detaljvy**.
- Söka efter föråldrade produkter eller produktvarianter baserat på behov och associera ett livscykeltillstånd.  

Mer information:

- För att associera ett produktlivscykeltillstånd till en frisläppt produktmall, se [tilldela produktlivscykeltillstånd till en frisläppt produktmall](tasks/product-lifecycle-state-released-product-master.md).

- För att associera ett produktlivscykeltillstånd till en frisläppt produkt, se [tilldela produktlivscykeltillstånd till en frisläppt produkt](tasks/product-lifecycle-state-released-product.md).

## <a name="impact-on-master-planning"></a>Påverkan på huvudplanering

Produktlivscykeltillståndet har bara en kontrollflagga: **är aktiv för planeringtillstånd**. Som standard är inställt på **Ja** för alla skapade produktlivscykeltillstånd, men kan ändras till **Nej**. Om den är inställd på **Nej**, är de associerade produkterna eller frisläppta produktvarianterna:

- Undantagna från huvudplaneringen.
- Undantagna från strukturlistenivåberäkningen.

Detaljerad information om hur du använder produktlivscykeltillstånd för att undanta produkter från huvudplanering och strukturlistenivåberäkningen, se [skapa ett produktlivscykeltillstånd från huvudplaneringen](tasks/exclude-products-master-planning.md).

> [!NOTE]
> Av prestandaskäl rekommenderas att koppla alla föråldrade frisläppta produkter eller produktvarianter, särskilt när du arbetar med icke-återanvändningsbara produktkonfigurationsvarianter med produktlivscykeltillstånd som inaktiveras för huvudplanering.  

## <a name="default-migration-import-and-export"></a>Standardmigrering, import och export

Produktlivscykeltillstånd stöds av datatabeller och livscykeltillståndet kan anges till ett variabelläge via antingen de frisläppta produktdataentiteten eller de frisläppta variantdataentiteten.

## <a name="find-obsolete-products-and-products-variants"></a>Söka efter föråldrade produkter och produktvarianter

Du kan köra en simuleringsanalys om du vill söka efter föråldrade frisläppta produkter eller produktvarianter och sedan uppdatera deras status för produktlivscykeltillstånd. Om du vill hitta föråldrade produkter, se [Sök föråldrade produktvarianter och tilldela ett produktlivscykeltillstånd](tasks/obsolete-product-variants.md). Det här ämnet visar hur du hittar föråldrade frisläppta produkter eller produktvarianter och hur du associerar ett produktlivscykeltillstånd till de föråldrade produkterna. Här visas också hur du visar resultaten för simulering och bedömer hur många produkter och produktvarianter som ska kopplas till ett nytt produktlivscykeltillstånd när du kör uppdateringen utan simulering.  

Genom att köra analysen i ett simuleringsläge, identifieras produkterna och produktvarianterna som föråldrade och visas i en specifik form där de enkelt kan granskas. Analysen söker efter transaktioner och specifika huvuddata för att identifiera produkter som inte har några behov inom variabel period och inga huvuddata som kan leda till efterfrågan. Nya frisläppta produkter inom variabelperiod kan uteslutas från analysen. När analysissimuleringen returnerar det förväntade resultatet kan användaren köra analysen och ange ett nytt produktlivscykeltillstånd för alla produkter som identifieras som föråldrade av analysen.  

> [!NOTE]
> Observera att alla analyser och uppdateringar måste utföras inom samma juridiska person.  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>Kriterier för att välja och uppdatera frisläppta produkter eller produktvarianter

Använd följande kriterier för att välja och uppdatera frisläppta produkter och produktvarianter:

- Produktlivscykeltillstånd för produkten eller produktvarianten måste skilja sig från det önskade tillståndet.
- Produkten eller produktvarianten skapades för några dagar sedan baserat på hur många dagar som du anger i urvalsdialogrutan.
- Det finns inga öppna produktionsorder (status = < avslutas) för produkten eller produktvarianten.
- Det finns inga öppna lagertransaktioner (= statusproblem ReservPhysical till QuotationIssue eller statusmottagande registrerad till QuotationReceipt) för produkten eller produktvarianten.
- Det finns inga lagertransaktioner inom sista antalet dagar för produkten eller produktvarianten.
- Det finns ingen framtida efterfrågan eller leveransprognos för produkten eller produktvarianten.  
- Inget minsta lagernivå har ställts in i artikeldisponering för produkten eller produktvarianten.
- Ingen aktiv fast kvantitetkanbanregel för produkten eller produktvarianten.  
- Ingen serviceorderrad för produkten eller produktvarianten.
- Inga aktiva och framtida försäljnings- eller inköpsrader för produkten eller produktvarianten.
- Produkten eller produktvarianten används inte i en strukturlista som är kopplad till en ej förfallen godkänd strukturlisteversion för en produkt eller variant som är aktiv för planering.

## <a name="related-topics"></a>Relaterade ämnen

- [Skapa ett nytt livscykeltillstånd för produkt](tasks/new-product-lifecycle-state.md)
- [Skapa ett standardlivscykeltillstånd för produkt](tasks/default-product-lifecycle-state.md)
- [Tilldela ett produktlivscykeltillstånd för en frisläppt produktmall](tasks/product-lifecycle-state-released-product-master.md)
- [Tilldela ett produktlivscykeltillstånd för en frisläppt produkt](tasks/product-lifecycle-state-released-product.md)
- [Söka efter föråldrade produktvarianter och tilldela ett produktlivscykeltillstånd](tasks/obsolete-product-variants.md)
- [Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering](tasks/exclude-products-master-planning.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]