---
title: Fiktiva artiklar
description: Det här avsnittet beskrivs i detalj, hur radtypen fiktiv kan användas för rader i en strukturlista (BOM) och en formel i Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: tfehr
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: kamaybac
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: b14bebadd7088c9bbcfb6b1c5df1fe1a3c98694d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437852"
---
# <a name="phantom-items"></a>Fiktiva artiklar

[!include [banner](../includes/banner.md)]

Det här avsnittet beskrivs i detalj, hur radtypen fiktiv kan användas för rader i en strukturlista (BOM) och en formel. I bilden nedan (a) är strukturlistan för produkt H och delar F och G och (b) flödesbladet för produkter H och del F.

![Produkt H och del F](media/product-H-part-F.png)


Illustrationen visar ett exempel på en strukturlista på två nivåer. Slutprodukten H representerar en produkt för en maskinsammansättning. Maskinsammansättningen består av två delar, en elektrisk enhet (F) med två material (A och B) och en uppsättning förpackningsmaterial (G) som också har två material (C och D). Ett annat material (E) används vid allmän sammansättning av maskinen.

![Produkt H och del F](media/product-H-part-B.png)

Bilden ovan representerar teknikstrukturlistan för produkt H. Den här strukturen ger en bra översikt över delarna och komponenterna i maskinens övergripande sammansättning. Men även om produktutvecklare kanske föredrar att visa strukturlistan på detta sätt, kanske strukturen inte korrekt återger hur maskinen byggs i fabriken. 

T.ex. teknikstrukturen i föregående illustration anger till exempel att den elektriska enheten F sammansätts som en separat del på en separat arbetsorder. Men i verkstaden kanske det anses mer optimalt att sammansätta den elektriska enheten som en del av hela maskinsammansättningen och inte som en separat arbetsorder.

Teknikstrukturen indikerar också att del G är en separat del. Men i den här strukturen representerar del G inte en fysisk del utan en samling av förpackningsmaterial. 

Därför, även om en teknikstrukturlista ger bra värde för designen av en produkt och underhåll av den designen, den behöver inte vara det mest logiska sättet att stödja produktens tillverkningskörningsprocess. Däremot representerar en tillverkningsstrukturlista det bästa sättet att skapa en produkt.

Följande bild visar hur föregående teknikstrukturlista övergår till en tillverkningsstrukturlista. I den här illustrationen (a) är strukturlistan för produkt H och b flödesbladet för produkt H.

I den här strukturen kan du se att det inte finns några delar F och G och de material som dessa delar består av har upphöjts till nästa strukturlistenivå. 

Till skillnad från teknikstrukturlistan som hade två operationsblad har tillverkningsstrukturlistan endast ett operationsblad. Förpackningsoperationen som var kopplad till del G har också utökats och ingår nu i operationsbladet för produkt H. Sammansättningen av den elektriska enheten är den första operationen. Denna order passar bra, eftersom enheten används i nästa operation som är maskinsammansättningen. Den sista operationen är förpackningsoperationen som förbrukar två förpackningsmaterial (C och D).

Övergången mellan teknikstrukturlistan och tillverkningsstrukturlistan har aktiverats via radtypen Fiktiv strukturlista. Såsom begreppet ”fiktiv” anger, har delar F och G försvunnit under övergångsperioden mellan de två typerna av strukturlista. I det här exemplet används radtypen Fiktiv till strukturlisteraderna för delar F och G i teknikstrukturlistan. När en produktions- eller batchorder skapas kopieras teknikstrukturlista till produktions- eller batchordern. Sedan när ordern beräknas, sker övergången från teknikstrukturlistan till tillverkningsstrukturlistan enligt föregående illustrationer. Från operationsbladet i den andra bilden inmatas förpackningsmaterialen C och D för operationen. 

## <a name="multilevel-phantom-bom-structures"></a>Fiktiva artikelstrukturlistor på flera nivåer
Radtypen Fiktiv kan användas i strukturlistor på flera nivåer, vilket visas i följande illustration. I den här illustrationen (a) är strukturlistan för produkt G och (b) flödesbladet för delar E och produkt G. 

![Produkt G och del F med bladflöde](media/product-G-route-sheet-G.png)


Följande bild visar den resulterande tillverkningsstrukturlistan och flödesbladet och strukturlisteraderna för delar E och F konfigureras så att radtypen är Fiktiv. I den här illustrationen (a) är strukturlistan för produkt G och (b) flödesbladet för produkt G.

![Produkt G](media/product-G.png)


## <a name="phantom-and-route-network"></a>Fiktiv och flödesnätverk
Fiktiva strukturlistor kan också användas för en strukturlista som har ett flödesnätverk. I ett flödesnätverk körs en eller flera åtgärder parallellt. Nedan visas ett exempel på ett flödesnätverk som används i en strukturlista med flera nivåer. I den här illustrationen (a) är strukturlistan för produkt G och F och (b) flödesbladet för produkt G och del F som har flödesnätverk.

![Produkt G och del F](media/product-G-part-F.png)


I bilden nedan (a) är strukturlistan för produkt G och del F och (b) flödesbladet för produkt G och del F.

![Produkt G och del F med bladflöde](media/product-G-part-F-with-route-sheet.png)
