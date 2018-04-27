---
title: "Produktens livscykeltillstånd"
description: "Ett livscykeltillstånd för produkt beskriver livscykelstatusen för en frisläppt produkt eller produktvariant."
author: cvocph
manager: AnnBe
ms.date: 12/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: conradv
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: 236b0253f20330f09f07dbcfa19257350fb5d37f
ms.openlocfilehash: 8ef72de3f226a3270ac0145a20e4da7dfe64f4ba
ms.contentlocale: sv-se
ms.lasthandoff: 02/08/2018

---

# <a name="product-lifecycle-state"></a>Produktens livscykeltillstånd 

[!INCLUDE [banner](../includes/banner.md)]

Ett livscykeltillstånd för produkt beskriver livscykelstatusen för en frisläppt produkt eller produktvariant. Produktens livscykeltillstånd definieras av användaren, vanligtvis en produktchef eller en produktmallchef. Specifika affärsprocesser, t.ex. huvudplanering kan påverkas av ett visst livscykeltillstånd.   

En frisläppt produkt eller produktvariant kan vara kopplade till ett livscykeltillstånd för produkten som dokumenterar med vilket livscykeltillstånd för en viss produkt eller variant används för närvarande. Du kan definiera valfritt antal produktlivscykeltillstånd genom att tilldela ett tillståndsnamn och beskrivning. Du kan välja ett livscykeltillstånd som standardläge för nya frisläppta produkter. Frisläppta produktvarianter ärver deras produktlivscykeltillstånd från deras frisläppa produktmallar när de skapas. När du ändrar livscykeltillståndet i en frisläppt produktmall kan du välja att uppdatera alla befintliga varianter som har samma ursprungliga tillstånd.  

## <a name="create-a-new-product-lifecycle-state"></a>Skapa ett nytt produktlivscykeltillstånd 

- För att skapa ett nytt produktlivscykeltillstånd spelar du upp eller läser uppgiftsguiden **Skapa ett nytt produktlivscykeltillstånd**. 

-  För att skapa ett standardproduktlivscykeltillstånd spelar du upp eller läser uppgiftsguiden **Skapa ett standardproduktlivscykeltillstånd**.   

## <a name="associate-product-lifecycle-states-to-released-products"></a>Associera produktlivscykeltillstånd till frisläppta produkter  

Det finns flera sätt att associera ett produktlivscykeltillstånd till frisläppta produkter eller produktvarianter.

-  Vid skapandet av en ny frisläppt produkt tilldelas standard **produktlivscykeltillstånd** automatiskt. 
-  Vid frisläppning av en produkt till en juridisk person kommer standard **produktlivscykeltillstånd** tilldelas automatiskt. 
-  Vid frisläppning av en produktvariant för en juridisk person i **produktlivscykeltillstånd** som associeras med den utgivna produktmallen i den här juridiska personen tilldelas automatiskt till den nya varianten. 

Du kan uppdatera produktlivscykeltillståndet manuellt med hjälp av: 

-    Listsidan **frisläppta produkter** eller **detaljvy**. 
-  Listsidan **frisläppta produktvarianter** eller **detaljvy**. 
-  Söka efter föråldrade produkter eller produktvarianter baserat på behov och associera ett livscykeltillstånd.  

För detaljerad information om hur du associerar ett produktlivscykeltillstånd, spela upp eller läs följande två uppgiftsguider.

-  För att associera ett produktlivscykeltillstånd till en frisläppt produktmall, spela upp eller läs uppgiftsguiden **tilldela produktlivscykeltillstånd till en frisläppt produktmall**. 

-  För att associera ett produktlivscykeltillstånd till en frisläppt produkt, spela upp eller läs uppgiftsguiden **tilldela produktlivscykeltillstånd till en frisläppt produkt**. 

## <a name="impact-on-master-planning"></a>Påverkan på huvudplanering 

Produktlivscykeltillståndet har bara en kontrollflagga: **är aktiv för planeringtillstånd**. Som standard är inställt på **Ja** för alla skapade produktlivscykeltillstånd, men kan ändras till **Nej**. Om den är inställd på **Nej**, är de associerade produkterna eller frisläppta produktvarianterna: 

-  Undantagna från huvudplaneringen. 
-  Undantagna från strukturlistenivåberäkningen. 

Detaljerad information om hur du använder produktlivscykeltillstånd för att undanta produkter från huvudplanering och strukturlistenivåberäkningen, spela upp eller läs uppgiftsguiden **skapa ett produktlivscykeltillstånd från huvudplaneringen**.

> [!NOTE]
> Av prestandaskäl rekommenderas att koppla alla föråldrade frisläppta produkter eller produktvarianter, särskilt när du arbetar med icke-återanvändningsbara produktkonfigurationsvarianter med produktlivscykeltillstånd som inaktiveras för huvudplanering.  

## <a name="default-migration-import-and-export"></a>Standardmigrering, import och export 

Produktlivscykeltillstånd stöds inte av datatabeller och livscykeltillståndet kan inte anges till ett variabelläge via de frisläppta produktdatatabellerna.

-  Vid migration från tidigare frisläppningar är livscykeltillståndet för alla produkter och produktvarianter tomt.  
-  När du importerar frisläppta produkter via en datatabell, används standard livscykeltillståndet när de skapas.  
-  När du importerar frisläppta produktvarianter via en datatabell, importeras livscykeltillstånd för den frisläppta produktmallen.   

## <a name="find-obsolete-products-and-products-variants"></a>Söka efter föråldrade produkter och produktvarianter 

Du kan köra en simuleringsanalys om du vill söka efter föråldrade frisläppta produkter eller produktvarianter och sedan uppdatera deras status för produktlivscykeltillstånd. Om du vill hitta föråldrade produkter, spela upp och läs uppgiftsguiden **Sök föråldrade produktvarianter och tilldela ett produktlivscykeltillstånd**. Den här uppgiftsguiden visar hur du hittar föråldrade frisläppta produkter eller produktvarianter och hur du associerar ett produktlivscykeltillstånd till de föråldrade produkterna. Här visas också hur du visar resultaten för simulering och bedömer hur många produkter och produktvarianter som ska kopplas till ett nytt produktlivscykeltillstånd när du kör uppdateringen utan simulering.  

Genom att köra analysen i ett simuleringsläge, identifieras produkterna och produktvarianterna som föråldrade och visas i en specifik form där de enkelt kan granskas. Analysen söker efter transaktioner och specifika huvuddata för att identifiera produkter som inte har några behov inom variabel period och inga huvuddata som kan leda till efterfrågan. Nya frisläppta produkter inom variabelperiod kan uteslutas från analysen. När analysissimuleringen returnerar det förväntade resultatet kan användaren köra analysen och ange ett nytt produktlivscykeltillstånd för alla produkter som identifieras som föråldrade av analysen.  

> [!NOTE]
> Observera att alla analyser och uppdateringar måste utföras inom samma juridiska person.  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>Kriterier för att välja och uppdatera frisläppta produkter eller produktvarianter 

Använd följande kriterier för att välja och uppdatera frisläppta produkter och produktvarianter: 

-    Produktlivscykeltillstånd för produkten eller produktvarianten måste skilja sig från det önskade tillståndet. 
-  Produkten eller produktvarianten skapades för några dagar sedan baserat på hur många dagar som du anger i urvalsdialogrutan. 
-  Det finns inga öppna produktionsorder (status = < avslutas) för produkten eller produktvarianten. 
-  Det finns inga öppna lagertransaktioner (= statusproblem ReservPhysical till QuotationIssue eller statusmottagande registrerad till QuotationReceipt) för produkten eller produktvarianten. 
-  Det finns inga lagertransaktioner inom sista antalet dagar för produkten eller produktvarianten. 
-  Det finns ingen framtida efterfrågan eller leveransprognos för produkten eller produktvarianten.  
-  Inget minsta lagernivå har ställts in i artikeldisponering för produkten eller produktvarianten. 
-  Ingen aktiv fast kvantitetkanbanregel för produkten eller produktvarianten.  
-  Ingen serviceorderrad för produkten eller produktvarianten. 
-  Inga aktiva och framtida försäljnings- eller inköpsrader för produkten eller produktvarianten. 
-  Produkten eller produktvarianten används inte i en strukturlista som är kopplad till en ej förfallen godkänd strukturlisteversion för en produkt eller variant som är aktiv för planering.

## <a name="related-topics"></a>Relaterade ämnen

-  [Skapa ett nytt produktlivscykeltillstånd (Uppgiftsguide)](tasks/new-product-lifecycle-state.md)
-  [Skapa ett standardiserat produktlivscykeltillstånd (Uppgiftsguide)](tasks/default-product-lifecycle-state.md)
-  [Associera ett produktlivscykeltillstånd till en frisläppt produktmall (Uppgiftsguide)](tasks/product-lifecycle-state-released-product-master.md)
-  [Associera ett produktlivscykeltillstånd till en frisläppt produkt (Uppgiftsguide)](tasks/product-lifecycle-state-released-product.md)
-  [Sök efter inaktuella produktvarianter och tilldela ett produktlivscykeltillstånd (Uppgiftsguide)](tasks/obsolete-product-variants.md)
-  [Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering (Uppgiftsguide)](tasks/exclude-products-master-planning.md)

